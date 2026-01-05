# Onboarding Guide for ps-email-airdrop

Welcome to the ps-email-airdrop project! This guide will help you get started as a new contributor or team member.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Quick Start](#quick-start)
3. [Development Environment Setup](#development-environment-setup)
4. [Architecture Overview](#architecture-overview)
5. [Common Tasks](#common-tasks)
6. [Resources](#resources)

## Project Overview

The ps-email-airdrop is a comprehensive solution for distributing NFTs via email addresses. It consists of:

- **Backend:** Node.js/TypeScript API server with MySQL database
- **Frontend:** Vue 3/Nuxt.js web application
- **Integration:** Apillon SDK for NFT collection management

### Key Features

- Admin panel for managing NFT distributions
- Bulk email upload via CSV
- Automated email notifications
- Wallet linking and NFT claiming
- Delivery tracking and reporting

## Quick Start

### Day 1: Get the Code Running

1. **Clone the repository:**
   ```bash
   git clone https://github.com/chaishillomnitech1/ps-email-airdrop.git
   cd ps-email-airdrop
   ```

2. **Backend Setup:**
   ```bash
   cd backend
   npm install
   ```

3. **Frontend Setup:**
   ```bash
   cd ../frontend
   npm install
   ```

4. **Review Documentation:**
   - Read [README.md](../README.md)
   - Review [CONTRIBUTING.md](../CONTRIBUTING.md)
   - Check [Backend README](../backend/README.md)
   - Check [Frontend README](../frontend/README.md)

### Day 2-3: Understand the Architecture

- Explore the backend API structure
- Review the frontend component organization
- Understand the database schema
- Review Apillon SDK integration

### Week 1: Make Your First Contribution

- Pick a "good first issue" from GitHub
- Set up your development environment
- Make a small change and submit a PR
- Get familiar with the review process

## Development Environment Setup

### Prerequisites

Install these tools:
- **Node.js:** v18.x or v20.x ([Download](https://nodejs.org/))
- **npm:** Comes with Node.js
- **Git:** For version control ([Download](https://git-scm.com/))
- **Docker:** (Optional) For containerized backend ([Download](https://www.docker.com/))
- **MySQL:** Database server (or use Docker)
- **Code Editor:** VS Code recommended

### Backend Environment

1. **Navigate to backend:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Create environment file:**
   ```bash
   cp .env.example .env
   ```

4. **Configure environment variables:**
   Edit `.env` with your settings:
   - Database credentials
   - Apillon API key and secret
   - Email server configuration
   - JWT secret

5. **Setup database:**
   ```bash
   npm run db-upgrade
   ```

6. **Run development server:**
   ```bash
   npm run dev
   ```

7. **Run tests:**
   ```bash
   npm test
   ```

### Frontend Environment

1. **Navigate to frontend:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure settings:**
   - Review `nuxt.config.ts`
   - Update API endpoints if needed

4. **Run development server:**
   ```bash
   npm run dev
   ```

5. **Access the application:**
   - Open browser to `http://localhost:3000`

### Docker Setup (Optional)

For backend development with Docker:

```bash
cd backend
docker-compose up -d
```

## Architecture Overview

### Backend Structure

```
backend/
├── src/
│   ├── config/         # Configuration files
│   ├── lib/            # Core libraries and utilities
│   ├── modules/        # Feature modules
│   ├── scripts/        # Startup and utility scripts
│   └── tests/          # Test files
├── bin/                # Deployment scripts
└── package.json
```

### Frontend Structure

```
frontend/
├── assets/             # Static assets
├── components/         # Vue components
├── composables/        # Composition API functions
├── layouts/            # Page layouts
├── pages/              # Page components
├── plugins/            # Nuxt plugins
├── public/             # Public static files
└── stores/             # Pinia stores
```

### Technology Stack

**Backend:**
- Node.js & TypeScript
- Express.js (API framework)
- MySQL (Database)
- Apillon SDK (NFT management)
- JWT (Authentication)
- Nodemailer (Email)

**Frontend:**
- Vue 3 (Framework)
- Nuxt.js (Meta-framework)
- Pinia (State management)
- TailwindCSS (Styling)
- Naive UI (Component library)
- Viem/Wagmi (Web3 integration)

## Common Tasks

### Creating a New API Endpoint

1. Define route in appropriate module
2. Create controller function
3. Add validation logic
4. Update database schema if needed
5. Write tests
6. Document the endpoint

### Adding a Frontend Component

1. Create component in `components/` directory
2. Follow Vue 3 Composition API patterns
3. Use TypeScript for props
4. Add to appropriate page/layout
5. Style with TailwindCSS

### Running Tests

**Backend:**
```bash
cd backend
npm test
```

**Frontend:**
```bash
cd frontend
npm run test  # If tests are configured
```

### Building for Production

**Backend:**
```bash
cd backend
npm run build
```

**Frontend:**
```bash
cd frontend
npm run build
# Or for static generation:
npm run generate
```

### Database Migrations

**Create migration:**
```bash
cd backend
npm run db-upgrade
```

**Rollback migration:**
```bash
npm run db-downgrade
```

**Rebuild database:**
```bash
npm run db-rebuild
```

### Code Formatting

**Backend:**
```bash
cd backend
npm run format
```

**Frontend:**
```bash
cd frontend
npm run format  # If configured
```

## Resources

### Documentation

- [Backend Documentation](../backend/README.md)
- [Frontend Documentation](../frontend/README.md)
- [Contributing Guidelines](../CONTRIBUTING.md)
- [Security Policy](../SECURITY.md)

### External Resources

- [Apillon Documentation](https://docs.apillon.io/)
- [Vue 3 Documentation](https://vuejs.org/)
- [Nuxt.js Documentation](https://nuxt.com/)
- [TypeScript Documentation](https://www.typescriptlang.org/)
- [Express.js Documentation](https://expressjs.com/)

### Getting Help

- **GitHub Issues:** Report bugs or request features
- **Pull Requests:** Submit code contributions
- **Code Review:** Learn from PR feedback
- **Documentation:** Check existing docs first

### Key Contacts

- **Primary Maintainer:** [@chaishillomnitech1](https://github.com/chaishillomnitech1)
- **Code Owners:** See [CODEOWNERS](../.github/CODEOWNERS)

## Next Steps

1. **Explore the codebase:** Familiarize yourself with the structure
2. **Run the application:** Get everything running locally
3. **Pick an issue:** Start with a good first issue
4. **Join discussions:** Participate in GitHub discussions
5. **Ask questions:** Don't hesitate to ask for help

## Tips for Success

- **Start small:** Make small, focused changes
- **Read the code:** Understand existing patterns before adding new ones
- **Test thoroughly:** Always test your changes
- **Document:** Update docs when adding features
- **Communicate:** Keep others informed of your work
- **Be patient:** Learning a new codebase takes time

## Development Best Practices

- **Branching:** Create feature branches from `develop`
- **Commits:** Write clear, descriptive commit messages
- **PRs:** Keep pull requests focused and small
- **Reviews:** Address feedback promptly
- **Tests:** Maintain and improve test coverage
- **Security:** Never commit secrets or API keys

---

Welcome aboard! We're excited to have you as part of the team.

ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨
