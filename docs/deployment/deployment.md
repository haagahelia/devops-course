---
sidebar_position: 2
title: CD pipeline
---

### Deployment 

We will do our first deployment to Render.com (https://render.com) that provides free Hobby plan for small-scale applications. There are some limitations in free plan that you should be aware. The deployments are much slower when using free plan and free instances will spin down with inactivity, which can delay requests by 50 seconds or more. We are going to deploy the Node Express app that we used in the CI pipelines chapter earlier. 

First, you have to create an account to Render.com in https://dashboard.render.com/register. After you have sign-in to Render, select **New --> Web Service** in your workspace.

Next, you can select public GitHub repository where your project is hosted and press the **Connect** button.

In the web service form select the following:

| Language | Node |
| Branch | main |
| Build command | npm install |
| Start command | npm start |

In the Instance Type select **Free** option

Finally, press the **Deploy** button. After the deployment starts, you will be redirected to a page where you can see the deployment log. Wait until, you get the message that your service is live:

![Render.com deployment log](./img/deployment_log.png)

As you can see the deployment to modern hosting providers is really straigthforward.

By default, Render automatically deploys your service whenever you update its code in linked GitHub repository. Opent the `app.ts` file and change the message that is displayed when you navigate to the root endpoint:

```ts
app.get('/', (req, res) => {
  res.json({ message: 'Calculator API is running on Render.com' });
});
```
Push your changes to the repository and see that the GitHub actions workflow fails. 

![Failed test](./img/failed_test.png)

One of the tests does not pass, yet the application is still automatically deployed to Render.com. **Deployments should only occur after all linting and tests have successfully passed.**.


### CI/CD Pipeline

In this phase we will modify our GitHub actions workflow so that deployment is done only after linting and tests are passed.

First, we will disable automatic deployment from the Render.com web service. Navigate to the settings page of your web service and select **No** from the **Auto-Deploy**.

![Auto deployment](./img/auto_deploy.png)

Next, we will modify our Github actions workflow.


- Deployment & Delivery (CD)
- Automated Deployments with GitHub Actions
- Building CI/CD pipelines
- Deploying to cloud providers (Rahti ?)
- Kubernetes??
- Versions (should it be in CI?) 


Render: https://render.com/docs/web-services
https://render.com/docs/deploy-node-express-app

Github pages:
- https://docs.github.com/en/actions/security-for-github-actions/security-guides/automatic-token-authentication
- https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/controlling-permissions-for-github_token#:%7E:text=pages%3A%20write%20permits%20an%20action%20to%20request%20a%20GitHub%20Pages%20build

Rahti: