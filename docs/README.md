# Documentation Index

Welcome to the ps-email-airdrop documentation hub. This index will help you navigate all available documentation.

## 📚 Quick Links

### Getting Started
- **[Main README](../README.md)** - Project overview and quick start
- **[Onboarding Guide](ONBOARDING.md)** - New contributor onboarding
- **[Contributing Guidelines](../CONTRIBUTING.md)** - How to contribute

### Development
- **[Backend Documentation](../backend/README.md)** - Backend setup and API docs
- **[Frontend Documentation](../frontend/README.md)** - Frontend setup and components

### Governance & Security
- **[Security Policy](../SECURITY.md)** - Security reporting and best practices
- **[Branch Protection](BRANCH_PROTECTION.md)** - Branch protection recommendations
- **[DAO Automation](DAO_AUTOMATION.md)** - Governance and automation hooks

### GitHub
- **[Issue Template](../.github/ISSUE_TEMPLATE.md)** - How to create issues
- **[PR Template](../.github/PULL_REQUEST_TEMPLATE.md)** - Pull request guidelines
- **[CODEOWNERS](../.github/CODEOWNERS)** - Code ownership structure

## 📖 Documentation by Topic

### For New Contributors

If you're new to the project:

1. Start with the **[Main README](../README.md)** to understand what the project does
2. Read the **[Onboarding Guide](ONBOARDING.md)** to set up your development environment
3. Review **[Contributing Guidelines](../CONTRIBUTING.md)** to understand our workflow
4. Pick a "good first issue" from GitHub and start coding!

### For Developers

#### Backend Development
- **Setup:** See [Backend README](../backend/README.md)
- **API Structure:** Located in `backend/src/modules/`
- **Database:** MySQL with migrations in `backend/src/lib/migrations/`
- **Testing:** Run `npm test` in backend directory
- **Scripts:** Available in `backend/package.json`

#### Frontend Development
- **Setup:** See [Frontend README](../frontend/README.md)
- **Framework:** Vue 3 with Nuxt.js
- **Components:** Located in `frontend/components/`
- **Pages:** Located in `frontend/pages/`
- **State Management:** Pinia stores in `frontend/stores/`

#### Testing & Quality
- **Backend Tests:** `cd backend && npm test`
- **Code Formatting:** `npm run format` (both frontend and backend)
- **Type Checking:** `npm run tsc` (backend)
- **Linting:** ESLint configured for frontend

### For Maintainers

#### Repository Management
- **[CODEOWNERS](../.github/CODEOWNERS)** - Review ownership structure
- **[Branch Protection](BRANCH_PROTECTION.md)** - Recommended protection rules
- **[Dependabot](../.github/dependabot.yml)** - Automated dependency updates

#### Security
- **[Security Policy](../SECURITY.md)** - Security guidelines and reporting
- **Workflows:** Security scanning in `.github/workflows/security.yml`
- **Best Practices:** Environment variable management, API key rotation

#### Governance
- **[DAO Automation](DAO_AUTOMATION.md)** - Decentralized governance integration
- **Decision Making:** Community-driven through issues and PRs
- **Code Reviews:** Required before merging (see CODEOWNERS)

## 🔧 Workflows & Automation

### GitHub Actions

All workflows are located in `.github/workflows/`:

#### Continuous Integration
- **[backend-ci.yml](../.github/workflows/backend-ci.yml)** - Backend install, test, and build
- **[frontend-ci.yml](../.github/workflows/frontend-ci.yml)** - Frontend install, build, and generate
- **[code-quality.yml](../.github/workflows/code-quality.yml)** - Code quality checks and PR size

#### Security & Dependencies
- **[security.yml](../.github/workflows/security.yml)** - Security scanning and dependency audits
- **[dependabot.yml](../.github/dependabot.yml)** - Automated dependency updates

#### Deployment
- **[deploy.yml](../.github/workflows/deploy.yml)** - Deployment to Apillon Hosting

### Automation Features
- Automatic PR size labeling
- Dependency security scanning
- Code quality checks
- Automatic branch cleanup
- Issue and PR templates

## 🎯 Common Tasks

### How to...

#### Report a Bug
1. Check existing issues to avoid duplicates
2. Use the [Issue Template](../.github/ISSUE_TEMPLATE.md)
3. Provide clear reproduction steps
4. Include environment details

#### Request a Feature
1. Open a new issue with feature description
2. Explain the use case and benefits
3. Discuss with maintainers
4. Submit PR if approved

#### Submit a Pull Request
1. Fork and clone the repository
2. Create a feature branch
3. Make your changes with tests
4. Use the [PR Template](../.github/PULL_REQUEST_TEMPLATE.md)
5. Address review feedback
6. Get approval and merge

#### Review Code
1. Check the PR description and related issue
2. Review code changes thoroughly
3. Test locally if possible
4. Provide constructive feedback
5. Approve or request changes

#### Deploy Changes
1. Ensure all CI checks pass
2. Get required approvals
3. Merge to main branch
4. Trigger deployment workflow
5. Monitor deployment status

## 📝 Templates

### Issue Templates
- Located in `.github/ISSUE_TEMPLATE.md`
- Auto-assigned to @chaishillomnitech1
- Includes all necessary sections

### Pull Request Template
- Located in `.github/PULL_REQUEST_TEMPLATE.md`
- Checklist for contributors
- Links to related issues

## 🔐 Security

### Reporting Vulnerabilities
- **DO NOT** create public issues for security vulnerabilities
- Follow the [Security Policy](../SECURITY.md)
- Contact maintainers privately
- Use GitHub Security Advisories

### Best Practices
- Never commit secrets or API keys
- Use environment variables
- Keep dependencies updated
- Follow security scanning recommendations
- Review the [Security Policy](../SECURITY.md)

## 🌐 External Resources

### Technologies
- [Apillon SDK Documentation](https://docs.apillon.io/)
- [Vue 3 Documentation](https://vuejs.org/)
- [Nuxt.js Documentation](https://nuxt.com/)
- [TypeScript Documentation](https://www.typescriptlang.org/)
- [Express.js Documentation](https://expressjs.com/)

### GitHub Features
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches)
- [Dependabot Documentation](https://docs.github.com/en/code-security/dependabot)
- [Code Owners Documentation](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)

## 🤝 Community

### Getting Help
- **GitHub Issues:** For bugs and feature requests
- **GitHub Discussions:** For questions and general discussion
- **Pull Requests:** For code contributions

### Communication
- Be respectful and inclusive
- Follow the code of conduct
- Provide constructive feedback
- Help newcomers get started

## 📅 Regular Updates

This documentation is regularly updated. If you find any issues or have suggestions:

1. Open an issue
2. Submit a PR with improvements
3. Contact maintainers

Last updated: 2026-01-05

---

## Quick Reference Card

```
📖 Getting Started:     README.md → ONBOARDING.md → CONTRIBUTING.md
🔧 Development:         backend/README.md, frontend/README.md
🔐 Security:            SECURITY.md
🏛️ Governance:          DAO_AUTOMATION.md, BRANCH_PROTECTION.md
🤖 Automation:          .github/workflows/
📝 Templates:           .github/ISSUE_TEMPLATE.md, .github/PULL_REQUEST_TEMPLATE.md
👥 Ownership:           .github/CODEOWNERS
```

---

ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨
