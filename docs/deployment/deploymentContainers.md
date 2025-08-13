---
sidebar_position: 3
title: Deployment using containers
---


Containers are a popular way to deploy applications in the cloud. As discussed earlier, they provide a lightweight and portable way to package applications and their dependencies, making it easier to deploy and manage them across different environments.

Most cloud providers offer different types of container based services to deploy your applications. These services can be used to run your containerized applications in a scalable and reliable way. There are both managed and self-managed options available, depending on your needs. In a managed service, the cloud provider takes care of the underlying infrastructure, while in a self-managed service, you are responsible for managing the infrastructure yourself. Examples of managed services include [Azure Container Instances](https://azure.microsoft.com/en-us/products/container-instances), [Amazon Elastic Container Service](https://aws.amazon.com/ecs/), and [Google Cloud Run](https://cloud.google.com/run). Self-managed options include Kubernetes clusters, examples of which are [Azure Kubernetes Service](https://azure.microsoft.com/en-us/services/kubernetes-service/), [Amazon Elastic Kubernetes Service](https://aws.amazon.com/eks/), and [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine). Private clouds are also an option, such as [CSC Rahti](https://rahti.csc.fi/), which is a container platform provided by the Finnish IT Center for Science (CSC).


## Container registries

The cloud providers also offer their own container registry services. These registries are used to store and manage container images, which can be used to deploy applications in the cloud. Container registries are similar to code repositories, but they are specifically designed for storing container images. They provide a way to version and manage container images, making it easier to deploy and update applications.

* [Docker hub](https://hub.docker.com/)
* [Azure Container Registry](https://azure.microsoft.com/en-us/services/container-registry/)
* [Amazon Elastic Container Registry](https://aws.amazon.com/ecr/)
* [Google Container Registry](https://cloud.google.com/container-registry)
* [GitHub Container Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry)


## Pushing images to a registry

To push a local Docker image to a container registry, you typically need to authenticate with the registry, tag the image with the registry's URL, and then push the image. Individual steps vary depending on the registry, but the general process is similar across different registries.

Docker has a concise [guide on how to push images to a registry](https://docs.docker.com/get-started/introduction/build-and-push-first-image/) that covers the basic steps. Meanwhile, GitHub container registry encourages building and pushing images using GitHub Actions, which you can find more information on their [documentation](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry).


## Deploying containers

Once an image has been published to a container registry, it can be deployed to a cloud service as a container. Again, the process of deploying a containerized application varies depending on the cloud provider and the service being used, but generally involves specifying the image to be used, configuring any necessary environment variables or secrets, and defining the desired scaling and networking options.

For example, [Render.com](https://render.com/docs/deploying-an-image) provides a simple way to experiment with deploying containerized applications. You can create a new service, select the "Docker" option, and then specify the image to be used.


## Triggering deployments on new images

To automate deployments when a new image is pushed to a container registry, you can use different types of integrations, webhooks and CI/CD pipelines. Many cloud providers use their own proprietary integrations to detect changes and trigger deployments, but some also support webhooks. A webhook is simply an HTTP address that can be called to trigger an action, such as start a new deployment. The advantage of webhooks is that they can be simple to set up and do not necessarily require complex authentication mechanisms:

For example, [Render.com allows you to set up a webhook](https://render.com/docs/deploy-hooks) that triggers a deployment when a new image is pushed to the registry:

```bash
# You can test the webhook with curl:
curl https://api.render.com/deploy/srv-xyz...

# Do not store the hook URL in version control, as it could be
# used by unauthorized users to trigger deployments.
#
# Instead, use GitHub secrets or other secret management tools:
curl "$deploy_url"
```

See https://render.com/docs/deploy-hooks for more information about their deployment hooks. Render.com also provides [a sample GitHub action](https://render.com/docs/deploy-hooks#example-workflow) that can be used to trigger deployment.
