---
sidebar_position: 1
title: Deployment & Delivery
---

In DevOps **CD** stands for: **Continuous Delivery** or **Continuous Deployment**.

Continuous Delivery is a practice where code changes are automatically built, tested, and prepared for release to production.The deployment to production is manual and requires human approval. That ensures the software is always in a deployable state.

Continuous Deployment is a practice where code changes are automatically built, tested, and deployed to production without human intervention.
Every change that passes automated tests is immediately released to end users.

Both practices are part of the broader DevOps philosophy, but the choice between them depends on the organization's need and maturity of automation processes.

In this course, we are focusing on Continuous Deployment.

**Deployment** is the process of delivering software to an environment where it can be accessed and used by end-users. It is a critical phase in the software development lifecycle, as it ensures that the application is functional, reliable, and accessible in production.

There can be different types of Deployment Environments:
- Development Environment: Used by developers to write and test code.
- Testing/Staging Environment: Mimics production for testing purposes.
- Production Environment: The live environment where end-users interact with the application.

Deployment is often automated and automation brings a lot of benefits, such as:
- Consistency and Reliability whic ensures deployments are performed the same way every time, reducing human error. It also eliminates manual steps that can introduce inconsistencies.
- Speed and Efficiency. Due to automation deployments happen faster, allowing teams to release features and fixes more quickly.
- Scalability
- Enables zero-downtime deployment strategies that minimizes disruption to users during updates.

There are several **deployment strategies**, including blue/green deployment and canary deployment. The choice of strategy depends on the organization's business needs and goals. You can learn more about various deployment strategies in this [AWS whitepaper](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/deployment-strategies.html).

Common tools for deployment automation: GitHub Actions,Jenkins, GitLab CI/CD, Azure DevOps, or CircleCI.

Next, we will deploy our sample application that we used in the CI chapter to a cloud provider.