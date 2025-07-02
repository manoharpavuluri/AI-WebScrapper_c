# Contributing to AI Web Scraper

Thank you for your interest in contributing to the AI Web Scraper project! This document provides guidelines and information for contributors.

## 🤝 How to Contribute

### Types of Contributions

We welcome various types of contributions:

- **Bug Reports**: Report issues you encounter
- **Feature Requests**: Suggest new features or improvements
- **Code Contributions**: Submit pull requests with code changes
- **Documentation**: Improve or add documentation
- **Testing**: Help with testing and quality assurance
- **Examples**: Provide usage examples or tutorials

### Getting Started

1. **Fork the Repository**
   ```bash
   git clone https://github.com/your-username/AI-WebScrapper_c.git
   cd AI-WebScrapper_c
   ```

2. **Create a Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## 📝 Development Guidelines

### Code Style

- Follow **PEP 8** style guidelines
- Use meaningful variable and function names
- Add type hints where appropriate
- Keep functions small and focused
- Add docstrings for all public functions

### Example Code Style

```python
from typing import List, Optional
import streamlit as st


def process_website_content(url: str, chunk_size: Optional[int] = None) -> List[str]:
    """
    Process website content and return chunks.
    
    Args:
        url: The website URL to process
        chunk_size: Size of content chunks (default: 6000)
        
    Returns:
        List of content chunks
        
    Raises:
        ValueError: If URL is invalid
    """
    if not url:
        raise ValueError("URL cannot be empty")
    
    # Your implementation here
    pass
```

### Testing

- Write tests for new features
- Ensure existing tests pass
- Add integration tests for complex workflows
- Test with different Python versions if possible

### Documentation

- Update README.md for user-facing changes
- Add docstrings for new functions
- Update inline comments for complex logic
- Create examples for new features

## 🐛 Bug Reports

When reporting bugs, please include:

1. **Clear Description**: What happened vs. what you expected
2. **Steps to Reproduce**: Detailed steps to recreate the issue
3. **Environment**: OS, Python version, dependency versions
4. **Error Messages**: Full error traceback if applicable
5. **Screenshots**: If relevant to UI issues

### Bug Report Template

```markdown
## Bug Description
Brief description of the issue

## Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

## Expected Behavior
What should happen

## Actual Behavior
What actually happened

## Environment
- OS: [e.g., Windows 10, macOS 12.0]
- Python: [e.g., 3.9.7]
- Dependencies: [output of `pip freeze`]

## Additional Information
Any other relevant information
```

## 💡 Feature Requests

When suggesting features:

1. **Clear Use Case**: Explain why this feature is needed
2. **Implementation Ideas**: Suggest how it might work
3. **Priority**: Indicate if it's a nice-to-have or critical
4. **Examples**: Provide examples of similar features

## 🔄 Pull Request Process

### Before Submitting

1. **Test Your Changes**
   ```bash
   # Run the application
   streamlit run main.py
   
   # Run any existing tests
   python -m pytest tests/
   ```

2. **Check Code Style**
   ```bash
   # Install flake8 if not already installed
   pip install flake8
   
   # Check code style
   flake8 .
   ```

3. **Update Documentation**
   - Update README.md if needed
   - Add docstrings for new functions
   - Update any relevant documentation

### Pull Request Guidelines

1. **Clear Title**: Descriptive title for the PR
2. **Detailed Description**: Explain what and why, not how
3. **Related Issues**: Link to any related issues
4. **Screenshots**: Include screenshots for UI changes
5. **Testing**: Describe how you tested the changes

### PR Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Code refactoring
- [ ] Performance improvement

## Testing
- [ ] Manual testing completed
- [ ] Unit tests added/updated
- [ ] All tests pass

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No breaking changes introduced

## Related Issues
Closes #(issue number)
```

## 🏷️ Commit Messages

Use clear, descriptive commit messages:

### Good Examples
```
feat: add support for batch URL processing
fix: resolve ChromeDriver compatibility issue
docs: update installation instructions
refactor: improve content cleaning algorithm
test: add unit tests for parse module
```

### Commit Message Format
```
type(scope): description

[optional body]

[optional footer]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

## 🚀 Release Process

### Versioning

We follow [Semantic Versioning](https://semver.org/):
- **MAJOR**: Breaking changes
- **MINOR**: New features (backward compatible)
- **PATCH**: Bug fixes (backward compatible)

### Release Checklist

- [ ] All tests pass
- [ ] Documentation is up to date
- [ ] Version number updated
- [ ] Changelog updated
- [ ] Release notes prepared

## 📞 Getting Help

If you need help with contributing:

1. **Check Documentation**: Review README.md and existing docs
2. **Search Issues**: Look for similar issues or discussions
3. **Create Issue**: Open an issue for questions or problems
4. **Join Discussions**: Participate in issue discussions

## 🎯 Areas for Contribution

### High Priority
- Bug fixes and stability improvements
- Performance optimizations
- Security enhancements
- Better error handling

### Medium Priority
- Additional LLM provider support
- Export functionality
- Batch processing features
- UI/UX improvements

### Low Priority
- Documentation improvements
- Code refactoring
- Additional examples
- Testing coverage

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the MIT License.

## 🙏 Recognition

Contributors will be recognized in:
- README.md contributors section
- Release notes
- Project documentation

Thank you for contributing to AI Web Scraper! 🚀 