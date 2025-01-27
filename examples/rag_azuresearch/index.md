# RAG with Azure AI Search¶

| Step         | Tech            | Execution   |
|--------------|-----------------|-------------|
| Embedding    | Azure OpenAI    | 🌐 Remote    |
| Vector Store | Azure AI Search | 🌐 Remote    |
| Gen AI       | Azure OpenAI    | 🌐 Remote    |

## A recipe 🧑‍🍳 🐥 💚¶

This notebook demonstrates how to build a Retrieval-Augmented Generation (RAG) system using:

- Docling for document parsing and chunking
- Azure AI Search for vector indexing and retrieval
- Azure OpenAI for embeddings and chat completion

This sample demonstrates how to:

1. Parse a PDF with Docling.
2. Chunk the parsed text.
3. Use Azure OpenAI for embeddings.
4. Index and search in Azure AI Search.
5. Run a retrieval-augmented generation (RAG) query with Azure OpenAI GPT-4o.

### Part 0: Prerequisites¶

- Azure AI Search resource
- Azure OpenAI resource with a deployed embedding and chat completion model (e.g. text-embedding-3-small and gpt-4o)
- Docling 2.12+ (installs docling\_core automatically)  Docling installed (Python 3.8+ environment)
- A GPU-enabled environment is preferred for faster parsing. Docling 2.12 automatically detects GPU if present.

A GPU-enabled environment is preferred for faster parsing. Docling 2.12 automatically detects GPU if present.

    - If you only have CPU, parsing large PDFs can be slower.

### Part 1: Parse the PDF with Docling¶

We’ll parse the Microsoft GraphRAG Research Paper (~15 pages). Parsing should be relatively quick, even on CPU, but it will be faster on a GPU or MPS device if available.

(If you prefer a different document, simply provide a different URL or local file path.)

### Part 2: Hierarchical Chunking¶

We convert the Document into smaller chunks for embedding and indexing. The built-in HierarchicalChunker preserves structure.

### Part 3: Create Azure AI Search Index and Push Chunk Embeddings¶

We’ll define a vector index in Azure AI Search, then embed each chunk using Azure OpenAI and upload in batches.

#### Generate Embeddings and Upload to Azure AI Search¶

### Part 4: Perform RAG over PDF¶

Combine retrieval from Azure AI Search with Azure OpenAI Chat Completions (aka. grounding your LLM)