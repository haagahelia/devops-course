---
sidebar_position: 1
title: Introduction to Docker
---

Docker has quickly become a fundamental tool in modern software development. In 2024 StackOverflow developer survey, it was both the [most used](https://survey.stackoverflow.co/2024/technology#1-other-tools) and [most admired tool for compiling, building and testing](https://survey.stackoverflow.co/2024/technology#most-popular-technologies-tools-tech). Docker allows developers to package applications and their dependencies into **containers**, ensuring that they run consistently across different environments. Containers not only ensure that a single application runs the same way on any machine, but they also make it efficient to run multiple applications with different dependencies on the same host without conflicts.

> *"Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker's methodologies for shipping, testing, and deploying code, you can significantly reduce the delay between writing code and running it in production."*
>
> [What is Docker?](https://docs.docker.com/get-started/docker-overview/)

One can use Docker to run production applications, to test applications in isolated environments, or to develop applications locally without worrying about the underlying infrastructure. It can be easiest to start with Docker by using it locally on your own machine, and moving to more complex setups such as cloud deployments later on.

Recommended videos to get started:

* [Docker in 100 Seconds (Fireship)](https://youtu.be/Gjnup-PuquQ)
* [Never install locally (Coderized)](https://youtu.be/J0NuOlA2xDc)
* [Virtual Machine (VM) vs Docker (IBM Technology)](https://youtu.be/a1M_thDTqmU)

Recommended reading:

* [What is Docker?](https://docs.docker.com/get-started/docker-overview/)

:::info[Subscriptions and service agreements]
When discussing containerization, it is important to note that Docker is not the only option available. Docker can be considered as "open" and parts of it are open source. It can, with some limitations, be used without registering an account and without purchasing a subscription, but especially when using Docker professionally, you will need to see [Docker pricing](https://www.docker.com/pricing) and [Docker subscription service agreement](https://www.docker.com/legal/docker-subscription-service-agreement/).
:::


## Docker CLI

Docker provides a command-line interface (CLI) that allows you to interact with Docker and manage containers, images, networks, and volumes. The Docker CLI is a powerful tool that enables you to perform various operations, such as building images, running containers, and managing resources. Docker also comes with a graphical user interface (GUI) called Docker Desktop, and VS Code has Docker extensions that can be used for managing Docker resources. The examples and exercises in this course will use the Docker CLI:

```bash
docker run --help
```

See the [Docker CLI documentation](https://docs.docker.com/reference/cli/docker/) for a all commands and options available in the Docker CLI.


## Dockerfile *(instructions for building an image)*

A Dockerfile is a text file that contains instructions for building a Docker image. It defines the base image, the application code, dependencies, and any other configurations needed to run the application in a container. Dockerfiles are used to automate the process of creating Docker images, making it easy to reproduce and share applications.

See the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/) for a complete list of instructions and options available in Dockerfiles.


## Docker image *(package of software and dependencies)*

A Docker image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and dependencies. Images are immutable, meaning that once they are built, they cannot be changed. This immutability ensures that the application runs consistently across different environments, whether it is on a developer's machine, in a testing environment, or in production. When you run a Docker image, Docker creates a container and adds a writable layer on top of the image. This allows Docker containers to make changes to their own filesystem without affecting the original image or other containers using the same image.

Images are built from Dockerfiles and can be used locally or shared through container registries like Docker Hub or private registries.

See more about [Docker images](https://docs.docker.com/engine/reference/commandline/images/) and [how to build them](https://docs.docker.com/engine/reference/commandline/build/) at the Docker documentation.


## Docker container *(running instance of an image)*

A Docker container is a running instance of a Docker image. It is an isolated environment that contains the code, runtime, libraries, and dependencies. Containers may expose ports to the host machine or mount volumes to share data with the host system. Containers can also utilize networks to communicate with other containers or external services.

See more about [Docker containers](https://docs.docker.com/engine/reference/commandline/container/) and [how to run them](https://docs.docker.com/engine/reference/commandline/run/) at the Docker documentation.


## Docker compose *(multi-container applications)*

Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to define the services, networks, and volumes needed for your application in a single YAML file called `docker-compose.yml`. With Docker Compose, you can easily start, stop, and manage multiple containers.

See the [Docker Compose documentation](https://docs.docker.com/compose/) for more information on how to use Docker Compose, including how to define services, networks, and volumes in a `docker-compose.yml` file. You can also watch the video [Docker Compose will BLOW your MIND](https://youtu.be/DM65_JyGxCo?feature=shared) by NetworkChuck on YouTube.

:::info[TASK: Containerize an application]
Follow the instructions at https://docs.docker.com/get-started/workshop/ to containerize a simple web application step by step. You will learn how to create a Dockerfile, build a Docker image, and run a container from that image. The source code for the application does not require modifications, and it can be found at https://github.com/docker/getting-started-app/.

During the task, you will need to apply knowledge from the [Getting started](https://docs.docker.com/get-started/introduction/) section of Docker documentation.
:::

