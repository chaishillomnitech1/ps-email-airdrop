# Security Policy

## Supported Versions

We release patches for security vulnerabilities. Currently supported versions:

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |
| < 1.0   | :x:                |

## Reporting a Vulnerability

The ps-email-airdrop team takes security bugs seriously. We appreciate your efforts to responsibly disclose your findings.

### How to Report a Security Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

Instead, please report them via one of the following methods:

1. **Email:** Send details to the repository owner [@chaishillomnitech1](https://github.com/chaishillomnitech1)
2. **GitHub Security Advisory:** Use GitHub's [private vulnerability reporting](https://github.com/chaishillomnitech1/ps-email-airdrop/security/advisories/new)

### What to Include in Your Report

Please include the following information in your report:

- Type of vulnerability
- Full paths of source file(s) related to the manifestation of the vulnerability
- Location of the affected source code (tag/branch/commit or direct URL)
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the vulnerability, including how an attacker might exploit it

### What to Expect

- **Acknowledgment:** We will acknowledge your email within 48 hours
- **Updates:** We will send you regular updates about our progress
- **Resolution:** We aim to resolve critical vulnerabilities within 7 days
- **Credit:** We will credit you in the security advisory (unless you prefer to remain anonymous)

## Security Best Practices

When using this application:

1. **Environment Variables:** Never commit `.env` files or expose API keys
2. **Dependencies:** Regularly update dependencies to patch known vulnerabilities
3. **Access Control:** Use strong authentication for admin panel access
4. **API Keys:** Rotate Apillon API keys regularly
5. **Email Server:** Use secure email server configurations (TLS/SSL)
6. **Wallet Security:** Store admin wallet private keys securely
7. **Database:** Secure your MySQL/database instance with strong passwords
8. **HTTPS:** Always use HTTPS in production environments

## Security Features

This application implements several security features:

- JWT-based authentication for admin panel
- Input validation and sanitization
- CORS configuration
- Environment-based configuration management
- Secure email transmission protocols

## Branch Protection Recommendations

For enhanced security, we recommend enabling the following branch protection rules:

### Main Branch
- Require pull request reviews before merging (minimum 1 approval)
- Require status checks to pass before merging
  - Backend CI
  - Frontend CI
- Require branches to be up to date before merging
- Require conversation resolution before merging
- Do not allow bypassing the above settings

### Develop Branch
- Require pull request reviews before merging (minimum 1 approval)
- Require status checks to pass before merging

## Automated Security Scanning

We recommend integrating the following security tools:

- **Dependabot:** Automated dependency updates
- **CodeQL:** Static code analysis
- **npm audit:** Vulnerability scanning for Node.js dependencies
- **SAST:** Static Application Security Testing
- **Secret Scanning:** Prevent committing sensitive data

---
ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨
