# PPT Generator 🎯

[![Python](https://img.shields.io/badge/python-3.12-blue.svg)](http## 📝 Technical Notes

### Limitations
- Input text is truncated to ensure token safety with LLMs
- Layout selection uses heuristic matching with fallback options
- Only visible picture shapes are detected for image reuse
- Background images may not be automatically detected

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Thanks to all contributors who have helped shape this project
- Special thanks to the FastAPI and python-pptx communities
- Inspired by the need for automated presentation generation

---

<div align="center">
Made with ❤️ for presentation automation
</div>www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104.0-green.svg)](https://fastapi.tiangolo.com/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Docker](https://img.shields.io/badge/docker-ready-brightgreen.svg)](Dockerfile)

> Transform your text into professional presentations in seconds! 🚀

## 📖 Overview

PPT Generator is an intelligent presentation creation tool that transforms your raw text/Markdown into beautifully formatted PowerPoint presentations while preserving your brand identity. It leverages the power of Large Language Models (LLMs) to understand context and create meaningful slide structures.

### 🌟 Why Choose PPT Generator?

- **Template Preservation**: Maintains your brand's visual identity by respecting template styles
- **Multiple LLM Support**: Works with OpenAI, Anthropic, or Gemini
- **Smart Image Reuse**: Intelligently reuses template images (no AI generation)
- **Privacy-Focused**: Your API keys are never stored or logged
- **Easy Integration**: Simple to deploy and integrate into your workflow

## ✨ Features
- Paste long text/markdown + optional one-line guidance (e.g., “investor pitch deck”).
- Upload a `.pptx` or `.potx` template — styles, colors, fonts, and layouts are respected via placeholders.
- BYO LLM API key: OpenAI / Anthropic / Gemini (keys are not stored or logged).
- Intelligent slide splitting + bulleting via LLM with JSON-structured output.
- Reuse any images discovered in the template/presentation (tastefully placed on some slides).
- Download a brand new `.pptx` generated from your template.

## 🛠️ Technical Stack

### Backend
- **Framework**: FastAPI
- **Presentation Handling**: `python-pptx`
- **Python Version**: 3.12+

### Frontend
- **Technology**: Plain HTML/CSS/JavaScript
- **Design**: Responsive and user-friendly interface
- **Template Support**: .pptx and .potx formats

### AI Providers
- **OpenAI**: Using Responses API for text processing
- **Anthropic**: Integrated with Messages API
- **Google Gemini**: Implementation via `google-genai`

## 🚀 Getting Started

### Prerequisites
- Python 3.12 or higher
- Virtual environment tool
- API key from any supported LLM provider

### Local Development
```bash
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
uvicorn app:app --reload
# open http://localhost:8000
```

## 🌐 Deployment Options

### Cloud Platforms
Deploy easily on any of these platforms:
- **Render**
- **Railway**
- **Fly.io**
- **Heroku**
- **Hugging Face Spaces**

### 🐳 Docker Deployment
Build and run with Docker:
```bash
docker build -t presentify .
docker run -p 8000:8000 presentify
```

### Environment Variables
- `PORT`: Server port (default: 8000)
- `HOST`: Host address (default: 0.0.0.0)
- `DEBUG`: Enable debug mode (default: False)

## 🔒 Privacy & Security
- API keys are accepted in the form and used only for that request in memory.
- Keys are **not stored** and **not logged**. Please self-host for maximum privacy.

## Notes
- Extremely large inputs get truncated to token-safe limits before the LLM call.
- Layout inference is heuristic; we pick the closest “Title + Content” layout and fall back safely.
- Background images might not be detected; we reuse only visible picture shapes.
