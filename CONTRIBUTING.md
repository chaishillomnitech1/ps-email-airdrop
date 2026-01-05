# Contributing Guidelines

Thank you for your interest in contributing to the ps-email-airdrop project! We welcome contributions from the community.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Process](#development-process)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing](#testing)
- [Quantum and Web3 Alignment](#quantum-and-web3-alignment)

## Code of Conduct

We are committed to providing a welcoming and inclusive environment. Please:

- Be respectful and considerate
- Welcome diverse perspectives
- Accept constructive criticism gracefully
- Focus on what's best for the community

## Getting Started

### Prerequisites

- Node.js 18.x or 20.x
- npm or yarn package manager
- Git for version control
- (Optional) Docker for backend deployment

### Fork and Clone

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/ps-email-airdrop.git
   cd ps-email-airdrop
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/chaishillomnitech1/ps-email-airdrop.git
   ```

### Setup Development Environment

#### Backend Setup
```bash
cd backend
npm install
cp .env.example .env  # Configure your environment variables
npm run dev
```

#### Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

## Development Process

### Branch Naming Convention

Use descriptive branch names:
- `feature/description` - New features
- `fix/description` - Bug fixes
- `docs/description` - Documentation updates
- `refactor/description` - Code refactoring
- `test/description` - Test additions or updates

### Commit Messages

Write clear, concise commit messages:
- Use present tense ("Add feature" not "Added feature")
- Keep first line under 50 characters
- Provide detailed description if needed
- Reference issues and PRs when applicable

Example:
```
Add email validation for bulk uploads

- Implement email format validation
- Add error handling for invalid emails
- Update tests for new validation logic

Fixes #123
```

## Pull Request Process

1. **Create a Branch:** Create a new branch for your work
2. **Make Changes:** Implement your changes following coding standards
3. **Test:** Ensure all tests pass and add new tests if needed
4. **Update Documentation:** Update relevant documentation
5. **Commit:** Commit your changes with clear messages
6. **Push:** Push your branch to your fork
7. **Open PR:** Open a pull request against the `develop` branch
8. **Review:** Address review feedback
9. **Merge:** Once approved, your PR will be merged

### PR Checklist

Before submitting, ensure:
- [ ] Code follows project coding standards
- [ ] All tests pass
- [ ] New tests added for new functionality
- [ ] Documentation updated
- [ ] No merge conflicts
- [ ] PR description clearly explains the changes

## Coding Standards

### TypeScript/JavaScript

- Use TypeScript for type safety (backend)
- Follow existing code style
- Use meaningful variable and function names
- Add comments for complex logic
- Keep functions small and focused
- Avoid deep nesting

### Vue.js (Frontend)

- Follow Vue 3 composition API patterns
- Use Nuxt.js conventions
- Keep components focused and reusable
- Use proper prop validation
- Follow established naming conventions

### Formatting

- Use Prettier for code formatting
- Run `npm run format` before committing
- Follow existing `.prettierrc` configuration

### Linting

- Ensure ESLint passes (frontend)
- Fix linting errors before submitting PR
- Add linting exceptions only when necessary with comments

## Testing

### Backend Tests

```bash
cd backend
npm test
```

### Test Coverage

- Aim for high test coverage
- Write unit tests for new functions
- Add integration tests for API endpoints
- Test edge cases and error handling

### Manual Testing

- Test your changes locally
- Verify functionality in different scenarios
- Check for console errors
- Test on different browsers (frontend)

## Quantum and Web3 Alignment

We're excited about contributions that align quantum computing principles and Web3 technologies:

1. **Quantum Principles:** Ensure your contributions leverage or enhance algorithms, protocols, or systems that integrate quantum computing with the goals of this repository
2. **Web3 Synergy:** Contributions should extend or complement blockchain or Web3 technologies, maintaining a decentralized and secure outlook
3. **Collaboration:** Open constructive discussions through issues to elaborate on your intended contributions; maintain a collaborative demeanor
4. **Testing and Validation:** Submit contributions with proper tests and proofs-of-concept, especially for hybrid quantum-Web3 systems

## Reporting Issues

### Bug Reports

When reporting bugs, please include:
- Clear, descriptive title
- Steps to reproduce
- Expected vs actual behavior
- Environment details (OS, Node version, etc.)
- Screenshots if applicable
- Error messages or logs

### Feature Requests

When requesting features:
- Explain the use case
- Describe the proposed solution
- Discuss alternatives considered
- Consider implementation complexity

## Questions and Support

- **Issues:** Use GitHub Issues for bug reports and feature requests
- **Discussions:** For questions and general discussion
- **Documentation:** Check existing documentation first

## Recognition

Contributors will be recognized in:
- Release notes
- Project documentation
- GitHub contributors page

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to ps-email-airdrop! Your efforts help make this project better for everyone.

ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨
