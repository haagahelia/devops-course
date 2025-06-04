---
sidebar_position: 1
title: Git
---

Git is a distributed version control system that allows multiple developers to work on the same codebase simultaneously without overwriting each other's changes. Since the [creation of Git in 2005](https://git-scm.com/book/ms/v2/Getting-Started-A-Short-History-of-Git), it has become the de facto standard for version control in software development.

To this point you may have learned about the basic commands and workflows of Git, such as `git clone`, `git commit`, `git push`, and `git pull`. That's a great start! These commands are essential for working with Git and are the foundation of version control. However, there is much more to Git than just these basic commands. In this course, we will cover more advanced topics and workflows that will help you become a more effective developer, especially when working in teams.

If you do not feel comfortable with the basic commands of Git, we recommend that you utilize resources such as [the Git documentation](https://git-scm.com/doc) and [Git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf) to fill in the gaps. You can also find many tutorials and courses online that cover the basics of Git.

We will use GitHub as our primary platform for version control and collaboration, but the concepts we cover will apply to other platforms as well, such as [GitLab](https://about.gitlab.com/) and [Bitbucket](https://bitbucket.org/).


## Git branching models and workflows

Git provides a team with a lot of flexibility in how they can work together. Branches, forks, tags, and pull requests are all tools that teams and individuals can use to manage their code changes, but how they apply them depends on the team's workflow and preferences:

> *"Given Git's focus on flexibility, there is no standardized process on how to interact with Git"*
>
> Comparing Git workflows: What you should know. [atlassian.com](https://www.atlassian.com/git/tutorials/comparing-workflows)

For example, a team may choose to all work on the same branch, such as `main`, or they may use separate branches for each feature or fix. Open source projects often use forks to allow contributors to work on their own copies of the codebase, while teams may prefer a shared repository model where all developers have access to the same repository.

Read the following articles at Atlassian.com about Git workflows to learn more about the different approaches and how they can be applied in practice:

- [Git feature branch workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [Gitflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Forking workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)
- [Trunk-based development](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development)



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


## Pull requests and code reviews

Pull requests are a key feature of GitHub and other Git hosting platforms that allow developers to propose changes to a codebase. They provide a way to review and discuss changes before they are merged into the main branch. Pull requests are often used in conjunction with code reviews, where other developers review the proposed changes and provide feedback.

In GitHub, you can create a pull request and assign reviewers to it. Reviewers can then comment on the changes, suggest improvements, and approve or reject the pull request. New commits can be added to the pull request to address the feedback, and once the pull request is approved, it can be merged into the target branch.

Popular repositories can have a large number of pull requests open at any given time, so it is important that there is a clear process for managing them and automated checks that ensure that the code meets at least the minimum quality standards before they are assessed by a reviewer. See, for example, the [pull requests for the open source publishing platform WordPress](https://github.com/WordPress/wordpress-develop/pulls).

Continue by reading about [Collaborating with pull requests at the GitHub documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests).

Recommended videos:

- [Create pull request (GitHub at YouTube.com)](https://www.youtube.com/watch?v=nCKdihvneS0)
- [Merge pull request (GitHub at YouTube.com)](https://www.youtube.com/watch?v=FDXSgyDGmho)

The video about merging a pull request also shows how to resolve a merge conflict, so watching it is highly recommended.