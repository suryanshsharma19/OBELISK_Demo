# OBELISK CI/CD Demo Repo

This repo is used to demonstrate OBELISK CI/CD security gating on GitHub.

## What it does

- Runs OBELISK dependency + changed-code scans on push and pull_request.
- Blocks merges when risk crosses the configured threshold.

## Quick start (demo)

1) Add repo secrets (Settings -> Secrets -> Actions):

- OBELISK_API_BASE_URL
- OBELISK_AUTH_USERNAME
- OBELISK_AUTH_PASSWORD

2) Open the Actions tab and confirm the workflow runs on push.

3) For the "block" demo, open a PR that changes requirements.txt to a typo package
   (see DEMO_GUIDE.md).

4) For the "pass" demo, revert to a safe package/version.
