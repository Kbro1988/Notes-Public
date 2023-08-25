<!-- omit from toc -->
# Application Container Engine

Containers allows us to build our application into an isolated self-contained binary.

Containers remove the barrier between your development and runtime environments.

Key elements:

- Dependency packaging
- Efficient packaging
- Isolated runtime
- Host platform

Containers are not virtual machines.

- Where VMs include an entire operating system, containers share an underlying OS.
- VMs can run on bare metal (type 1 hypervisors) and can run directly on hardware.
  - Containers need to have that underlying OS already installed.
- VMs are considered ‘heavy’ where containers are ‘light.'

<!-- omit from toc -->
## Content

- [Docker](#docker)
- [Kubernetes](#kubernetes)
  - [Kubernetes Pod](#kubernetes-pod)
  - [Kubernetes Cluster](#kubernetes-cluster)

## Docker

- Docker is a popular and recommended container engine.
- While installing and managing Docker on the CLI, it is free; however, the hard-client application is licensed ($$$).

- Recommendations:
  - Build and share containers using [source control (git)](git.md).
  - Do not build containers as `root`. Instead, create a new user:

   ```unix
   adduser <USERNAME>
   usermod -aG sudo <USERNAME>
   su - <USERNAME>
   ```

  - When composing the docker file, use `ENTRYPOINT` instead of `COMMAND`.

## Kubernetes

- Allows us to orchestrate containers or deploy them over many, many servers (referred to as ‘nodes’).

- Manages efficient distribution through load-balancing algorithms across nodes.

- Roll out updates easily to applications.

> [!NOTE]
>
> Realistically, Kubernetes can be very complex to use and manage. Similar to NSO.

### Kubernetes Pod

- A container for a container image.

- Pods can house more than one container (but typically you’ll only have 1 container per 1 pod).

- Pods are deployed on nodes.

### Kubernetes Cluster

- A collection of pods.

- Kubernetes handles the job of deploying a cluster out to nodes.

**[- Back to Top -](#content)**

---

**[- Notes / NetDevOps -](netdevops.md)**

**[- Notes / Home -](../..)**
