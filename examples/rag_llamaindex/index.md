# RAG with LlamaIndex¶

| Step         | Tech                                 | Execution   |
|--------------|--------------------------------------|-------------|
| Embedding    | Hugging Face / Sentence Transformers | 💻 Local     |
| Vector store | Milvus                               | 💻 Local     |
| Gen AI       | Hugging Face Inference API           | 🌐 Remote    |

## Overview¶

This example leverages the official LlamaIndex Docling extension.

Presented extensions DoclingReader and DoclingNodeParser enable you to:

- use various document types in your LLM applications with ease and speed, and
- leverage Docling's rich format for advanced, document-native grounding.

## Setup¶

- 👉 For best conversion speed, use GPU acceleration whenever available; e.g. if running on Colab, use GPU-enabled runtime.
- Notebook uses HuggingFace's Inference API; for increased LLM quota, token can be provided via env var HF\_TOKEN.
- Requirements can be installed as shown below (--no-warn-conflicts meant for Colab's pre-populated Python env; feel free to remove for stricter usage):

We can now define the main parameters:

## Using Markdown export¶

To create a simple RAG pipeline, we can:

- define a DoclingReader, which by default exports to Markdown, and
- use a standard node parser for these Markdown-based docs, e.g. a MarkdownNodeParser

## Using Docling format¶

To leverage Docling's rich native format, we:

- create a DoclingReader with JSON export type, and
- employ a DoclingNodeParser in order to appropriately parse that Docling format.

Notice how the sources now also contain document-level grounding (e.g. page number or bounding box information):

## With Simple Directory Reader¶

To demonstrate this usage pattern, we first set up a test document directory.

Using the reader and node\_parser definitions from any of the above variants, usage with SimpleDirectoryReader then looks as follows: