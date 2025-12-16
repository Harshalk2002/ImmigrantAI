# Contributing to Visa Journey Agent

Thank you for your interest in contributing! This document provides guidelines for contributing to the project.

## 🚀 Getting Started

1. Fork the repository
2. Clone your fork: `git clone https://github.com/YOUR-USERNAME/visa-journey-agent.git`
3. Create a branch: `git checkout -b feature/your-feature-name`
4. Make your changes
5. Test thoroughly
6. Commit with clear messages
7. Push and create a Pull Request

## 📋 Development Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Add your OPENAI_API_KEY to .env

# Run tests
pytest tests/
```

## 🎯 What to Contribute

### High Priority
- Additional data sources (more universities, countries)
- Improved evaluation metrics
- Mobile-friendly UI enhancements
- Performance optimizations

### Medium Priority
- Additional visa types (J-1, H-1B transition workflows)
- Multi-language support
- Calendar integrations
- Enhanced error handling

### Good First Issues
Look for issues tagged with `good-first-issue` in the GitHub Issues tab.

## 💻 Code Standards

- Follow PEP 8 style guide for Python code
- Add docstrings to all functions and classes
- Include type hints where appropriate
- Write unit tests for new features
- Keep functions focused and modular

### Example Code Style

```python
from typing import List, Dict

def retrieve_policy_chunks(query: str, max_results: int = 5) -> List[Dict[str, str]]:
    """
    Retrieve relevant policy chunks from the vector database.
    
    Args:
        query: The user's question or search term
        max_results: Maximum number of chunks to retrieve
        
    Returns:
        List of dictionaries containing chunk text and metadata
    """
    # Implementation here
    pass
```

## 🧪 Testing

- Write tests for all new features
- Ensure existing tests pass: `pytest tests/`
- Aim for >80% code coverage
- Test edge cases and error conditions

## 📝 Documentation

- Update README.md if adding major features
- Add docstrings to new functions
- Include usage examples for new features
- Update architecture diagrams if needed

## 🐛 Bug Reports

When reporting bugs, include:
- Clear description of the issue
- Steps to reproduce
- Expected vs actual behavior
- Environment details (OS, Python version)
- Relevant error messages or logs

## 💡 Feature Requests

When suggesting features:
- Explain the use case
- Describe expected behavior
- Consider implementation complexity
- Note any potential challenges

## 📜 Commit Message Guidelines

Follow conventional commits format:

```
type(scope): brief description

Longer description if needed

Fixes #123
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Examples:
- `feat(agent1): add support for H-1B cap-gap queries`
- `fix(scraper): handle timeout errors in USCIS scraper`
- `docs(readme): add installation troubleshooting section`

## 🔍 Code Review Process

1. Maintainers will review your PR within 3-5 days
2. Address any requested changes
3. Once approved, your PR will be merged
4. Your contribution will be credited in the release notes

## ⚖️ Legal

By contributing, you agree that your contributions will be licensed under the MIT License.

## 🙏 Thank You!

Every contribution makes this project better for international students worldwide. We appreciate your help!
