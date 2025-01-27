# RAG with Weaviate¶

| Step         | Tech      | Execution   |
|--------------|-----------|-------------|
| Embedding    | Open AI   | 🌐 Remote    |
| Vector store | Weavieate | 💻 Local     |
| Gen AI       | Open AI   | 🌐 Remote    |

## A recipe 🧑‍🍳 🐥 💚¶

This is a code recipe that uses Weaviate to perform RAG over PDF documents parsed by Docling.

In this notebook, we accomplish the following:

- Parse the top machine learning papers on arXiv using Docling
- Perform hierarchical chunking of the documents using Docling
- Generate text embeddings with OpenAI
- Perform RAG using Weaviate

To run this notebook, you'll need:

- An OpenAI API key
- Access to GPU/s

Note: For best results, please use GPU acceleration to run this notebook. Here are two options for running this notebook:

1. Locally on a MacBook with an Apple Silicon chip. Converting all documents in the notebook takes ~2 minutes on a MacBook M2 due to Docling's usage of MPS accelerators.
2. Run this notebook on Google Colab. Converting all documents in the notebook takes ~8 mintutes on a Google Colab T4 GPU.

### Install Docling and Weaviate client¶

Note: If Colab prompts you to restart the session after running the cell below, click "restart" and proceed with running the rest of the notebook.

## 🐥 Part 1: Docling¶

Part of what makes Docling so remarkable is the fact that it can run on commodity hardware. This means that this notebook can be run on a local machine with GPU acceleration. If you're using a MacBook with a silicon chip, Docling integrates seamlessly with Metal Performance Shaders (MPS). MPS provides out-of-the-box GPU acceleration for macOS, seamlessly integrating with PyTorch and TensorFlow, offering energy-efficient performance on Apple Silicon, and broad compatibility with all Metal-supported GPUs.

The code below checks to see if a GPU is available, either via CUDA or MPS.

Here, we've collected 10 influential machine learning papers published as PDFs on arXiv. Because Docling does not yet have title extraction for PDFs, we manually add the titles in a corresponding list.

Note: Converting all 10 papers should take around 8 minutes with a T4 GPU.

### Convert PDFs to Docling documents¶

Here we use Docling's .convert\_all() to parse a batch of PDFs. The result is a list of Docling documents that we can use for text extraction.

Note: Please ignore the ERR# message.

### Post-process extracted document data¶

#### Perform hierarchical chunking on documents¶

We use Docling's HierarchicalChunker() to perform hierarchy-aware chunking of our list of documents. This is meant to preserve some of the structure and relationships within the document, which enables more accurate and relevant retrieval in our RAG pipeline.

Because we're splitting the documents into chunks, we'll concatenate the article title to the beginning of each chunk for additional context.

## 💚 Part 2: Weaviate¶

### Create and configure an embedded Weaviate collection¶

We'll be using the OpenAI API for both generating the text embeddings and for the generative model in our RAG pipeline. The code below dynamically fetches your API key based on whether you're running this notebook in Google Colab and running it as a regular Jupyter notebook. All you need to do is replace openai\_api\_key\_var with the name of your environmental variable name or Colab secret name for the API key.

If you're running this notebook in Google Colab, make sure you add your API key as a secret.

Embedded Weaviate allows you to spin up a Weaviate instance directly from your application code, without having to use a Docker container. If you're interested in other deployment methods, like using Docker-Compose or Kubernetes, check out this page in the Weaviate docs.

### Wrangle data into an acceptable format for Weaviate¶

Transform our data from lists to a list of dictionaries for insertion into our Weaviate collection.

### Insert data into Weaviate and generate embeddings¶

Embeddings will be generated upon insertion to our Weaviate collection.

### Query the data¶

Here, we perform a simple similarity search to return the most similar embedded chunks to our search query.

### Perform RAG on parsed articles¶

Weaviate's generate module allows you to perform RAG over your embedded data without having to use a separate framework.

We specify a prompt that includes the field we want to search through in the database (in this case it's text), a query that includes our search term, and the number of retrieved results to use in the generation.

We can see that our RAG pipeline performs relatively well for simple queries, especially given the small size of the dataset. Scaling this method for converting a larger sample of PDFs would require more compute (GPUs) and a more advanced deployment of Weaviate (like Docker, Kubernetes, or Weaviate Cloud). For more information on available Weaviate configurations, check out the documetation.