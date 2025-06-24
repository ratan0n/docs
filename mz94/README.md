# MZ94 - LLM Training Dataset

## Overview
This dataset contains crawled documentation from https://infozone.atlassian.net/wiki/spaces/MD94/, formatted for LLM training and RAG systems.

## Dataset Statistics
- **Total Pages**: 4109
- **Total Words**: 1005892
- **Total Chunks**: 2420
- **Crawled**: 2025-06-24 04:55:10

## Directory Structure

### `/llm_ready/`
Plain text files optimized for LLM training:
- Clean, formatted text content
- Consistent structure with headers
- Document metadata included

### `/jsonl/`
JSONL format for fine-tuning:
- OpenAI/Anthropic compatible format
- Question-answer pairs
- System prompts included

### `/chunks/`
Chunked content for RAG systems:
- 2000 character chunks
- Overlap handling
- Metadata preserved

### `/embeddings/`
Vector database ready format:
- Complete document structure
- Category information
- Embedding-optimized text

## Usage Examples

### Fine-tuning OpenAI GPT:
```bash
openai api fine_tunes.create -t training_data.jsonl -m gpt-3.5-turbo
```

### Loading for RAG:
```python
import json
with open('chunks_index.json', 'r') as f:
    chunks = json.load(f)
    # Process chunks for vector database
```

### Training Custom Model:
```python
# Use files in llm_ready/ directory
for file in glob('llm_ready/*.txt'):
    # Process for training
```

## Data Quality
- Text cleaned and normalized
- Navigation elements removed
- Consistent formatting applied
- Categories and metadata preserved

## License
Educational and research use. Respect original source licensing.
