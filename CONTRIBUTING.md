# Contributing to JCROBOT Komodo Series

Thank you for your interest in contributing to the JCROBOT Komodo Series project! We welcome contributions from the community, whether it's bug reports, feature suggestions, documentation improvements, or code enhancements.

## 📋 Code of Conduct

Please be respectful and constructive in all interactions. We are committed to providing a welcoming and inclusive environment for all contributors.

## 🐛 Reporting Bugs

If you find a bug, please create an issue with:

1. **Clear title** describing the problem
2. **Detailed description** of the issue
3. **Steps to reproduce** the bug
4. **Expected vs actual behavior**
5. **Your environment** (OS, hardware model, firmware version)
6. **Screenshots or attachments** if applicable

Example:
```
Title: Komodo-01 wheel calibration fails on first boot

Description: When first powering on Komodo-01, the wheel calibration process times out...

Steps to Reproduce:
1. Power on Komodo-01
2. Wait for initialization
3. Observe error message

Environment:
- Model: Komodo-01
- Firmware: v1.2.3
```

## 💡 Feature Requests

We'd love to hear your ideas! Submit feature requests as GitHub Issues with:

1. **Clear title** of the feature
2. **Detailed description** and use case
3. **Why you need it** and how it benefits users
4. **Potential implementation approach** (if you have ideas)

## 📚 Documentation Improvements

Documentation improvements are always welcome:

- Fix typos or unclear wording
- Add missing information
- Improve formatting or structure
- Add examples or diagrams
- Translate to other languages

To contribute documentation:

1. Fork the repository
2. Make your changes in a new branch: `git checkout -b docs/your-improvement`
3. Commit with clear messages: `git commit -m "docs: improve assembly guide clarity"`
4. Submit a Pull Request

## 🔧 Code Contributions

### Getting Started

1. **Fork** the repository
2. **Clone** your fork: `git clone https://github.com/YOUR-USERNAME/robot-chassis-Komodo.git`
3. **Create a branch** for your feature: `git checkout -b feature/your-feature-name`
4. **Make changes** following our coding standards (see below)
5. **Test** your changes thoroughly
6. **Commit** with clear messages
7. **Push** to your fork
8. **Submit a Pull Request** to the main repository

### Coding Standards

#### File Organization
- Place firmware code in `/software/firmware/`
- Place drivers in `/software/drivers/`
- Place examples in `/software/examples/`
- Place hardware files in `/hardware/`

#### Naming Conventions
- Use descriptive, lowercase names for files: `motor_controller.py`, `wheel_calibration.cpp`
- Use snake_case for variables and functions
- Use PascalCase for classes

#### Comments & Documentation
- Add comments for complex logic
- Include docstrings for functions and classes
- Update README if adding new features

#### Testing
- Write tests for new functionality
- Ensure existing tests still pass
- Test on multiple Komodo variants when applicable

### Commit Messages

Follow this format:
```
[type]: brief description

Optional detailed explanation of changes.

Fixes #123
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Examples:
```
feat: add wheel speed feedback sensor support
fix: resolve motor calibration timeout on Komodo-02
docs: improve getting started guide
test: add unit tests for motor controller
```

## 📝 Pull Request Process

1. **Ensure your PR** has a clear title and description
2. **Link related issues** (use "Fixes #123" or "Relates to #456")
3. **Fill out the PR template** completely
4. **Keep PRs focused** - one feature or fix per PR
5. **Update documentation** if needed
6. **Respond to reviews** promptly and professionally

### PR Checklist
- [ ] Code follows project style guidelines
- [ ] Changes are tested
- [ ] Documentation is updated
- [ ] Commit messages are clear
- [ ] No new warnings are introduced

## 🎨 3D Model & Hardware Contributions

### Adding New Models or Variants

1. Prepare files in multiple formats:
   - .STL (for 3D printing/viewing)
   - .STEP (for CAD)
   - .OBJ (for web viewers)

2. Place in appropriate directory: `/3d-models/Komodo-XX/`

3. Create a `README.md` in the model directory describing:
   - Model specifications
   - Assembly notes
   - Part list
   - Measurement units and scale

4. Add high-quality preview images

5. Submit a PR with clear description

## 🔍 Review Process

- All contributions will be reviewed by maintainers
- We may request changes or improvements
- Once approved, your contribution will be merged
- You'll be added to our contributors list

## 📖 Style Guide

### Documentation
- Use clear, simple language
- Include examples and diagrams
- Keep sentences concise
- Use headers to organize content
- Add links to related sections

### Code Comments
```python
# Good - explains WHY, not WHAT
# Calibration runs twice to ensure stability after power cycle
calibrate()
calibrate()

# Avoid - obvious from code
# Run calibration
calibrate()
```

## ✅ Recognition

All contributors will be recognized in:
- [Contributors](./CONTRIBUTORS.md) file
- GitHub's automatic contributor graph
- Release notes (for significant contributions)

## 📞 Questions?

- Check existing issues for similar questions
- Ask in [GitHub Discussions](../../discussions)
- Review related documentation
- Contact: support@jcrobot.com

## 📜 Legal

By contributing to this project, you agree that:
- Your contributions will be licensed under the same MIT License
- You have the right to submit the work
- You grant JCROBOT permission to use and modify your contribution

---

**Thank you for helping make JCROBOT Komodo Series better!** 🚀
