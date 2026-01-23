# Deployment Guide - Phase 2

This guide covers the deployment setup for the Phase 2 rollout, including Vercel integration and GitHub automation workflows.

## Prerequisites

- GitHub repository with proper access rights
- Vercel account with deployment permissions
- Node.js 20+ installed locally for testing
- All required API keys and secrets (see below)

## Required Secrets

Before running any workflows, ensure the following secrets are configured in your GitHub repository settings (Settings > Secrets and variables > Actions):

### OpenAI Integration
- `OPENAI_API_KEY` - OpenAI API key for AI PR bot functionality

### Vercel Deployment
- `VERCEL_TOKEN` - Vercel authentication token for automated deployments
- `VERCEL_ORG_ID` - Vercel organization ID (found in project settings)
- `VERCEL_PROJECT_ID` - Vercel project ID (found in project settings)

### Rewards System (Test Environment)
- `REWARDS_PRIVATE_KEY` - Private key for test rewards contract (test wallet only)
- `ALCHEMY_MUMBAI_URL` - Alchemy API URL for Mumbai testnet
- `REWARDS_API_KEY` - API key for rewards system
- `REWARDS_CONTRACT_ADDRESS` - Smart contract address for rewards
- `PILOT_TEST_WALLET` - Test wallet address for pilot program

### Repository Sync
- `GITHUB_PAT` - GitHub Personal Access Token for repo synchronization

## Vercel Setup

1. **Link Your Repository**
   - Log in to Vercel dashboard
   - Import your GitHub repository
   - Select the `frontend` directory as the root

2. **Configure Environment Variables**
   - Add all required environment variables in Vercel project settings
   - Ensure `NODE_VERSION` is set to `20`
   - Configure build and deployment settings

3. **Set Build Configuration**
   - Framework: Nuxt.js
   - Build Command: `npm run build`
   - Output Directory: `.output`
   - Install Command: `npm install`

## Workflow Overview

### 1. Vercel Deploy (`vercel-deploy.yml`)
- Automatically deploys to Vercel on push to main/master
- Uses Node 20 runtime
- Runs build checks before deployment

### 2. E2E Tests (`e2e.yml`)
- Runs end-to-end tests on pull requests
- Ensures quality before merging
- Uses Node 20 runtime

### 3. AI PR Bot (`ai-pr-bot.yml`)
- Analyzes pull requests using AI
- Posts analysis as PR comments only (no auto-merge)
- Uses conservative prompt settings
- Never exposes secrets

### 4. Reward and Mint (`reward-and-mint.yml`)
- Pilot program for testing rewards
- Runs on manual trigger only
- Uses test environment and test wallets
- No production deployments

### 5. Repo Sync (`repo-sync.yml`)
- Synchronizes with upstream repositories
- Manual trigger or scheduled runs
- Requires GitHub PAT for cross-repo access

## Deployment Steps

1. **Merge Phase 2 Branch**
   ```bash
   # Review and merge copilot/phase-2-rollout branch
   git checkout master
   git merge copilot/phase-2-rollout
   git push origin master
   ```

2. **Add Required Secrets**
   - Go to repository Settings > Secrets and variables > Actions
   - Add all secrets listed in the "Required Secrets" section above

3. **Confirm Vercel Configuration**
   - Verify Vercel project is properly linked
   - Check environment variables are set
   - Confirm build settings match requirements

4. **Run Test Deploy**
   - Trigger a manual deployment from Vercel dashboard
   - Monitor build logs for any issues
   - Verify deployment is successful

5. **Enable Workflows**
   - All workflows are now enabled automatically
   - Monitor Actions tab for workflow runs
   - Review AI PR bot comments on new PRs

## Testing

After deployment:

1. Create a test PR to verify AI bot functionality
2. Check Vercel deployment automation
3. Run manual reward test (test wallet only)
4. Verify e2e tests execute properly

## Troubleshooting

### Vercel Deployment Fails
- Check build logs in Vercel dashboard
- Verify Node version is set to 20
- Ensure all environment variables are configured

### Workflow Failures
- Check GitHub Actions logs
- Verify secrets are properly set
- Confirm permissions are correct

### AI PR Bot Issues
- Verify OPENAI_API_KEY is valid
- Check rate limits and quotas
- Review prompt settings in workflow file

## Security Notes

- Never commit secrets to repository
- Use test wallets only for pilot programs
- AI bot posts comments only, no auto-merge
- Regular security audits recommended
- Keep dependencies updated

## Support

For issues or questions:
- Review workflow logs in GitHub Actions
- Check Vercel deployment logs
- Contact @chaishillomnitech1 for code reviews
