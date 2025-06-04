---
sidebar_position: 5
title: Write actions
---

So far in this course, we've used pre-built GitHub Actions from the GitHub Marketplace to automate tasks in our CI pipelines. These actions are excellent for common use cases, but sometimes your workflow needs something more specific or flexible. That's where writing your own GitHub Actions becomes powerful.

Here are a few reasons to create your own GitHub Action:
- When no existing action does exactly what you want.
- Package your logic once, then use it across projects.
- Hide complex logic behind a simple interface.

There are two main types of actions you can write:

1. JavaScript actions
- JavaScript actions runs directly on the GitHub-hosted runners. They use Node.js and npm packages.

2. Docker container actions
-  Run in a Docker container. Good for custom environments or using tools not available on the runner.

In this course, we’ll start with JavaScript Actions, as they're simpler to set up and work well for most cases.

The basic custom JavaScript action structure looks the following:

```mermaid
my-action/
├── action.yml       # Metadata and definition of the action
├── index.js         # Your JavaScript logic
└── package.json     # Dependencies (optional)
```

The key file is action.yml and it defines your action’s inputs, outputs, and main entry point.

:::info[TASK: Your first JavaScript action]

To get hands-on experience creating your own GitHub Action, you'll complete an interactive tutorial provided by GitHub.

1. Navigate to GitHub skills: https://skills.github.com/. 
2. Find and click on **Write JavaScript Actions**.
3. Follow the step-by-step tutorial in your own GitHub account.

:::

