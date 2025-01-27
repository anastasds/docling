# RAG with Haystack¶

| Step         | Tech                                 | Execution   |
|--------------|--------------------------------------|-------------|
| Embedding    | Hugging Face / Sentence Transformers | 💻 Local     |
| Vector store | Milvus                               | 💻 Local     |
| Gen AI       | Hugging Face Inference API           | 🌐 Remote    |

## Overview¶

This example leverages the
Haystack Docling extension, along with
Milvus-based document store and retriever instances, as well as sentence-transformers
embeddings.

The presented DoclingConverter component enables you to:

- use various document types in your LLM applications with ease and speed, and
- leverage Docling's rich format for advanced, document-native grounding.

DoclingConverter supports two different export modes:

- ExportType.MARKDOWN: if you want to capture each input document as a separate
Haystack document, or
- ExportType.DOC\_CHUNKS (default): if you want to have each input document chunked and
to then capture each individual chunk as a separate Haystack document downstream.

The example allows to explore both modes via parameter EXPORT\_TYPE; depending on the
value set, the ingestion and RAG pipelines are then set up accordingly.

## Setup¶

- 👉 For best conversion speed, use GPU acceleration whenever available; e.g. if running on Colab, use GPU-enabled runtime.
- Notebook uses HuggingFace's Inference API; for increased LLM quota, token can be provided via env var HF\_TOKEN.
- Requirements can be installed as shown below (--no-warn-conflicts meant for Colab's pre-populated Python env; feel free to remove for stricter usage):

## Indexing pipeline¶

## RAG pipeline¶

Below we print out the RAG results. If you have used ExportType.DOC\_CHUNKS, notice how
the sources contain document-level grounding (e.g. page number or bounding box
information):