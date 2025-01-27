# Conversion of custom XML¶

| Step         | Tech                                 | Execution   |
|--------------|--------------------------------------|-------------|
| Embedding    | Hugging Face / Sentence Transformers | 💻 Local     |
| Vector store | Milvus                               | 💻 Local     |
| Gen AI       | Hugging Face Inference API           | 🌐 Remote    |

## Overview¶

This is an example of using Docling for converting structured data (XML) into a unified document
representation format, DoclingDocument, and leverage its riched structured content for RAG applications.

Data used in this example consist of patents from the United States Patent and Trademark Office (USPTO) and medical
articles from PubMed Central® (PMC).

In this notebook, we accomplish the following:

- Simple conversion of supported XML files in a nutshell
- An end-to-end application using public collections of XML files supported by Docling
    - Setup the API access for generative AI
    - Fetch the data from USPTO and PubMed Central® sites, using Docling custom backends
    - Parse, chunk, and index the documents in a vector database
    - Perform RAG using LlamaIndex Docling extension

For more details on document chunking with Docling, refer to the Chunking documentation. For RAG with Docling and LlamaIndex, also check the example RAG with LlamaIndex.

## Simple conversion¶

The XML file format defines and stores data in a format that is both human-readable and machine-readable.
Because of this flexibility, Docling requires custom backend processors to interpret XML definitions and convert them into DoclingDocument objects.

Some public data collections in XML format are already supported by Docling (USTPO patents and PMC articles). In these cases, the document conversion is straightforward and the same as with any other supported format, such as PDF or HTML. The execution example in Simple Conversion is the recommended usage of Docling for a single file:

Once the document is converted, it can be exported to any format supported by Docling. For instance, to markdown (showing here the first lines only):

If the XML file is not supported, a ConversionError message will be raised.

You can always refer to the Usage documentation page for a list of supported formats.

## End-to-end application¶

This section describes a step-by-step application for processing XML files from supported public collections and use them for question-answering.

### Setup¶

Requirements can be installed as shown below. The --no-warn-conflicts argument is meant for Colab's pre-populated Python environment, feel free to remove for stricter usage.

This notebook uses HuggingFace's Inference API. For an increased LLM quota, a token can be provided via the environment variable HF\_TOKEN.

If you're running this notebook in Google Colab, make sure you add your API key as a secret.

We can now define the main parameters:

### Fetch the data¶

In this notebook we will use XML data from collections supported by Docling:

- Medical articles from the PubMed Central® (PMC). They are available in an FTP server as .tar.gz files. Each file contains the full article data in XML format, among other supplementary files like images or spreadsheets.
- Patents from the United States Patent and Trademark Office. They are available in the Bulk Data Storage System (BDSS) as zip files. Each zip file may contain several patents in XML format.

The raw files will be downloaded form the source and saved in a temporary directory.

#### PMC articles¶

The OA file is a manifest file of all the PMC articles, including the URL path to download the source files. In this notebook we will use as example the article Pathogens spread by high-altitude windborne mosquitoes, which is available in the archive file PMC11703268.tar.gz.

#### USPTO patents¶

Since each USPTO file is a concatenation of several patents, we need to split its content into valid XML pieces. The following code downloads a sample zip file, split its content in sections, and dumps each section as an XML file. For simplicity, this pipeline is shown here in a sequential manner, but it could be parallelized.

### Using the backend converter (optional)¶

- The custom backend converters PubMedDocumentBackend and PatentUsptoDocumentBackend aim at handling the parsing of PMC articles and USPTO patents, respectively.
- As any other backends, you can leverage the function is\_valid() to check if the input document is supported by the this backend.
- Note that some XML sections in the original USPTO zip file may not represent patents, like sequence listings, and therefore they will show as invalid by the backend.

Calling the function convert() will convert the input document into a DoclingDocument

✏️ Tip: in general, there is no need to use the backend converters to parse USPTO or PubMed XML files. The generic DocumentConverter object tries to guess the input document format and applies the corresponding backend parser. The conversion shown in Simple Conversion is the recommended usage for the supported XML files.

### Parse, chunk, and index¶

The DoclingDocument format of the converted patents has a rich hierarchical structure, inherited from the original XML document and preserved by the Docling custom backend.
In this notebook, we will leverage:

- The SimpleDirectoryReader pattern to iterate over the exported XML files created in section Fetch the data.
- The LlamaIndex extensions, DoclingReader and DoclingNodeParser, to ingest the patent chunks into a Milvus vectore store.
- The HierarchicalChunker implementation, which applies a document-based hierarchical chunking, to leverage the patent structures like sections and paragraphs within sections.

Refer to other possible implementations and usage patterns in the Chunking documentation and the RAG with LlamaIndex notebook.

##### Set the Docling reader and the directory reader¶

Note that DoclingReader uses Docling's DocumentConverter by default and therefore it will recognize the format of the XML files and leverage the PatentUsptoDocumentBackend automatically.

For demonstration purposes, we limit the scope of the analysis to the first 100 patents.

##### Set the node parser¶

Note that the HierarchicalChunker is the default chunking implementation of the DoclingNodeParser.

##### Set a local Milvus database and run the ingestion¶

Finally, add the PMC article to the vector store directly from the reader.

### Question-answering with RAG¶

The retriever can be used to identify highly relevant documents:

With the query engine, we can run the question-answering with the RAG pattern on the set of indexed documents.

First, we can prompt the LLM directly:

Now, we can compare the response when the model is prompted with the indexed PMC article as supporting context: