## Why Security

Often times security is looked at as this massive overhaul that’s going to take years to complete and millions of dollars.

Here’s the reality…

You can download a hardening guide for free, take a day, and remove several mitigation risks just by following the hardening guide.

Did I just oversimplify security? Absolutely. Can you actually do what I just said? Absolutely.

In a ton of environments, the biggest security issues come down to the most low hanging fruit. Patching, updates, permissions, and basic scans.

Security isn’t about stopping everything possible because that’s impossible.

Security is about mitigating as much risk as possible. You can NEVER stop every single risk and every single attacker. It’s not possible. However, you do have the ability to mitigate as much as you can.

## Docker Security

Containers, by default, are not secure. Everything and anything can go wrong from the host running the container runtime being compromised to the code that's inside of the container being compromised. There are various obstacles and entry points where a container can become insecure.

When thinking about Docker security, think about overall security in general.

Does whoever needs access have proper access?

Do they have too much access?

Is the network secure?

Is the host secure?

Are proper security processes for the organization being met?

Remember, containers or not, security is still security. Just because it’s a container doesn’t mean the container network is any less of a network. The network still has ports, IPs, and firewalls that can be breached.

Point being - don’t overthink it because it’s a container. Think about it in a similar fashion that you would with standard infrastructure and security. A lot of the best practices carry over.

However, there are a few key best practices that you should think about.
1. Rootless mode
2. Scan your container images
3. Ensure resource utilization is limited
4. Ensure that the host running the container runtime is secure
5. Use benchmarks: https://www.cisecurity.org/benchmark/docker

Rootless mode makes it possible to run the Docker daemon and any containers as a user that isn’t root to mitigate vulnerabilities in the daemon and the container runtime.

Scanning container images is a method that allows you to run a security scan against a container image. There are various tools out there that help with this and they all mostly either use CIS (which you’ll learn about later), NIST, or the National Vulnerability Database (NVD).

Resource utilization and ensuring that the container resources are limited comes down to the container only utilizing the resources that it needs. If you know an application only needs 2MB of RAM and the RAM ends up spiking up to 2GB, that could be a million things (like a memory leak) or a bad actor in your code.

Any hosts that are running the container runtime should be secure. This goes without saying, but hosts are hosts. They have operating systems. They have security risks by default. Ensure that they’re as secure as possible.

Benchmarks, which will be explained next, are a great place to start when hardening any system. Even if you aren’t running containers, CIS is the defacto standard for securing and hardening any system (and yes, containers are systems).

## CIS Benchmark

CIS is always a great place to start. It's essentially a curated list of best practices for security that you can implement.
Download the report at the link below and read through it.

When thinking about the outcome that you’ll see within the Docker Benchmark, understand that every organization has different thresholds for how much security they want to implement. Some organizations are fine with the minimum. Other organizations have compliance needs that they need to meet. Some organizations will always be more secure than the other. Because of that, when you’re implementing security practices, it’s all going to come down to what your organization needs. Think about the business first.

https://www.cisecurity.org/benchmark/docker

## Running Containers In Rootless Mode

Running containers in Rootless mode is a different setup for every environment, as in, every Linux distribution. Because of that, it’s best to just take a look at the link below so you can set up rootless mode based on the environment.

[https://docs.docker.com/engine/security/rootless/#:~:text=To run Rootless Docker inside,%3A-dind .&text=The docker%3A-,%2C AppArmor%2C and mount masks](https://docs.docker.com/engine/security/rootless/#:~:text=To%20run%20Rootless%20Docker%20inside,%3A%2Ddind%20.&text=The%20docker%3A%2D,%2C%20AppArmor%2C%20and%20mount%20masks).

As an example, let’s see how to do it in Ubuntu.

First, if the Docker Daemon is already running, disable it.

```jsx
sudo systemctl disable --now docker.service docker.socket
```

If you have Docker 20.10 or later, you should have `dockerd-rootless-setuptool.sh` in `/usr/bin`.

Run the following as a non-root user to run the Daemon as non-root.

```jsx
dockerd-rootless-setuptool.sh install
```

Lastly, install Docker CE as rootless.

```jsx
sudo apt-get install -y docker-ce-rootless-extras
```