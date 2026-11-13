---
sidebar_position: 5
title: Agentic workflows
---

### GitHub Agentic Workflows

[GitHub Agentic Workflows](https://github.github.com/gh-aw/) are a way to automate software development and repository maintenance tasks using AI agents and GitHub Actions.

Traditional workflows follow predefined instructions. They do exactly what the developer has programmed them to do. Agentic Workflows take this idea further by introducing AI agents into the automation process. Instead of programming every individual step, developers can describe a task using natural language. An AI agent then interprets the instructions, examines the repository, makes decisions and performs the requested work using the tools available to it.

#### How GitHub Agentic Workflows work?

##### 1. Instructions

The developer describes the task in a markdown file (md) using natural language. The markdown file is then compiled to `.lock.yml` file for GitHub actions workflow.

Example markdown file:

```yaml
---
on:                        # Trigger: when to run
  issues:
    types: [opened]

permissions: read-all      # Security: read-only by default

safe-outputs:              # Allowed write operations
  add-comment:
---
# Issue Clarifier

Analyze the current issue and ask for additional details if the issue is unclear.
```
The frontmatter (YAML configuration section between --- markers) of GitHub Agentic Workflows includes the triggers, permissions, AI engines (which AI model/provider to use), and workflow settings. 

##### 2. AI agent
AI coding agent reads the instructions, examines the repository and uses available tools to complete the task.

##### 3. Result
The agent produces results, such as an analysis, a comment, a report or a proposed code change. Depending on the configuration, it can also create GitHub issues or pull requests.

### Security

Giving AI agents access to a software repository introduces security risks. For example, an AI agent might encounter malicious instructions in an issue description or source code.

GitHub aw addresses this with several security mechanisms:
* Agent execution takes place in an isolated environment (sandboxing). 
* Agents are read-only by default. 
* Agents use GitHub permissions to publish the result (safe output).

### Workshop

GitHub provides a practical, hands-on workshop that introduces GitHub Agentic Workflows by guiding you through the implementation of your own AI-powered workflow. 

https://githubnext.github.io/gh-aw-workshop/