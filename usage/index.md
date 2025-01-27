# Usage

## Conversion

### Convert a single document

To convert individual PDF documents, use convert(), for example:

### CLI

You can also use Docling directly from your command line to convert individual files —be it local or by URL— or whole directories.

A simple example would look like this:
docling https://arxiv.org/pdf/2206.01062

To see all available options (export formats etc.) run docling --help. More details in the CLI reference page.

### Supported formats

The document conversion in Docling supports several popular formats, including:

- PDF (Portable Document Format): the format developed by Adobe to present documents compatible across application software, hardware, and operating systems.
- .docx, .xlsx, .pptx (Word, Excel, and PowerPoint): the Open XML formats suppored by Microsof Office.
- Markdown:  a lightweight markup language to add formatting elements to plain text documents.
- AsciiDoc: a plain text markup language for writing technical content.
- HTML (Hypertext Markup Language): the standard markup language for creating web pages.
- XHTML (Extensible Hypertext Markup Language): the XML-based version of HTML.
- XML (Extensible Markup Language): a markup format for storing and transmitting data. Due to its flexibility, Docling requires custom implementations to identify the
semantics of the data. Currently, Docling supports the parsing of USPTO patents and PubMed Central® (PMC) articles.

### Advanced options

#### Adjust pipeline features

The example file custom\_convert.py contains multiple ways
one can adjust the conversion pipeline and features.

##### Control PDF table extraction options

You can control if table structure recognition should map the recognized structure back to PDF cells (default) or use text cells from the structure prediction itself.
This can improve output quality if you find that multiple columns in extracted tables are erroneously merged into one.

Since docling 1.16.0: You can control which TableFormer mode you want to use. Choose between TableFormerMode.FAST (default) and TableFormerMode.ACCURATE (better, but slower) to receive better quality with difficult table structures.

##### Provide specific artifacts path

By default, artifacts such as models are downloaded automatically upon first usage. If you would prefer to use a local path where the artifacts have been explicitly prefetched, you can do that as follows:

#### Impose limits on the document size

You can limit the file size and number of pages which should be allowed to process per document:

#### Convert from binary PDF streams

You can convert PDFs from a binary stream instead of from the filesystem as follows:

#### Limit resource usage

You can limit the CPU threads used by Docling by setting the environment variable OMP\_NUM\_THREADS accordingly. The default setting is using 4 CPU threads.

#### Use specific backend converters

By default, Docling will try to identify the document format to apply the appropriate conversion backend (see the list of supported formats).
You can restrict the DocumentConverter to a set of allowed document formats, as shown in the Multi-format conversion example.
Alternatively, you can also use the specific backend that matches your document content. For instance, you can use HTMLDocumentBackend for HTML pages:

## Chunking

You can chunk a Docling document using a chunker, such as a
HybridChunker, as shown below (for more details check out
this example):

An example chunk would look like this: