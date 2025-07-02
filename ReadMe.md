# AI Web Scraper

A sophisticated web scraping application that combines automated web scraping with AI-powered content parsing using Ollama LLM. This tool provides a user-friendly Streamlit interface for extracting and analyzing web content with intelligent data extraction capabilities.

## 🚀 Features

- **Automated Web Scraping**: Uses Selenium WebDriver for robust web scraping
- **AI-Powered Content Parsing**: Leverages Ollama LLM for intelligent content extraction
- **Captcha Handling**: Integrated BrightData proxy service for bypassing captchas
- **Web Interface**: Clean Streamlit-based user interface
- **Content Cleaning**: Automatic removal of scripts, styles, and formatting
- **Chunked Processing**: Handles large content by splitting into manageable chunks
- **Real-time Processing**: Live scraping and parsing with progress indicators

## 🛠️ Technology Stack

### Core Technologies
- **Streamlit** (v1.28.0+) - Web application framework
- **Selenium** (v4.15.0+) - Web automation and scraping
- **BeautifulSoup4** (v4.12.0+) - HTML parsing and content extraction
- **LangChain** (v0.1.0+) - LLM integration framework
- **Ollama** - Local LLM for content parsing

### Additional Dependencies
- **NumPy** (v1.24.0+) - Numerical computing
- **Requests** (v2.31.0+) - HTTP library
- **LXML** (v4.9.0+) - XML/HTML processing

## 📋 Prerequisites

### System Requirements
- Python 3.8 or higher
- Chrome browser installed
- Internet connection
- Ollama installed and running locally

### External Services
- **BrightData** (optional) - For captcha bypassing and proxy services
- **Ollama** - Local LLM service (llama3 model recommended)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd AI-WebScrapper_c
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Install Ollama** (if not already installed)
   ```bash
   # Follow instructions at https://ollama.ai/
   ollama pull llama3
   ```

4. **Set up BrightData** (optional)
   - Sign up for BrightData account
   - Update credentials in `scrape.py` if using proxy services

## 🎯 Usage

### Starting the Application
```bash
streamlit run main.py
```

### Using the Application

1. **Enter Website URL**: Input the target website URL in the text field
2. **Scrape Content**: Click "Scrape Site" to extract website content
3. **Review Content**: View the extracted DOM content in the expandable section
4. **Define Parsing Criteria**: Describe what information you want to extract
5. **Parse Content**: Click "Parse Content" to get AI-processed results

### Example Use Cases
- Extract product information from e-commerce sites
- Gather news articles and headlines
- Collect contact information from business directories
- Extract pricing data from competitor websites
- Gather research data from academic or news websites

## 🏗️ Architecture

### Core Components

#### 1. **Web Scraping Module** (`scrape.py`)
- **`scrape_website(url)`**: Main scraping function using Selenium
- **`extract_body_content(html)`**: Extracts body content from HTML
- **`clean_body_content(content)`**: Removes scripts, styles, and formats text
- **`split_dom_content(content, max_length)`**: Splits large content into chunks

#### 2. **AI Parsing Module** (`parse.py`)
- **`parse_with_ollama(chunks, description)`**: Processes content with Ollama LLM
- Uses LangChain for prompt management and LLM integration
- Implements chunked processing for large content

#### 3. **Web Interface** (`main.py`)
- Streamlit-based user interface
- Session state management for content persistence
- Real-time progress indicators

### Data Flow
```
URL Input → Web Scraping → Content Extraction → Content Cleaning → 
Chunking → AI Parsing → Results Display
```

## ⚙️ Configuration

### BrightData Configuration
Update the following variables in `scrape.py`:
```python
AUTH = 'YOUR_USERNAME:YOUR_PASSWORD'
SBR_WEBDRIVER = 'YOUR_BRIGHTDATA_ENDPOINT'
```

### Ollama Configuration
- Ensure Ollama is running locally
- Default model: `llama3`
- Can be modified in `parse.py`:
```python
model = OllamaLLM(model="your-preferred-model")
```

### Content Processing Settings
- Default chunk size: 6000 characters
- Adjustable in `split_dom_content()` function

## 🔧 Troubleshooting

### Common Issues

1. **ChromeDriver Issues**
   - Ensure Chrome browser is installed
   - Download appropriate ChromeDriver version
   - Update path in `scrape.py` if using local ChromeDriver

