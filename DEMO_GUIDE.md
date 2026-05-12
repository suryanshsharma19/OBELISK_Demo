# OBELISK CI/CD Demo Guide

## Goal
Show OBELISK blocking risky changes in CI on PRs and allowing safe fixes after.

## One-time setup (repo secrets)
Add these GitHub Actions secrets:

- OBELISK_API_BASE_URL
- OBELISK_AUTH_USERNAME
- OBELISK_AUTH_PASSWORD

## Demo flow (fail -> fix)

### 1) Create a PR that should fail

Edit requirements.txt and change:

```
requests==2.33.1
```

to a typo package (typosquatting signal):

```
reqeusts==1.0.0
```

Push to a new branch and open a PR. The workflow should fail and block.

### 2) Fix the PR to pass

Revert requirements.txt back to:

```
requests==2.33.1
```

Push the fix to the same PR. The workflow should pass.

## Notes

- The risk threshold is set to 20 in the workflow to make the block demo reliable.
- Ensure the OBELISK API URL is reachable from GitHub Actions.
