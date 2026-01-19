# Contributing to Real State

Thank you for your interest in contributing to the Real State project! This document provides guidelines and instructions for contributing.

## Code of Conduct

Please be respectful and constructive in all interactions with other contributors.

## How to Contribute

### Reporting Bugs

If you find a bug, please create an issue with:
- Clear description of the bug
- Steps to reproduce
- Expected behavior
- Actual behavior
- Screenshots (if applicable)

### Suggesting Features

Feature suggestions are welcome! Please include:
- Clear description of the feature
- Use cases and benefits
- Possible implementation approach

### Creating Pull Requests

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/YourFeature`
3. Make your changes
4. Commit with clear messages: `git commit -m 'Add YourFeature'`
5. Push to your fork: `git push origin feature/YourFeature`
6. Open a Pull Request with detailed description

## Development Guidelines

### Code Style
- Use ES6+ syntax
- Follow React best practices
- Use meaningful variable and function names
- Add comments for complex logic

### Component Structure
```
ComponentName/
├── ComponentName.js
├── ComponentName.css
└── index.js
```

### Naming Conventions
- Components: PascalCase (e.g., `Header`, `PropertyCard`)
- Functions/Variables: camelCase (e.g., `handleClick`, `propertyList`)
- CSS Classes: kebab-case (e.g., `.property-card`, `.header-nav`)

### Testing
- Write tests for new features
- Run `npm test` before submitting PR
- Ensure all tests pass

## Project Setup

1. Clone your fork
2. Install dependencies: `npm install`
3. Start dev server: `npm start`
4. Make your changes
5. Test locally before pushing

## Questions?

Feel free to open an issue or contact the maintainers.

Thank you for contributing! 🎉
