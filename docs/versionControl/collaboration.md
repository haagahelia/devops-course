---
sidebar_position: 2
title: Collaboration
---

In a team environment, effective collaboration is crucial not only for the success of the team, but also for enjoying the work you do. Managing a project with Excel or Google Sheets and sending email attachments may work for a limited time with a small team, but it can become frustrating and inefficient quite quickly.

A good software project management tool and a well defined workflow can help teams to work together more effectively. There are many tools available for managing projects, such as [GitHub Projects](https://github.com/features/issues), [Jira](https://www.atlassian.com/software/jira), and [Trello](https://trello.com/). These tools allow teams to track tasks, assign responsibilities, and monitor progress in a more organized way.

It can be common that the team has a project management tool in place, but the status of individual tasks in the tool is outdated. Discussions about tasks may take place in various places, such as email, Discord, Whatsapp, Slack or one to one meetings. When a task is marked as completed, it may not be obvious how it was completed or how the quality of the work was ensured. Not to mention tasks that have been completed a long time ago, and there is now confusion about why someone added a `sleep(1)` to the code at some point.

Luckily, the tools mentioned above have features that automatically update the status of tasks and connect code changes to the tasks they are related to. Referring to tasks in commit messages, pull requests, and code reviews can help to keep the project tool up to date. For example, you can write a commit message or pull request description `Fixed error in checkout when the shopping cart is empty. Fixes #128.` could mark the referred issue automatically as resolved. See more at [GitHub documentation](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue).

Recommended videos:

- [Using Projects for feature planning (GitHub at YouTube)](https://www.youtube.com/watch?v=yFQ-p6wMS_Y)
- [Learn how to use Project Roadmaps - GitHub Checkout (Github at YouTube)](https://www.youtube.com/watch?v=D80u__nYYWw)

:::info[TASK: Collaborate on a project]
We have set up a GitHub project and a repository for this lecture.

Your task is to fork the repository, create new branches for the tasks assigned to you, and create pull requests for your changes. Make sure to refer to the tasks in your commit messages and pull requests to keep the project management tool up to date.
:::