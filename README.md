<<<<<<< HEAD
# 🌍 Visa Journey Agent

An AI-powered compliance assistant for F-1 visa holders, providing personalized immigration guidance through intelligent document retrieval and multi-agent orchestration.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Streamlit](https://img.shields.io/badge/streamlit-1.28+-red.svg)

## 📋 Overview

The Visa Journey Agent is a sophisticated RAG-based (Retrieval-Augmented Generation) system designed to simplify F-1 visa compliance for international students. By combining automated policy extraction with personalized timeline generation, the system transforms complex immigration regulations into actionable guidance.

### ✨ Key Features

- **🤖 Dual-Agent Architecture**
  - **Agent 1**: Policy retrieval and summarization engine using RAG
  - **Agent 2**: Timeline computation and checklist generation

- **📚 Comprehensive Knowledge Base**
  - 3,243 document chunks from USCIS, State Department, and university sources
  - Semantic search via ChromaDB vector database
  - Real-time policy updates and interpretations

- **⏰ Personalized Compliance Tracking**
  - Automated CPT/OPT timeline calculation
  - Custom checklists based on program milestones
  - Risk assessment and deadline notifications

- **💬 Interactive Chat Interface**
  - Natural language Q&A about visa regulations
  - Short-term and long-term memory integration
  - Streamlit-powered UI with session persistence

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     User Interface (Streamlit)               │
│  ┌──────────────────────┐  ┌──────────────────────────┐    │
│  │   Chat Assistant     │  │  Timeline & Checklist    │    │
│  │  (Q&A + Memory)      │  │     (Personalized)       │    │
│  └──────────────────────┘  └──────────────────────────┘    │
└────────────────┬────────────────────────┬───────────────────┘
                 │                        │
        ┌────────▼─────────┐    ┌────────▼──────────┐
        │    Agent 1       │    │     Agent 2       │
        │  RAG Engine      │◄───┤  Timeline Engine  │
        │  - Retrieval     │    │  - Calculation    │
        │  - Summarization │    │  - Integration    │
        └────────┬─────────┘    └───────────────────┘
                 │
        ┌────────▼─────────┐
        │   ChromaDB       │
        │  Vector Store    │
        │  (3,243 chunks)  │
        └──────────────────┘
```

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- OpenAI API key
- Google Drive account (optional, for persistent storage)

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/visa-journey-agent.git
cd visa-journey-agent
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Set up environment variables
```bash
cp .env.example .env
# Edit .env and add your OPENAI_API_KEY
```

4. Download the vector database
```bash
# The ChromaDB instance will be automatically initialized on first run
# Or mount your Google Drive if using the Colab version
```

5. Run the application
```bash
streamlit run app.py
```

## 📂 Project Structure

```
visa-journey-agent/
├── data/
│   ├── raw/                    # Raw scraped HTML/Markdown
│   ├── processed/              # Cleaned and chunked documents
│   └── vector_db/              # ChromaDB persistent storage
├── src/
│   ├── agents/
│   │   ├── agent1_rag.py      # RAG-based Q&A agent
│   │   └── agent2_timeline.py # Timeline generation agent
│   ├── scrapers/
│   │   ├── uscis_scraper.py   # USCIS policy scraper
│   │   ├── travel_scraper.py  # travel.state.gov scraper
│   │   └── isss_scraper.py    # University ISSS scraper
│   ├── utils/
│   │   ├── embeddings.py      # Embedding generation
│   │   ├── chunking.py        # Document chunking
│   │   └── memory.py          # Session memory management
│   └── evaluation/
│       └── evaluate_rag.py    # RAG evaluation metrics
├── ui/
│   ├── app.py                 # Main Streamlit application
│   └── components/            # Reusable UI components
├── notebooks/
│   └── demo.ipynb             # Colab demo notebook
├── tests/
│   ├── test_agent1.py
│   └── test_agent2.py
├── requirements.txt
├── .env.example
├── LICENSE
└── README.md
```

## 🔧 Technology Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Vector Database** | ChromaDB | Efficient semantic search over 3K+ documents |
| **Embeddings** | sentence-transformers/all-MiniLM-L6-v2 | Fast 384-dim embeddings for QA tasks |
| **LLM** | OpenAI GPT-4o-mini | Cost-effective policy summarization |
| **Chunking** | LangChain RecursiveCharacterTextSplitter | Context-preserving document segmentation |
| **UI Framework** | Streamlit | Rapid prototyping and deployment |
| **Web Scraping** | BeautifulSoup + Requests | Policy document extraction |

## 📊 Evaluation Results

The system was evaluated using a keyword recall metric across 4 representative immigration queries:

| Query | Recall | Interpretation |
|-------|--------|----------------|
| H-1B requirements | 1.0 | Perfect - all required policy components captured |
| H-1B filing timeline | 1.0 | Perfect - complete timeline information |
| Specialty occupation criteria | 0.5 | Partial - one of two expected keywords present |
| CPT → OPT eligibility | 1.0 | Perfect - full-time CPT impact accurately retrieved |

**Overall Performance**: 87.5% average recall across test queries, demonstrating strong retrieval accuracy and grounded summarization.

## 💡 Usage Examples

### Basic Q&A
```python
# Ask about CPT eligibility
"When can I apply for CPT?"

# Response includes:
# - Eligibility timeline (after 1 academic year)
# - Required documents
# - Application process
# - Risk warnings
```

### Timeline Generation
```python
# Provide your profile
profile = {
    "program_start": "2024-08-15",
    "expected_graduation": "2025-12-15"
}

# System automatically generates:
# - CPT eligibility date: 2025-08-15
# - OPT application window: 2025-09-15 to 2025-12-15
# - Personalized checklist with deadlines
```

## 🔮 Future Enhancements

- [ ] **Document Upload**: Support for I-20, job offer PDFs
- [ ] **Calendar Integration**: Google Calendar API for deadline notifications
- [ ] **Expanded Visa Types**: J-1 scholar and permanent residency workflows
- [ ] **Real-time Updates**: Automated USCIS policy monitoring
- [ ] **Mobile App**: iOS/Android native applications
- [ ] **Multi-language Support**: Spanish, Chinese, Hindi translations

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This tool provides informational guidance based on publicly available immigration policies. It is **not a substitute for professional legal advice**. Always consult with a qualified immigration attorney or your institution's International Student Services office for official guidance.

## 📧 Contact

For questions or feedback, please open an issue on GitHub.

## 🙏 Acknowledgments

- USCIS and Department of State for public policy documentation
- Georgia State University ISSS for institutional guidance
- OpenAI for GPT-4 API access
- Anthropic for Claude development assistance

---

**Built with ❤️ for international students navigating the complexities of U.S. immigration**
=======
# ImmigrantAI
>>>>>>> 578d6e187426b733091ecd9d90637f851cb29a15
