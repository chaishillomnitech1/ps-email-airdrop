---
name: Vercel Setup Checklist
about: Setup guide for Vercel deployment configuration
title: '[SETUP] Vercel Deployment Configuration'
labels: ['setup', 'deployment', 'vercel']
assignees: ['chaishillomnitech1']
---

## Vercel Setup Checklist

This issue tracks the setup and configuration of Vercel deployment for the project.

### Prerequisites

- [ ] Vercel account created
- [ ] GitHub repository connected to Vercel
- [ ] Required secrets available

### Vercel Dashboard Configuration

- [ ] Import project from GitHub
- [ ] Set framework preset to **Nuxt.js**
- [ ] Configure root directory to `frontend`
- [ ] Set Node.js version to **20.x**

### Build Settings

- [ ] Build Command: `npm run build`
- [ ] Output Directory: `.output`
- [ ] Install Command: `npm install`
- [ ] Development Command: `npm run dev`

### Environment Variables

Add the following environment variables in Vercel project settings:

**Required:**
- [ ] `NODE_VERSION` = `20`
- [ ] `APILLON_API_KEY` = (your Apillon API key)
- [ ] `APILLON_API_SECRET` = (your Apillon API secret)

**Optional (based on features):**
- [ ] `SMTP_HOST` = (email server host)
- [ ] `SMTP_PORT` = `587`
- [ ] `SMTP_USER` = (email server username)
- [ ] `SMTP_PASS` = (email server password)

### GitHub Secrets

Add the following secrets in GitHub repository settings (Settings > Secrets and variables > Actions):

**Vercel Integration:**
- [ ] `VERCEL_TOKEN` - Vercel API token
- [ ] `VERCEL_ORG_ID` - Vercel organization ID
- [ ] `VERCEL_PROJECT_ID` - Vercel project ID

**AI PR Bot:**
- [ ] `OPENAI_API_KEY` - OpenAI API key

**Rewards (Test Environment):**
- [ ] `REWARDS_PRIVATE_KEY` - Test wallet private key
- [ ] `ALCHEMY_MUMBAI_URL` - Alchemy Mumbai testnet URL
- [ ] `REWARDS_API_KEY` - Rewards API key
- [ ] `REWARDS_CONTRACT_ADDRESS` - Smart contract address
- [ ] `PILOT_TEST_WALLET` - Test wallet address

**Repo Sync:**
- [ ] `GITHUB_PAT` - GitHub Personal Access Token

### Vercel Integration Steps

1. **Get Vercel Token**
   - [ ] Go to Vercel Dashboard → Settings → Tokens
   - [ ] Create new token with appropriate permissions
   - [ ] Add as `VERCEL_TOKEN` secret in GitHub

2. **Get Organization and Project IDs**
   - [ ] Run: `vercel project ls` or check Vercel project settings
   - [ ] Add `VERCEL_ORG_ID` secret in GitHub
   - [ ] Add `VERCEL_PROJECT_ID` secret in GitHub

3. **Configure Deployment Workflow**
   - [ ] Verify `.github/workflows/vercel-deploy.yml` exists
   - [ ] Test workflow by pushing to master branch
   - [ ] Verify deployment succeeds

### Testing

- [ ] Create test commit to trigger deployment
- [ ] Verify build completes successfully
- [ ] Check deployment on Vercel dashboard
- [ ] Visit deployed URL and test functionality
- [ ] Verify environment variables are loaded correctly

### Domain Configuration (Optional)

- [ ] Add custom domain in Vercel project settings
- [ ] Configure DNS records
- [ ] Enable HTTPS
- [ ] Test domain accessibility

### Monitoring

- [ ] Enable Vercel Analytics (optional)
- [ ] Configure deployment notifications
- [ ] Set up error tracking (if needed)

### Documentation

- [ ] Update README.md with deployment instructions
- [ ] Document any project-specific configurations
- [ ] Add troubleshooting guide

### Final Checks

- [ ] All secrets are configured
- [ ] Build and deployment successful
- [ ] Application is accessible via Vercel URL
- [ ] Environment variables working correctly
- [ ] No secrets exposed in logs or client code

### Notes

<!-- Add any additional notes, issues encountered, or special configurations needed -->

### Resources

- [Vercel Documentation](https://vercel.com/docs)
- [Nuxt.js Deployment Guide](https://nuxt.com/docs/getting-started/deployment)
- [GitHub Actions for Vercel](https://github.com/marketplace/actions/vercel-action)
- [DEPLOYMENT.md](../DEPLOYMENT.md) - Project deployment guide

---

**Assigned to:** @chaishillomnitech1  
**Status:** 🔄 In Progress

<!-- Once all items are checked, close this issue and document the setup in DEPLOYMENT.md -->