2. **Ollama Connection Issues**
   - Verify Ollama is running: `ollama list`
   - Check if llama3 model is available: `ollama pull llama3`
   - Ensure Ollama service is accessible on default port

3. **BrightData Connection Issues**
   - Verify credentials are correct
   - Check account status and quota
   - Ensure proxy endpoint is accessible

4. **Memory Issues with Large Content**
   - Reduce chunk size in `split_dom_content()`
   - Process smaller websites
   - Monitor system memory usage

## 📊 Performance Considerations

### Optimization Tips
- Use appropriate chunk sizes for your content
- Implement caching for frequently accessed websites
- Consider rate limiting for large-scale scraping
- Monitor memory usage with large content processing

### Scalability
- The application can handle multiple concurrent users
- Consider implementing database storage for large datasets
- Add queue management for batch processing

## 🔒 Security Considerations

### Best Practices
- Use HTTPS URLs when possible
- Implement rate limiting to avoid being blocked
- Respect robots.txt files
- Use proxy services responsibly
- Secure API credentials and configuration

### Data Privacy
- Ensure compliance with website terms of service
- Implement data retention policies
- Secure storage of scraped content
- Respect user privacy and data protection laws

## 🧪 Testing

### Manual Testing
1. Test with various website types
2. Verify content extraction accuracy
3. Test AI parsing with different descriptions
4. Validate error handling

### Automated Testing (Future Enhancement)
- Unit tests for core functions
- Integration tests for end-to-end workflow
- Performance benchmarking
- Error scenario testing

## 📈 Future Improvements

### Enhanced AI Capabilities
- **Multi-Model Support**: Integration with additional LLM providers (OpenAI, Anthropic, etc.)
- **Custom Model Training**: Fine-tune models for specific domains or use cases
- **Advanced Prompt Engineering**: Implement more sophisticated prompting strategies
- **Semantic Search**: Add vector-based search capabilities for better content understanding

### User Experience Enhancements
- **Dashboard Analytics**: Add visualization of scraping statistics and trends
- **Batch Processing**: Support for processing multiple URLs simultaneously
- **Scheduled Scraping**: Implement cron-based automated scraping
- **Export Functionality**: Add support for exporting results in various formats (CSV, JSON, Excel)
- **Template Library**: Pre-built parsing templates for common use cases

### Technical Improvements
- **Database Integration**: Add persistent storage for scraped data and results
- **API Endpoints**: Create RESTful API for programmatic access
- **Microservices Architecture**: Split into separate services for better scalability
- **Containerization**: Docker support for easy deployment
- **Cloud Deployment**: AWS, Azure, or GCP deployment options

### Advanced Features
- **Dynamic Content Handling**: Better support for JavaScript-heavy websites
- **Image and Media Extraction**: Extract and process images, videos, and other media
- **Multi-language Support**: Internationalization for global users
- **Real-time Monitoring**: Live monitoring of scraping processes
- **Advanced Error Recovery**: Intelligent retry mechanisms and error handling

### Performance Optimizations
- **Caching Layer**: Implement Redis or similar for caching frequently accessed content
- **Async Processing**: Convert to async/await for better performance
- **Load Balancing**: Distribute scraping load across multiple instances
- **CDN Integration**: Optimize content delivery for global users

### Compliance and Ethics
- **Robots.txt Compliance**: Automatic robots.txt checking and compliance
- **Rate Limiting**: Intelligent rate limiting based on website policies
- **Ethical Guidelines**: Built-in ethical scraping guidelines and warnings
- **Audit Trail**: Comprehensive logging for compliance and debugging

## 🤝 Contributing

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Code Standards
- Follow PEP 8 style guidelines
- Add docstrings for all functions
- Include type hints where appropriate
- Write comprehensive commit messages

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **BrightData** for proxy and captcha solving services
- **Ollama** for local LLM capabilities
- **Streamlit** for the web interface framework
- **Selenium** for web automation capabilities
- **BeautifulSoup** for HTML parsing

## 📞 Support

For issues, questions, or contributions:
- Create an issue in the repository
- Check the troubleshooting section
- Review the documentation

---

**Note**: This tool is designed for educational and research purposes. Please ensure compliance with website terms of service and applicable laws when using this application.
