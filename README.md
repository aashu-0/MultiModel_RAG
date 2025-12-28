# Multimodal RAG System

A powerful search system that understands and correlates information across different data types using multimodal embeddings and semantic search. Built with ImageBind, Elasticsearch, and LLM-powered analysis.

## Overview

This system enables unified search and analysis across multiple data modalities:
- Generate embeddings for images, audio, text, and depth maps
- Perform semantic similarity search across different data types
- Analyze cross-modal connections using LLM reasoning
- Generate comprehensive analytical reports

## Architecture

```
┌─────────────────┐
│  Input Data     │
│ (any modality)  │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  ImageBind      │
│  Embeddings     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Elasticsearch   │
│ Vector Search   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  LLM Analyzer   │
│  (Groq/GPT)     │
└─────────────────┘
```

## Features

- **Multimodal Embeddings**: Uses Meta's ImageBind to generate unified embeddings for:
  - Vision (images, depth maps)
  - Audio (sound files, recordings)
  - Text (documents, descriptions)
  
- **Semantic Search**: Elasticsearch-powered vector similarity search with cosine similarity

- **Cross-Modal Analysis**: Find connections between different types of data

- **LLM-Powered Insights**: Automated analysis and pattern recognition

## Prerequisites

- Python 3.8+
- Elasticsearch 8.17.1+
- Groq API key

## Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd multimodal-search-system
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Set up environment variables**

Create a `.env` file in the root directory:
```env
ELASTICSEARCH_URL=https://your-elasticsearch-url:9200
ELASTICSEARCH_API_KEY=your_api_key_here
GROQ_API_KEY=your_groq_api_key_here
```

## Key Components

### EmbeddingGenerator
Generates 1024-dimensional embeddings using ImageBind.

**Supported modalities:**
- `vision`: Images, photos
- `audio`: WAV files
- `text`: String inputs
- `depth`: Depth maps

### ElasticsearchManager
Manages vector storage and similarity search.

**Key methods:**
- `index_content()`: Store embeddings with metadata
- `search_similar()`: Find similar content
- `delete()`: Remove indexed content

### LLMAnalyzer
Performs intelligent analysis of search results.

**Capabilities:**
- Multi-modal data synthesis
- Pattern recognition
- Cross-modal correlation analysis
- Customizable analysis prompts

## Project Structure

```
.
├── src/
│   ├── embedding_generator.py  # ImageBind embedding generation
│   ├── elastic_manager.py      # Elasticsearch operations
│   └── llm_analyzer.py         # LLM-based analysis
├── .env                        # Environment variables
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## How It Works

1. **Embedding Generation**: ImageBind converts all data types into a shared embedding space where semantically similar content clusters together, regardless of modality.

2. **Vector Storage**: Embeddings are indexed in Elasticsearch, enabling fast similarity search using cosine distance.

3. **Cross-Modal Retrieval**: Query with any modality and retrieve relevant content from any other modality.

4. **LLM Analysis**: Results are analyzed by an LLM to identify patterns, make connections, and generate insights.

## Security

- Never commit your `.env` file
- Use secure API keys
- Implement proper access controls for Elasticsearch
- Sanitize inputs before processing
