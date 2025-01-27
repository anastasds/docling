# Retrieval with Qdrant¶

| Step         | Tech      | Execution   |
|--------------|-----------|-------------|
| Embedding    | FastEmbed | 💻 Local     |
| Vector store | Qdrant    | 💻 Local     |

## Overview¶

This example demonstrates using Docling with Qdrant to perform a hybrid search across your documents using dense and sparse vectors.

We'll chunk the documents using Docling before adding them to a Qdrant collection. By limiting the length of the chunks, we can preserve the meaning in each vector embedding.

## Setup¶

- 👉 Qdrant client uses FastEmbed to generate vector embeddings. You can install the fastembed-gpu package if you've got the hardware to support it.

Let's import all the classes we'll be working with.

- For Docling, we'll set the  allowed formats to HTML since we'll only be working with webpages in this tutorial.
- If we set a sparse model, Qdrant client will fuse the dense and sparse results using RRF. Reference.

We can now download and chunk the document using Docling. For demonstration, we'll use an article about chunking strategies :)

Let's now upload the documents to Qdrant.

- The add() method batches the documents and uses FastEmbed to generate vector embeddings on our machine.

## Retrieval¶