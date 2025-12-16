# Setup Guide

## Quick Setup (5 minutes)

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR-USERNAME/visa-journey-agent.git
cd visa-journey-agent
```

### 2. Create Virtual Environment
```bash
# Using venv (recommended)
python -m venv venv

# Activate on macOS/Linux
source venv/bin/activate

# Activate on Windows
venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment
```bash
# Copy example environment file
cp .env.example .env

# Edit .env and add your OpenAI API key
# You can get an API key at: https://platform.openai.com/api-keys
nano .env  # or use any text editor
```

### 5. Initialize Vector Database
```bash
# The vector database will be automatically initialized on first run
# Or you can run the scraper to populate it:
python src/scrapers/uscis_scraper.py
```

### 6. Run the Application
```bash
streamlit run ui/app.py
```

The app will open in your browser at `http://localhost:8501`

## Google Colab Setup

For cloud deployment without local setup:

1. Open `notebooks/demo.ipynb` in Google Colab
2. Add your OpenAI API key to Colab secrets
3. Run all cells
4. Access via ngrok URL

## Troubleshooting

### ImportError: No module named 'chromadb'
```bash
pip install --upgrade chromadb
```

### OpenAI API Key Error
- Ensure `.env` file exists in project root
- Verify API key is valid at https://platform.openai.com/api-keys
- Check that `.env` contains: `OPENAI_API_KEY=sk-...`

### ChromaDB Permission Error
```bash
# On Linux/Mac, ensure proper permissions:
chmod -R 755 data/vector_db/
```

### Port Already in Use
```bash
# Change Streamlit port:
streamlit run ui/app.py --server.port 8502
```

## Development Setup

For contributing or advanced development:

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
pytest tests/ -v

# Run linting
flake8 src/ ui/
black src/ ui/ --check

# Type checking
mypy src/
```

## Docker Setup (Optional)

```bash
# Build image
docker build -t visa-journey-agent .

# Run container
docker run -p 8501:8501 --env-file .env visa-journey-agent
```

## Need Help?

- Check [Common Issues](docs/common-issues.md)
- Open an [Issue](https://github.com/YOUR-USERNAME/visa-journey-agent/issues)
- Read the full [Documentation](docs/)
