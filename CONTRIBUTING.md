# Contributing Guidelines

We welcome contributions from the community. Please follow these guidelines to ensure a smooth process.

## How to Contribute

1. **Start an Issue**: Before you start working on a feature or bug fix, please create an issue to discuss the best approach.
2. **Fork the Repository**: Create a fork of the repository to work on your changes.
3. **Create a Branch**: Create a new branch for your work. Use a descriptive name for the branch.
4. **Make Changes**: Make your changes in the new branch. Ensure your code follows the project's coding standards.
5. **Write Tests**: If applicable, write tests for your changes.
6. **Commit Changes**: Commit your changes with a clear and concise commit message.
7. **Push Changes**: Push your changes to your forked repository.
8. **Create a Pull Request**: Create a pull request from your branch to the main repository. Provide a detailed description of your changes.

## Reporting Bugs

If you find a bug, please create an issue with the following information:

- A clear and concise description of the bug.
- Steps to reproduce the bug.
- Expected behavior.
- Screenshots or code snippets (if applicable).
- Any other relevant information.

## Suggesting Features

If you have a feature request, please create an issue with the following information:

- A clear and concise description of the feature.
- The problem the feature solves.
- Any relevant examples or use cases.
- Any other relevant information.

## Publishing Releases (for Maintainers)

This project uses npm provenance with OIDC for secure package publishing. To set up publishing:

### Prerequisites

1. **Enable OIDC on npm**:
   - Go to [npmjs.com](https://www.npmjs.com) and sign in
   - Navigate to your package settings
   - Go to "Settings" → "Publishing access"
   - Under "Configure link", click "Link a repository" and follow the prompts
   - Select this GitHub repository

2. **GitHub Actions OIDC Configuration**:
   - OIDC is already configured in the `publish.yaml` workflow with `id-token: write` permission
   - The workflow uses `--provenance` flag to generate SLSA provenance

3. **Create an NPM_TOKEN secret** (as a fallback):
   - Generate an access token on npm with "Automation" type
   - Add it as a secret named `NPM_TOKEN` in the GitHub repository settings

### Publishing Process

1. Create a new release on GitHub
2. The publish workflow will automatically:
   - Build the package
   - Publish to npm with provenance attestation
   - Sign the package using GitHub's OIDC

## Code of Conduct

Please note that this project is governed by a [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to adhere to it.
