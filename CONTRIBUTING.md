# Contributing to WAFNinja 🥷

First off, thank you for considering contributing to WAFNinja! It's people like you that make WAFNinja such a great tool.

## 🌟 Ways to Contribute

### 🐛 Reporting Bugs

Before creating bug reports, please check the existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples**
- **Describe the behavior you observed and what you expected**
- **Include screenshots if possible**
- **Include your environment details** (OS, BurpSuite version, Python version)

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Explain why this enhancement would be useful**
- **List any similar features in other tools**

### 🔧 Pull Requests

1. **Fork the repo** and create your branch from `main`
2. **Make your changes** with clear, commented code
3. **Test your changes** thoroughly
4. **Update documentation** if needed
5. **Follow the code style** of the project
6. **Write a clear commit message**

## 🎯 Development Process

### Setting Up Development Environment

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/WAFNinja.git
cd WAFNinja

# Create a branch
git checkout -b feature/my-new-feature

# Make your changes
# Test in BurpSuite

# Commit your changes
git add .
git commit -m "Add amazing new feature"

# Push to your fork
git push origin feature/my-new-feature

# Open a Pull Request
```

### Code Style Guidelines

- **Python 2.7 compatible** (for Jython support)
- **Clear variable names** and comments
- **Docstrings** for all classes and methods
- **Error handling** with try/except blocks
- **Logging** with print statements for debugging

### Adding New Bypass Techniques

```python
# 1. Add technique to _load_bypass_techniques()
{'name': 'My New Technique', 'complexity': 3}

# 2. Implement technique logic in _apply_technique_to_request()
if technique['name'] == 'My New Technique':
    # Your implementation here
    pass

# 3. Update documentation
# - README.md
# - FEATURES_ADDED.txt
# - Docstring in WAFNinja.py

# 4. Test thoroughly
# - Test against multiple WAFs
# - Verify ML database recording
# - Check performance impact
```

### Adding New WAF Signatures

```python
# Add to _load_waf_signatures() method
'New WAF': {
    'headers': ['x-new-waf-header'],
    'body': ['New WAF Blocked'],
    'cookies': ['new_waf_cookie']
}
```

## 🧪 Testing

### Manual Testing Checklist

- [ ] Extension loads without errors
- [ ] All UI tabs display correctly
- [ ] Bypass techniques work as expected
- [ ] ML database records data correctly
- [ ] Export functionality works
- [ ] No memory leaks during extended use
- [ ] Performance meets expectations

### Test Scenarios

1. **Basic Functionality**
   - Load extension
   - Enable auto bypass
   - Send requests through proxy
   - Verify bypass attempts

2. **ML Database**
   - Verify database creation
   - Check data recording
   - Test export functionality
   - Verify statistics display

3. **Performance**
   - Test with caching enabled/disabled
   - Verify parallel processing
   - Check memory usage
   - Measure response times

## 📝 Documentation

When adding features, update:

- **README.md** - Main documentation
- **FEATURES_ADDED.txt** - Feature details
- **ML_DATABASE_INFO.txt** - If ML-related
- **Docstrings** - In-code documentation
- **Comments** - Explain complex logic

## 🎨 Commit Message Guidelines

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting)
- **refactor**: Code refactoring
- **perf**: Performance improvements
- **test**: Adding tests
- **chore**: Maintenance tasks

### Examples

```bash
feat(bypass): Add GraphQL bypass technique

Implemented new bypass technique specifically for GraphQL endpoints
that uses query batching to evade WAF detection.

Closes #123

---

fix(ml): Fix database connection leak

Fixed issue where database connections were not being properly closed,
causing memory leaks during extended use.

Fixes #456

---

docs(readme): Update installation instructions

Added more detailed steps for Jython configuration and
troubleshooting common installation issues.
```

## 🏆 Recognition

Contributors will be:

- Listed in the **Hall of Fame** in README.md
- Mentioned in release notes
- Credited in commit history
- Appreciated by the community! 🎉

## 📜 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inspiring community for all.

### Our Standards

**Positive behavior includes:**
- Being respectful and inclusive
- Gracefully accepting constructive criticism
- Focusing on what's best for the community
- Showing empathy towards others

**Unacceptable behavior includes:**
- Harassment or discriminatory language
- Trolling or insulting comments
- Publishing others' private information
- Any conduct inappropriate in a professional setting

## 🤔 Questions?

Feel free to:

- Open an issue for questions
- Email: me@krishnendu.com
- Start a discussion on GitHub

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for contributing to WAFNinja! 🥷**

Together, we're building the best WAF bypass tool in the world! 🚀
