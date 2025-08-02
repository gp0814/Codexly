# Codexly 🚀

**The intelligent coding problem solver that sees, thinks, and codes.**

Codexly extracts coding problems from images using OCR, generates optimal Python solutions using AI, and executes them in a secure sandbox environment - all in one seamless workflow.

## Features

- 🖼️ **Image OCR**: Extract text from images containing coding problems
- 🤖 **AI-Powered Code Generation**: Generate optimal Python solutions using Groq's LLaMA model
- ⚡ **Code Execution**: Run generated code in a secure E2B sandbox environment
- 🌐 **Web Interface**: User-friendly Flask web application
- 📝 **Text Input**: Support for both image upload and direct text input
- 🔍 **Error Analysis**: Intelligent error explanation and debugging

## Tech Stack

- **Backend**: Flask (Python web framework)
- **OCR**: Tesseract OCR with pytesseract
- **AI Model**: Groq LLaMA-3.3-70b-versatile
- **Code Execution**: E2B Code Interpreter Sandbox
- **Image Processing**: PIL (Python Imaging Library)
- **Environment**: dotenv for configuration management

## Prerequisites

### System Requirements
- Python 3.8+
- Tesseract OCR installed on your system

### Tesseract Installation

**Windows:**
1. Download Tesseract from [GitHub releases](https://github.com/UB-Mannheim/tesseract/wiki)
2. Install and note the installation path (typically `C:\Program Files\Tesseract-OCR\tesseract.exe`)

**macOS:**
```bash
brew install tesseract
```

**Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install tesseract-ocr
```

## Installation

1. **Clone the repository:**
```bash
git clone <repository-url>
cd codexly
```

2. **Create a virtual environment:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies:**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables:**
Create a `.env` file in the project root:
```env
GROQ_API_KEY=your_groq_api_key_here
E2B_API_KEY=your_e2b_api_key_here
```

## API Keys Setup

### Groq API Key
1. Visit [Groq Console](https://console.groq.com/)
2. Sign up/Login and create an API key
3. Add it to your `.env` file

### E2B API Key
1. Visit [E2B Platform](https://e2b.dev/)
2. Sign up/Login and generate an API key
3. Add it to your `.env` file

## Usage

### Web Application

1. **Start the Flask server:**
```bash
python app.py
```

2. **Open your browser and navigate to:**
```
http://localhost:5000
```

3. **Use the application:**
   - Upload an image containing a coding problem, OR
   - Enter a coding problem directly in the text area
   - Click submit to get AI-generated solution and execution results

### Command Line Interface

1. **Place your image in the project directory:**
   - Name it `test_question.png` or modify the path in `main.py`

2. **Run the CLI version:**
```bash
python main.py
```

## Project Structure

```
codexly/
├── app.py                 # Flask web application
├── main.py               # Command-line interface
├── requirements.txt      # Python dependencies
├── .env                  # Environment variables (create this)
├── .env.example         # Environment variables template
├── templates/           # HTML templates
│   └── index.html      # Main web interface
├── static/             # Static files (CSS, JS, images)
└── README.md          # This file
```

## How Codexly Works

1. **📸 Image Processing**: Tesseract OCR extracts text from uploaded images
2. **🔍 Problem Analysis**: Extracted text is analyzed to identify the coding problem
3. **🧠 Code Generation**: Groq's LLaMA model generates optimized Python solution
4. **⚡ Code Execution**: E2B sandbox safely executes the generated code
5. **📊 Result Display**: Shows the solution code and execution output/errors

## Configuration

### Tesseract Path (Windows)
If Tesseract is installed in a different location, update the path in both `app.py` and `main.py`:
```python
pytesseract.pytesseract.tesseract_cmd = r"YOUR_TESSERACT_PATH"
```

### Model Configuration
To use a different Groq model, modify the model ID in the Agent initialization:
```python
code_agent = Agent(
    model=Groq(id="your-preferred-model", api_key=GROQ_API_KEY),
    markdown=True
)
```

## Troubleshooting

### Common Issues

**OCR not working:**
- Ensure Tesseract is properly installed
- Check the Tesseract path configuration
- Verify image quality and text clarity

**API Errors:**
- Verify API keys are correctly set in `.env`
- Check API rate limits and quotas
- Ensure internet connectivity

**Code Execution Fails:**
- Check E2B API key validity
- Verify sandbox timeout settings
- Review generated code for syntax errors

### Error Messages

- `❌ No text detected in image`: Image quality too low or no text present
- `❌ No valid code block found`: AI didn't generate properly formatted code
- `⚠️ Execution Error`: Generated code has runtime errors

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) for text extraction
- [Groq](https://groq.com/) for AI-powered code generation
- [E2B](https://e2b.dev/) for secure code execution environment
- [Flask](https://flask.palletsprojects.com/) for the web framework

## Support

If you encounter any issues or have questions, please:
1. Check the troubleshooting section above
2. Search existing issues in the repository
3. Create a new issue with detailed information about the problem

---

**Made with ❤️ by the Codexly Team | Happy Coding! 🚀**
