# copilot-arc

Repo to test GitHub Actions Runner Controller (ARC) with GitHub Copilot Agent

For complete setup, please go to [Medium Article](https://renjithvr11.medium.com/taking-github-copilot-off-the-cloud-a-guide-to-in-house-ai-d1ca55b9e234?sk=3589b6617c2334ce8e44820cedd82718)

## Overview

This repository is designed to test and validate the integration between GitHub Actions Runner Controller (ARC) and GitHub Copilot Agent. It provides a testing environment for running Copilot workflows on self-hosted Kubernetes runners.

## Prerequisites

- Kubernetes cluster with ARC installed
- GitHub repository with Copilot enabled
- Self-hosted runner configured with the `arc-k3s-runners` label

## Environment Variables

The following environment variables are used in the workflows:

- `GITHUB_HOST`: The GitHub host (default: `github.com`)

To set the environment variable in a workflow:
```yaml
- name: Set GitHub Host
  run: echo "GITHUB_HOST=github.com" >> $GITHUB_ENV
```

## Setup

The repository includes a setup workflow that runs automatically when:
- Manually triggered via workflow_dispatch
- The workflow file is modified
- A pull request modifies the workflow file

The workflow runs on `arc-k3s-runners` and executes the setup steps defined in the `.github/workflows/` directory.

## Usage

1. Ensure your ARC runners are properly configured
2. Create a pull request or trigger the workflow manually
3. Monitor the workflow execution in the Actions tab

## License

See the [LICENSE](LICENSE) file for details.
