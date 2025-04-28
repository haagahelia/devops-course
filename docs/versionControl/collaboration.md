---
sidebar_position: 2
title: Collaboration
---

In Git, you can collaborate with others in a number of ways. Typically you will be using separate branches for each feature or bug fix, but you may also use forks, pull requests and other practices to manage code changes. In this section we will cover different strategies for collaboration and their common use cases.


## Forks vs. shared repositories

> *"The way you use pull requests depends on the type of development model you use in your project. You can use the fork and pull model or the shared repository model."*>
>
> [About collaborative development models (GitHub)](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models)

A typical way for a small team to work together is to use a *shared repository*. In this case, the developers are known to each other and have access to the same repository. This is the most common way to work with Git, and it is the easiest way to get started. In the shared repository, each feature or fix is typically implemented in a separate branch first, and then merged into a development or main branch after the work is done. This is a common workflow in small teams, where all developers have write access to the same repository.

> *"A fork is a new repository that shares code and visibility settings with the original "upstream" repository. Forks are often used to iterate on ideas or changes before they are proposed back to the upstream repository, such as in open source projects or when a user does not have write access to the upstream repository."*
>
> [Fork a repository (GitHub)](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)

In larger teams or open source projects, it is common that each contributor creates their own copy, or *fork*, of the repository. This allows new developers to work on the codebase without having write access to the original repository. The forks are connected to the original repository, and any changes made in a fork can be proposed back to the original repository using a **pull request**. This is a common workflow in open source projects, where contributors may not have direct access to the original repository.

:::info[Have you used forks or shared repositories?]
You may have encountered both of these strategies in your own work. If you have worked on a project with a small team, you have likely used a *shared* repository.

On the other hand, when you have completed exercises in GitHub classroom, you have been given your own personal copy, or a *fork*, of the shared exercise repository.
:::


## Pull requests

Pull requests enforce a review process for code changes. They allow you to propose changes to a codebase and have them reviewed by other developers before they are merged into other branches. This is a good practice both in open source projects and in teams, as it allows for code reviews and discussions about the changes before they are merged. Pull requests also allow you to see the differences between your branch and the target branch, which can help you understand the impact of your changes.
