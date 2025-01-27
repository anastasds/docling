# RAG with LangChain¶

| Step         | Tech                                 | Execution   |
|--------------|--------------------------------------|-------------|
| Embedding    | Hugging Face / Sentence Transformers | 💻 Local     |
| Vector store | Milvus                               | 💻 Local     |
| Gen AI       | Hugging Face Inference API           | 🌐 Remote    |

This example leverages the
LangChain Docling integration, along with a Milvus
vector store, as well as sentence-transformers embeddings.

The presented DoclingLoader component enables you to:

- use various document types in your LLM applications with ease and speed, and
- leverage Docling's rich format for advanced, document-native grounding.

DoclingLoader supports two different export modes:

- ExportType.MARKDOWN: if you want to capture each input document as a separate
LangChain document, or
- ExportType.DOC\_CHUNKS (default): if you want to have each input document chunked and
to then capture each individual chunk as a separate LangChain document downstream.

The example allows exploring both modes via parameter EXPORT\_TYPE; depending on the
value set, the example pipeline is then set up accordingly.

## Setup¶

- 👉 For best conversion speed, use GPU acceleration whenever available; e.g. if running on Colab, use GPU-enabled runtime.
- Notebook uses HuggingFace's Inference API; for increased LLM quota, token can be provided via env var HF\_TOKEN.
- Requirements can be installed as shown below (--no-warn-conflicts meant for Colab's pre-populated Python env; feel free to remove for stricter usage):

## Document loading¶

Now we can instantiate our loader and load documents.

Note: a message saying "Token indices sequence length is longer than the specified maximum sequence length..." can be ignored in this case — details
here.

Determining the splits:

Inspecting some sample splits:

## Ingestion¶

## RAG¶