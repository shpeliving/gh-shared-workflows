# GitHub Shared Workflows

## Running Locally with act

To run workflows locally using act, first retrieve a GitHub token with `gh auth token`. Then, use the token with the following command:

```bash
act -P self-hosted=us-west1-docker.pkg.dev/infra-368116/infra/actions-runner:0.1.0 -s ORGANIZATION_GITHUB_TOKEN=<token>
```

To run a specific job, use:

```bash
act -j run-tests -P self-hosted=us-west1-docker.pkg.dev/infra-368116/infra/actions-runner:0.1.0 -s ORGANIZATION_GITHUB_TOKEN=<token>
```
