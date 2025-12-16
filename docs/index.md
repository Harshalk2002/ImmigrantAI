# Visa Journey Agent - Documentation

## 📚 Table of Contents

1. [Getting Started](#getting-started)
2. [Architecture](#architecture)
3. [API Reference](#api-reference)
4. [Deployment](#deployment)

## Getting Started

### Installation
See [SETUP.md](../SETUP.md) for detailed installation instructions.

### Quick Start
```bash
git clone https://github.com/YOUR-USERNAME/visa-journey-agent.git
cd visa-journey-agent
pip install -r requirements.txt
cp .env.example .env
# Add your OPENAI_API_KEY to .env
streamlit run ui/app.py
```

## Architecture

### System Components

#### Agent 1: RAG Engine
- **Purpose**: Retrieve and summarize immigration policies
- **Input**: User questions about F-1 visa regulations
- **Output**: Structured policy summaries with risk ratings
- **Technology**: ChromaDB + OpenAI GPT-4o-mini

#### Agent 2: Timeline Engine
- **Purpose**: Generate personalized compliance checklists
- **Input**: Student profile (start date, graduation date)
- **Output**: CPT/OPT timelines and action items
- **Technology**: Python date calculations + policy integration

### Data Flow
```
User Query → Agent 1 (Retrieve Policy) → LLM (Summarize) → Agent 2 (Generate Timeline) → UI Display
```

## API Reference

### Core Functions

#### `retrieve_policy_chunks(query: str, max_results: int = 5)`
Retrieve relevant policy chunks from vector database.

**Parameters:**
- `query`: Search query string
- `max_results`: Number of chunks to retrieve (default: 5)

**Returns:** List of document chunks with metadata

#### `generate_timeline(profile: dict)`
Generate personalized CPT/OPT timeline.

**Parameters:**
- `profile`: Dictionary containing `program_start` and `expected_graduation`

**Returns:** Dictionary with timeline milestones and checklist

## Deployment

### Local Deployment
```bash
streamlit run ui/app.py
```

### Cloud Deployment (Streamlit Cloud)
1. Push code to GitHub
2. Connect repository at https://share.streamlit.io
3. Add secrets (OPENAI_API_KEY) in Streamlit dashboard
4. Deploy

### Google Colab Deployment
1. Open `notebooks/demo.ipynb`
2. Add API key to Colab secrets
3. Run all cells
4. Access via ngrok tunnel

## Contributing
See [CONTRIBUTING.md](../CONTRIBUTING.md) for contribution guidelines.
