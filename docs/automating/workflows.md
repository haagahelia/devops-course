---
sidebar_position: 2
title: Writing workflows
---

### Writing your first GitHub Actions workflow

Workflows are defined using YAML syntax (https://yaml.org/). Workflow files must have either a `.yml` or `.yaml` extension and they are save to `.\github\workflow` directory in your repository. One way to create workflows is to navigate to your GitHub repository and open the Actions tab. There you can select pre-defined workflows or create your own by clicking 'set up a workflow' yourself as shown in the following image:

![Github workflow creation](./img/github_actions_tab.png)

:::task
Create a new repository to Github and enable `Add a README file` to create `readme.md` file to your repository Then, follow the instructions in https://docs.github.com/en/actions/writing-workflows/quickstart#creating-your-first-workflow to create and run your first Github actions workflow.
:::



- Building CI Pipelines
- Running automated linting & tests
- Debugging failed workflows

Materiaaleja tähän osioon:
- https://github.com/features/actions
- https://www.youtube.com/watch?v=vMhDkt5JNN0 / Secrets
- https://fullstackopen.com/en/part11/getting_started_with_git_hub_actions
