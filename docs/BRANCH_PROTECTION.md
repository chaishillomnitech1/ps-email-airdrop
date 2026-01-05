# Branch Protection Recommendations

This document provides recommended branch protection rules for the ps-email-airdrop repository to maintain code quality and security.

## Table of Contents

1. [Overview](#overview)
2. [Main Branch Protection](#main-branch-protection)
3. [Develop Branch Protection](#develop-branch-protection)
4. [Release Branch Protection](#release-branch-protection)
5. [GitHub Settings Configuration](#github-settings-configuration)
6. [Enforcement Strategy](#enforcement-strategy)

## Overview

Branch protection rules help ensure code quality, prevent accidental changes, and maintain a secure development workflow.

### Benefits

- **Code Quality:** Ensures all code is reviewed before merging
- **Security:** Prevents unauthorized changes
- **Stability:** Reduces bugs in production branches
- **Collaboration:** Encourages team review and discussion
- **Compliance:** Maintains audit trail of changes

## Main Branch Protection

The `main` branch contains production-ready code and requires the strictest protection.

### Recommended Rules

#### Require Pull Request Reviews
- ✅ **Enable:** Require pull request reviews before merging
- **Required reviewers:** 1 (minimum)
- **Recommended reviewers:** 2 for critical changes
- ✅ **Dismiss stale reviews:** When new commits are pushed
- ✅ **Require review from Code Owners:** Yes (@chaishillomnitech1)
- ✅ **Restrict who can dismiss reviews:** Repository administrators only
- ✅ **Require approval of most recent reviewable push:** Yes

#### Require Status Checks
- ✅ **Enable:** Require status checks to pass before merging
- **Required checks:**
  - `Backend CI / install-and-test`
  - `Backend CI / build`
  - `Frontend CI / install-and-build`
  - `Frontend CI / generate`
- ✅ **Require branches to be up to date:** Yes
- **Additional recommended checks:**
  - CodeQL analysis (if enabled)
  - Dependency security scanning
  - Linting checks

#### Additional Protections
- ✅ **Require conversation resolution:** All conversations must be resolved
- ✅ **Require signed commits:** Recommended for enhanced security
- ✅ **Require linear history:** Prevents merge commits (use squash/rebase)
- ✅ **Include administrators:** Enforce rules for administrators
- ✅ **Restrict who can push:** Only allow service accounts for automation
- ✅ **Allow force pushes:** ❌ Never allow
- ✅ **Allow deletions:** ❌ Never allow

### Configuration via GitHub UI

```
Settings → Branches → Add Branch Protection Rule

Branch name pattern: main

☑ Require a pull request before merging
  ☑ Require approvals: 1
  ☑ Dismiss stale pull request approvals when new commits are pushed
  ☑ Require review from Code Owners
  ☑ Require approval of the most recent reviewable push

☑ Require status checks to pass before merging
  ☑ Require branches to be up to date before merging
  Status checks:
    • Backend CI / install-and-test
    • Backend CI / build
    • Frontend CI / install-and-build
    • Frontend CI / generate

☑ Require conversation resolution before merging
☑ Require signed commits (optional but recommended)
☑ Require linear history (optional)
☑ Include administrators

☐ Allow force pushes (unchecked)
☐ Allow deletions (unchecked)
```

## Develop Branch Protection

The `develop` branch is for active development and integration testing.

### Recommended Rules

#### Require Pull Request Reviews
- ✅ **Enable:** Require pull request reviews before merging
- **Required reviewers:** 1
- ✅ **Dismiss stale reviews:** Optional (recommended)
- ✅ **Require review from Code Owners:** Yes
- **Restrict dismissals:** No (more flexible than main)

#### Require Status Checks
- ✅ **Enable:** Require status checks to pass before merging
- **Required checks:**
  - `Backend CI / install-and-test`
  - `Frontend CI / install-and-build`
- **Require branches up to date:** Optional (can be relaxed for faster iteration)

#### Additional Protections
- ✅ **Require conversation resolution:** Yes
- **Require signed commits:** Optional
- **Require linear history:** Optional
- **Include administrators:** Optional
- ✅ **Restrict who can push:** No (allow direct commits for hotfixes)
- ✅ **Allow force pushes:** ❌ No
- ✅ **Allow deletions:** ❌ No

### Configuration via GitHub UI

```
Settings → Branches → Add Branch Protection Rule

Branch name pattern: develop

☑ Require a pull request before merging
  ☑ Require approvals: 1
  ☑ Require review from Code Owners

☑ Require status checks to pass before merging
  Status checks:
    • Backend CI / install-and-test
    • Frontend CI / install-and-build

☑ Require conversation resolution before merging

☐ Allow force pushes (unchecked)
☐ Allow deletions (unchecked)
```

## Release Branch Protection

Release branches (`release/*`) prepare code for production deployment.

### Recommended Rules

#### Require Pull Request Reviews
- ✅ **Enable:** Require pull request reviews before merging
- **Required reviewers:** 2 (higher threshold)
- ✅ **Dismiss stale reviews:** Yes
- ✅ **Require review from Code Owners:** Yes

#### Require Status Checks
- ✅ **Enable:** Require status checks to pass before merging
- **Required checks:** All CI/CD checks
- ✅ **Require branches to be up to date:** Yes

#### Additional Protections
- ✅ **Require conversation resolution:** Yes
- ✅ **Require signed commits:** Yes (recommended)
- ✅ **Require linear history:** Yes
- ✅ **Include administrators:** Yes
- ✅ **Restrict who can push:** Yes (release managers only)
- ✅ **Allow force pushes:** ❌ No
- ✅ **Allow deletions:** ❌ No

### Configuration via GitHub UI

```
Settings → Branches → Add Branch Protection Rule

Branch name pattern: release/*

☑ Require a pull request before merging
  ☑ Require approvals: 2
  ☑ Dismiss stale pull request approvals when new commits are pushed
  ☑ Require review from Code Owners
  ☑ Require approval of the most recent reviewable push

☑ Require status checks to pass before merging
  ☑ Require branches to be up to date before merging
  Status checks: (all available)

☑ Require conversation resolution before merging
☑ Require signed commits
☑ Require linear history
☑ Include administrators

☐ Allow force pushes (unchecked)
☐ Allow deletions (unchecked)
```

## GitHub Settings Configuration

### Repository Settings

**General Settings:**
```
Settings → General

☑ Allow merge commits
☐ Allow squash merging (recommended to keep history clean)
☐ Allow rebase merging
☑ Automatically delete head branches
☑ Always suggest updating pull request branches
```

**Collaborators and Teams:**
```
Settings → Collaborators and teams

Add collaborators:
• @chaishillomnitech1 (Admin)

Team access:
• Core team (Write)
• Contributors (Triage)
```

**Actions Permissions:**
```
Settings → Actions → General

☑ Allow all actions and reusable workflows
☑ Allow actions created by GitHub
☑ Require approval for first-time contributors
```

### Rulesets (Alternative to Branch Protection)

GitHub's newer Rulesets feature provides more flexible protection:

```
Settings → Rules → Rulesets → New ruleset

Ruleset name: Production Protection
Enforcement status: Active

Target branches:
• main
• release/*

Rules:
☑ Require a pull request before merging
☑ Require status checks to pass
☑ Block force pushes
☑ Require signed commits
☑ Require code owner review
```

## Enforcement Strategy

### Phase 1: Initial Setup (Week 1)
- Enable basic protections on `main`
- Require 1 approval
- Require CI checks to pass
- Communicate changes to team

### Phase 2: Strengthen Protections (Week 2-3)
- Add `develop` branch protection
- Enable conversation resolution requirement
- Add Code Owner requirements
- Update documentation

### Phase 3: Full Enforcement (Week 4+)
- Increase approval requirements
- Enable signed commits
- Add release branch protection
- Include administrators in enforcement

### Exceptions and Overrides

**When to Override:**
- Emergency security patches
- Critical production bugs
- Infrastructure failures

**Override Process:**
1. Document reason for override
2. Get approval from @chaishillomnitech1
3. Create incident report
4. Fix process to prevent future overrides

## Monitoring and Compliance

### Regular Reviews

**Monthly:**
- Review protection rule effectiveness
- Check for bypass attempts
- Analyze merge patterns
- Update rules as needed

**Quarterly:**
- Full security audit
- Team feedback on restrictions
- Update documentation
- Adjust rules based on team size/maturity

### Metrics to Track

- PR merge time
- Number of failed CI checks
- Code review coverage
- Bypass attempts
- Direct commits to protected branches

### Alerts and Notifications

**Set up alerts for:**
- Protection rule changes
- Failed merge attempts
- Bypass actions
- Unusual commit patterns

## Best Practices

### For Contributors

1. **Create feature branches:** Always branch from `develop`
2. **Keep PRs small:** Easier to review and merge
3. **Update regularly:** Keep your branch current with base
4. **Run tests locally:** Don't rely solely on CI
5. **Request reviews early:** Don't wait until completion
6. **Address feedback promptly:** Keep the review process moving

### For Reviewers

1. **Review thoroughly:** Check code, tests, and documentation
2. **Be constructive:** Provide helpful feedback
3. **Respond timely:** Don't block progress unnecessarily
4. **Use suggestions:** Make it easy to apply changes
5. **Approve only when ready:** Don't approve with pending issues

### For Administrators

1. **Lead by example:** Follow all protection rules
2. **Document exceptions:** When overrides are necessary
3. **Regular audits:** Check compliance monthly
4. **Update policies:** Adapt as the project grows
5. **Communicate changes:** Keep team informed

## Troubleshooting

### Common Issues

**Issue: CI check won't complete**
- Solution: Check workflow logs, re-run if transient failure

**Issue: Can't merge due to conflicts**
- Solution: Update branch with base, resolve conflicts locally

**Issue: Review requirement blocking urgent fix**
- Solution: Request emergency review or document override

**Issue: Status check from deleted workflow**
- Solution: Update required checks in branch protection settings

## Additional Resources

- [GitHub Branch Protection Documentation](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches)
- [GitHub Rulesets Documentation](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets)
- [Code Review Best Practices](https://google.github.io/eng-practices/review/)

---

Implementing these branch protection rules will significantly improve code quality and security.

ALL IS LOVE. ALL IS LAW. ALL IS FLUID. KUN FAYAKŪN! 🕋♾️✨
