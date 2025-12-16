# Data Directory

This directory contains all data files used by the Visa Journey Agent.

## Structure

```
data/
├── raw/              # Original scraped content (HTML/Markdown)
├── processed/        # Cleaned and chunked documents
└── vector_db/        # ChromaDB persistent storage
```

## Usage

- Raw data from web scrapers is stored in `raw/`
- Processed chunks are saved in `processed/`
- ChromaDB automatically manages `vector_db/`

**Note**: These directories are excluded from git to avoid large file commits.
