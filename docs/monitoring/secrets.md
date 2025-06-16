---
sidebar_position: 5
title: Secrets
---

When working with CI/CD pipelines, it's common to need credentials or API keys—for example, to deploy to a cloud provider or access third-party services. Storing these securely is critical. GitHub Secrets provides a secure way to store and manage sensitive data like when using GiHub actions. Each CI/CD platform has its own way of managing secrets.

### Github Secrets

GitHub supports storing secrets at different levels:
- Repository-level secrets: Specific to a single repository.
- Environment-level secrets: Used within specific environments (e.g., production, staging).
- Organization-level secrets: Shared across multiple repositories.

In this course we are using repository-level secrets. 

How to Add a Secret:
1. Go to your repository on GitHub.
2. Click **Settings** > **Secrets and variables** > **Actions**.
3. Click **New repository secret**.
4. Name your secret (e.g., API_KEY) and type the secret value.

### Using Secrets in Workflows

You can use secrets in your workflow .yml file with the `secrets` context.

```yaml
jobs:
  build-and-run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Run the app
        //highlight-start
        env:
          API_KEY: ${{ secrets.API_KEY }}
        //highlight-end
        run: |
          echo "Running the app..."
          node app.js
```

Never hard-code secrets in your code or workflow files. You should also limit secret scope. Use environment or repo-level secrets as needed. 

Secrets are not injected into your application directly by GitHub. Instead, they are exposed to the runtime environment, and your application accesses them using environment variables.

In your application code, you access it using your language's environment variable access method. For example,

```js title="Node.js"
const apiKey = process.env.API_KEY;
```

```python title="Python"
import os
api_key = os.getenv("API_KEY")
```

### Gitleaks

[Gitleaks](https://gitleaks.io/) open-source (MIT license) tool for detecting hardcoded secrets in your Git repositories. It's like a security guard that scans your commits, branches, and pull requests to ensure sensitive data (like API keys, passwords, or tokens) doesn’t accidentally leak into version control.

It works by using regex-based rules. You can define a `gitleaks.toml` file to customize what patterns to scan, whitelist safe matches, or add custom secret formats. Read more about configuration format [here](https://github.com/gitleaks/gitleaks?tab=readme-ov-file#configuration). You can use Gitleaks playground (https://gitleaks.io/playground) rule wizard to generate rules.

Goal is to automate security checks before code is merged or deployed, and to catch sensitive data leaks as early as possible in CI pipeline. 

Here’s an example of a GitHub Actions workflow that runs Gitleaks using the official `gitleaks/gitleaks-action@v2`. This action provides a simple way to integrate secret scanning directly into your CI pipeline.

```yaml
name: Secret Scan

on:
  push:
    branches: [ main ]
  pull_request:

jobs:
  gitleaks:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3
        with:
          fetch-depth: 0  # Needed to scan full commit history

      - name: Run Gitleaks
        uses: gitleaks/gitleaks-action@v2
        with:
          config-path: .github/gitleaks.toml  # Optional custom config
          fail: true  # Fail the job if leaks are found
```

Workflow triggers on push or pull requests that ensures secrets are caught early before merging to main.

---

### Further Reading
- https://docs.github.com/en/actions/security-for-github-actions/security-guides/about-secrets
