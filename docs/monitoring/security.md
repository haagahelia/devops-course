---
sidebar_position: 4
title: Security
---

**DevSecOps** is the practice of integrating security into every stage of the software development lifecycle, combining development (Dev), security (Sec), and operations (Ops). It emphasizes collaboration between development, security, and operations teams to identify and address security issues early and continuously.

**Practical examples of DevSecOps:**

**Automated Security Testing:** Integrating tools like CodeQL or SonarQube into CI/CD pipelines to automatically scan code for vulnerabilities.

**Container Security:** Using tools such as Trivy or Aqua Security to scan container images for known vulnerabilities before deployment.

**Infrastructure as Code (IaC) Scanning:** Employing tools like Checkov or Terraform Compliance to ensure infrastructure code follows security best practices.

**Secrets Management:** Implementing solutions like HashiCorp Vault or Azure Key Vault to securely manage sensitive information such as API keys and passwords.

https://www.microsoft.com/en-in/security/business/security-101/what-is-devsecops
https://www.redhat.com/en/topics/devops/what-is-devsecops

### Automated security testing

Automated security testing in software development is the practice of using tools and scripts to automatically scan code and dependencies for security vulnerabilities throughout the development lifecycle. This process helps identify issues such as insecure code patterns, known vulnerabilities in libraries, misconfigurations, and secrets exposure before software is deployed.

#### CodeQL

CodeQL is a code analysis engine developed by GitHub. It's used to automatically find security vulnerabilities and bugs in source code by treating code as data and querying it like a database. CodeQL lets you write queries in a declarative language (similar to SQL) to examine the relationships and flow in your codebase.

You can run CodeQL from the command line ([CodeQL CLI](https://docs.github.com/en/code-security/codeql-cli/getting-started-with-the-codeql-cli/about-the-codeql-cli)) or integrate with Visual Studio Code using the [CodeQL extension](https://marketplace.visualstudio.com/items?itemName=github.vscode-codeql).

In this course, we learn how to integrate CodeQL to your Github workflows. Clone the following Java project [repository](https://github.com/juhahinkula/codeql-demo.git).

The project is a basic user management system built with Spring Boot and Gradle. Our goal is to set up a CodeQL analysis workflow that runs automatically whenever code is pushed to the main branch.

To begin, create a new workflow file named `codeql.yml` in the `.github\workflows` directory. Specify a descriptive name for the workflow and configure the events that will trigger its execution:

```yaml
name: "CodeQL Analysis"

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]
```
Next, add a first job that runs on the latest Ubuntu virtual environment.

We have to define permissions in the following way:
`actions: read` – Allows the job to read actions in the repository.
`contents: read` – Allows the job to read repository contents.
`security-events: write` – Allows the job to upload security analysis results (such as CodeQL findings) to GitHub’s Security tab.

```yaml
jobs:
  analyze:
    name: Analyze
    runs-on: ubuntu-latest
    permissions:
      actions: read
      contents: read
      security-events: write
```

The `strategy` defines how jobs are run. The `fail-fast: false` define that jobs will run to completion even if one fails. The `matrix` contains one variable, `language`, set to `['java']`. If you add more languages (e.g., ['java', 'node']), the job would run once for each language.

```yaml
    strategy:
      fail-fast: false
      matrix:
        language: [ 'java' ]
```
The firs step checks out your repository’s code onto the runner. It makes your code available for the next steps in the workflow.

Then we uses the `actions/setup-java@v4` GitHub action to install Java (specifically version 23, using the Temurin distribution) on the runner. 

```yaml
steps:
    - name: Checkout repository
      uses: actions/checkout@v4

    - name: Setup Java
      uses: actions/setup-java@v4
      with:
        java-version: '23'
        distribution: 'temurin'
```
The last steps handles the CodeQL analysis.

`Initialize CodeQL` step sets up CodeQL for the workflow. It specifies which programming languages to analyze (using `${{ matrix.language }}` so it can run for multiple languages if needed).

`Autobuild` step automatically builds your project. CodeQL needs to understand your code’s structure, so it tries to build your project using standard build tools.

`Perform CodeQL Analysis` step runs the actual CodeQL analysis. It scans your codebase for security issues and vulnerabilities. The `category` property helps organize the results by language.

If your project has a custom build process, you might need to replace the Autobuild step with manual build commands to ensure CodeQL can analyze your code correctly.

Example for a Node.js/React project:

Let me know if you want a full example workflow for your stack!

```yaml
    - name: Initialize CodeQL
      uses: github/codeql-action/init@v3
      with:
        languages: ${{ matrix.language }}

    - name: Autobuild
      uses: github/codeql-action/autobuild@v3  

    - name: Perform CodeQL Analysis
      uses: github/codeql-action/analyze@v3
      with:
        category: "/language:${{matrix.language}}"
```

Finally, the whole workflow looks the following:

```yaml
name: "CodeQL Analysis"

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  analyze:
    name: Analyze
    runs-on: ubuntu-latest
    permissions:
      actions: read
      contents: read
      security-events: write

    strategy:
      fail-fast: false
      matrix:
        language: [ 'java' ]

    steps:
    - name: Checkout repository
      uses: actions/checkout@v4

    - name: Setup Java
      uses: actions/setup-java@v4
      with:
        java-version: '23'
        distribution: 'temurin'

    - name: Initialize CodeQL
      uses: github/codeql-action/init@v3
      with:
        languages: ${{ matrix.language }}

    - name: Autobuild
      uses: github/codeql-action/autobuild@v3  

    - name: Perform CodeQL Analysis
      uses: github/codeql-action/analyze@v3
      with:
        category: "/language:${{matrix.language}}"
```

### GitHub Dependabot

GitHub Dependabot is a built-in tool in GitHub that helps you keep your dependencies up to date and secure. It automatically checks your project’s dependencies for outdated or insecure libraries. When it finds a new version or a security vulnerability, Dependabot can automatically create pull requests to update the affected dependencies.

To get practical experience with GitHub Dependabot, it is recommended that you follow the official [Dependabot quickstart tutorial](https://docs.github.com/en/code-security/getting-started/dependabot-quickstart-guide).---

---
### Further Reading
http://codeql.github.com/
