# Hybrid chunking¶

## Overview¶

Hybrid chunking applies tokenization-aware refinements on top of document-based hierarchical chunking.

For more details, see here.

## Setup¶

## Conversion¶

## Chunking¶

### Basic usage¶

For a basic usage scenario, we can just instantiate a HybridChunker, which will use
the default parameters.

Note that the text you would typically want to embed is the context-enriched one as
returned by the serialize() method:

### Advanced usage¶

For more control on the chunking, we can parametrize through the HybridChunker
arguments illustrated below.

Notice how tokenizer and embed\_model further below are single-sourced from
EMBED\_MODEL\_ID.
This is important for making sure the chunker and the embedding model are using the same
tokenizer.

Points to notice looking at the output chunks below:

- Where possible, we fit the limit of 64 tokens for the metadata-enriched serialization form (see chunk 2)
- Where neeeded, we stop before the limit, e.g. see cases of 63 as it would otherwise run into a comma (see chunk 6)
- Where possible, we merge undersized peer chunks (see chunk 0)
- "Tail" chunks trailing right after merges may still be undersized (see chunk 8)