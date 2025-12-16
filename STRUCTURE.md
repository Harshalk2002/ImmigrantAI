# 📁 Folder Structure

```
visa-journey-agent/
│
├── 📄 README.md                    # Main project documentation
├── 📄 SETUP.md                     # Installation and setup guide
├── 📄 CONTRIBUTING.md              # Contribution guidelines
├── 📄 LICENSE                      # MIT License
├── 📄 requirements.txt             # Python dependencies
├── 📄 .env.example                 # Environment variables template
├── 📄 .gitignore                   # Git ignore rules
│
├── 📁 data/                        # Data storage
│   ├── 📁 raw/                     # Original scraped content
│   ├── 📁 processed/               # Cleaned and chunked documents
│   ├── 📁 vector_db/               # ChromaDB persistent storage
│   └── 📄 README.md                # Data directory documentation
│
├── 📁 src/                         # Source code
│   ├── 📁 agents/                  # Agent implementations
│   │   ├── 📄 agent1_rag.py        # RAG-based Q&A agent
│   │   └── 📄 agent2_timeline.py   # Timeline generation agent
│   │
│   ├── 📁 scrapers/                # Web scraping modules
│   │   ├── 📄 uscis_scraper.py     # USCIS policy scraper
│   │   ├── 📄 travel_scraper.py    # travel.state.gov scraper
│   │   └── 📄 isss_scraper.py      # University ISSS scraper
│   │
│   ├── 📁 utils/                   # Utility functions
│   │   ├── 📄 embeddings.py        # Embedding generation
│   │   ├── 📄 chunking.py          # Document chunking
│   │   └── 📄 memory.py            # Session memory management
│   │
│   └── 📁 evaluation/              # Evaluation scripts
│       └── 📄 evaluate_rag.py      # RAG evaluation metrics
│
├── 📁 ui/                          # User interface
│   ├── 📄 app.py                   # Main Streamlit application
│   └── 📁 components/              # Reusable UI components
│
├── 📁 notebooks/                   # Jupyter notebooks
│   └── 📄 demo.ipynb               # Google Colab demo notebook
│
├── 📁 tests/                       # Unit tests
│   ├── 📄 test_agent1.py           # Agent 1 tests
│   └── 📄 test_agent2.py           # Agent 2 tests
│
└── 📁 docs/                        # Additional documentation
    └── 📄 index.md                 # Documentation index
```

## 🗂️ Key Directories

### `/data/` - Data Storage
- **raw/**: Original HTML/Markdown from web scrapers
- **processed/**: Cleaned, chunked documents ready for embedding
- **vector_db/**: ChromaDB SQLite database and embeddings

### `/src/` - Core Application Logic
- **agents/**: The two-agent system (RAG + Timeline)
- **scrapers/**: Web scraping scripts for USCIS, State Dept, universities
- **utils/**: Helper functions for embeddings, chunking, memory
- **evaluation/**: Scripts to measure RAG accuracy and performance

### `/ui/` - User Interface
- **app.py**: Main Streamlit application
- **components/**: Reusable UI components (chat, timeline, checklist)

### `/notebooks/` - Interactive Demos
- Jupyter/Colab notebooks for demos and experimentation

### `/tests/` - Testing
- Unit tests for agents and core functionality

### `/docs/` - Documentation
- Detailed guides and API references

## 📝 Important Files

| File | Purpose |
|------|---------|
| `README.md` | Project overview, features, quick start |
| `SETUP.md` | Detailed installation and configuration |
| `requirements.txt` | Python package dependencies |
| `.env.example` | Template for environment variables |
| `LICENSE` | MIT License terms |
| `CONTRIBUTING.md` | Guidelines for contributors |

## 🔒 Excluded from Git

The following are automatically excluded via `.gitignore`:
- `.env` (contains API keys)
- `data/raw/*` and `data/vector_db/*` (large data files)
- `__pycache__/` and `*.pyc` (Python cache)
- Virtual environment directories

## 🚀 Where to Start

1. **New users**: Read `README.md` → Follow `SETUP.md`
2. **Developers**: Check `src/agents/` for core logic
3. **Contributors**: Read `CONTRIBUTING.md`
4. **Deployers**: See `ui/app.py` and `notebooks/demo.ipynb`
