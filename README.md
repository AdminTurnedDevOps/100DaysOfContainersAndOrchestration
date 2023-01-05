<p align="center">
 <img src="images/100Days.png?raw=true" alt="100Days Logo" width="50%" height="50%" />
</p>

# 100DaysOfContainersAndOrchestration
Your go-to open source repo to learn containers (Docker, Podman, etc.) and Orchestration (Kubernetes, ECS, etc.) from start to finish.

[![GitHub Repo stars](https://img.shields.io/github/stars/AdminTurnedDevOps/100DaysOfContainersAndOrchestration)](https://github.com/AdminTurnedDevOps/100DaysOfContainersAndOrchestrations)

## WIP
More to come! This project is a WIP (started January 3rd, 2023). Please note that the days are listed below, but are not completed yet.

## Why?
Containers, orchestration, and the overall landscape of running modern applications is changing.

When I first started working in tech, the innovative thing was to have a bunch of bash scripts, batch scripts (yes... batch), and PowerShell scripts run workloads.

We would put a couple of binaries (compiled code) on a server, run some commands or scripts to get them started, and boom... our app was up and running.

Now? We don't even need a dedicated bare-metal server to run our code anymore (wow... I've been working in tech for a long time).

Instead, we can just take a micro-sized binary (a container) and run it anywhere (even on our local computer).

So, why am I creating this project?

For a few reasons:
1. I've seen the transition from bare-metal to VMs to containers.
2. It's clear that containers are how we're running workloads today.
3. There are A LOT of different avenues you can do down when running containers.

The third reason above is the big reason why this open-source project is so important.

There are A LOT of ways to run and orchestrate containers in today's world... and it's not just Kubernetes.

There's also multiple different runtimes to run containers...

The reason for this project is to help you dive deep into all of the different avenues you can take to run containers.

## How?
100 Days Of Containers and Orchestration will be from both a theoretical perspective and a hands-on perspective.

The truth is that you cannot have one without the other.

You can't implement a solution if you don't understand it or know the "why" behind it.

An example of this is...

Kubernetes is the latest and greatest right now and you want to learn it, but why? Why do you need to learn it in today's cloud-native world?

Or beter yet, why does your organization need to use Kubernetes? Do they actually need Kubernetes? Is there another solution that gives you the same result as Kubernetes in an easier fashion?

As you're going through 100 Days Of Containers and Orchestration, yes, you'll learn the technical pieces and see/use the code... but you'll learn something even better.

The "why" and the "how" that'll help you in implementing a solution like containers and orchestration platforms.

## The App
100 Days Of Containers And Orchestration will be a lot of theory and hands-on components for deploying containers and orchestration, but to deploy a container, you need an app.

The app that will be used is the GoWebAPI that I built. It's a web API that can be run anywhere.

You can find it [here](https://github.com/AdminTurnedDevOps/GoWebAPI)

Don't worry about doing anything with the app right now as you'll learn everything that you need to do with the app throughout this project.

## Days
- [Day 1 - Why Containers And What Are They?](https://github.com/AdminTurnedDevOps/100DaysOfContainersAndOrchestration/blob/main/days/day-1-Why-Containers-And-What-Are-They.md) COMPLETE
- [Day 2 - Container runtimes](https://github.com/AdminTurnedDevOps/100DaysOfContainersAndOrchestration/blob/main/days/day-2-container-runtimes.md) COMPLETE
- [Day 3 - Getting Started With Docker on Linux and Windows](https://github.com/AdminTurnedDevOps/100DaysOfContainersAndOrchestration/blob/main/days/day-3-Getting-Started-With-Docker-on-Linux.md) COMPLETE
- [Day 4 - Docker desktop]()
- [Day 5 - Building Container Images]()
- [Day 6 - Running containers]()
- [Day 7 - Docker networking]()
- [Day 8 - Docker storage]()
- [Day 9 - Docker security]()
- [Day 10 - Docker registries]()
- [Day 11 - Docker Compose]()
- [Day 12 - Docker Swarm]()
- [Day 13 - Scanning docker containers and images]()
- [Day 14 - Podman getting started]()
- [Day 15 - Podman storage]()
- [Day 16 - Podman networking]()
- [Day 17 - Podman desktop]()
- [Day 18 - Monitoring containers]()
- [Day 19 - Containerd]()
- [Day 20 - Why Kubernetes (and why orchestration in general)]()
- [Day 21 - Orchestration home lab (Minikube and Docker Desktop) ]()
- [Day 22 - Running Kubernetes on-prem with Kubeadm]()
- [Day 23 - Kubernetes control plane]()
- [Day 24 - Kubernetes worker nodes]()
- [Day 25 - GKE Part 1]()
- [Day 26 - GKE Part 2]()
- [Day 27 - EKS Part 1]()
- [Day 28 - EKS Part 2]()
- [Day 29 - AKS Part 1]()
- [Day 30 - AKS Part 2]()
- [Day 31 - GKE Autopilot]()
- [Day 32 - EKS Fargate]()
- [Day 33 - AKS with virtual kubelet]()
- [Day 34 - EKS with virtual kubelet]()
- [Day 35 - Kubernetes Deployments, DaemonSets, and StatefulSets]()
- [Day 36 - Kubernetes Namespaces]()
- [Day 37 - Kubernetes ConfigMaps and RollingUpdates]()
- [Day 38 - Kubernetes storage (PVC, PV, SC)]()
- [Day 39 - Kubernetes networking part 1 (general k8s networking)]()
- [Day 40 - Kubernetes networking part 2 (Service mesh and ingress)]()
- [Day 41 - Kubernetes networking part 3]()
- [Day 42 - Kubernetes plugins]()
- [Day 43 - Scaling Kubernetes in the cloud]()
- [Day 44 - Kubernetes disaster and recovery]()
- [Day 45 - Monitoring Kubernetes]()
- [Day 46 - Observability and Kubernetes part 1 (logging)]()
- [Day 47 - Observability and Kubernetes part 2 (tracing)]()
- [Day 48 - Observability and Kubernetes part 3 (metrics)]()
- [Day 49 - OpenTelemetry]()
- [Day 50 - Kubernetes security part 1 (cluster security - Cluster hardening and control plane components)]()
- [Day 51 - Kubernetes security part 2 (Pod security - NetworkPolicies)]()
- [Day 52 - Policy enforcement (OPA)]()
- [Day 53 - Policy enforcement (Kyverno)]()
- [Day 54 - Kubernetes secrets]()
- [Day 55 - Vault and Kubernetes]()
- [Day 56 - Kubescape]()
- [Day 57 - Aqua Security kube-bench]()
- [Day 58 - CIS]()
- [Day 59 - Authentication]()
- [Day 60 - Third party OIDC solutions]()
- [Day 61 - RBAC]()
- [Day 62 - Resource optimization]()
- [Day 63 - Cost optomization]()
- [Day 64 - GitOps Part 1]()
- [Day 65 - GitOp Part 2]()
- [Day 66 - GitOps part 3]()
- [Day 67 - Helm]()
- [Day 68 - Kustomize]()
- [Day 69 - Deploying Kubernetes clusters with Terraform]()
- [Day 70 - Deploying Kubernetes clusters with GitHub Actions]()
- [Day 71 - Deploying Kubernetes clusters with (insert another CICD tool here)]()
- [Day 72 - Portainer]()
- [Day 73 - Rancher]()
- [Day 74 - Upgrading Kubernetes on-prem]()
- [Day 75 - Upgrading Kubernetes in the cloud]()
- [Day 76 - Troubleshooting Kubernetes Pods]()
- [Day 77 - Troubleshooting Kubernetes clusters]()
- [Day 78 - Chaos engineering]()
- [Day 79 - Running Kubernetes in the cloud without a managed service]()
- [Day 80 - Microk8s]()
- [Day 81 - k3s]()
- [Day 82 - ECS]()
- [Day 83 - GCP Cloudrun]()
- [Day 84 - Azure Container Apps]()
- [Day 85 - Azure Container Instance]()
- [Day 86 - Crossplane]()
- [Day 87 - Azure Arc]()
- [Day 88 - OpenShift part 1]()
- [Day 89 - OpenShift part 2]()
- [Day 90 - OpenShift part 3]()
- [Day 91 - Migrating VM apps to containers]()
- [Day 92 - Nomad part 1]()
- [Day 93 - Nomad part 2]()
- [Day 94 - Hybrid Kubneretes part 1 (Azure Stack HCI)]()
- [Day 95 - Hybrid Kubernetes part 2 (EKS Anywhere)]()
- [Day 96 - Hybrid Kubernetes part 3 (GCP Anthos)]()
- [Day 97 - cloud native buildpacks]()
- [Day 98 - Skaffold]()
- [Day 99 - Where to go from here]()
- [Day 100 - Getting a job working with containers and orchestration]()