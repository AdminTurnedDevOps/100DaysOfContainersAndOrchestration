## Container Engine

If you want to run a container, there must be a method of how containers can run that’s running on your current system. Whether that “current system” is your local laptop/desktop, a server, or the cloud. The method of a container having the ability to run (not the method of a container running, which you’ll learn about in the next section) is the container engine.

The container engine allows everything from:

- User requests with a CLI (like the Docker or Podman CLI)
- The ability for images to be cloned and pulled down to a system

and many other pieces to the containerization puzzle.

However, keep in mind, the container engine does not run a container. It just gives the ability to run a container on a system.

If you want to run a container, you need a container runtime.

## Runtime Theory

Container runtimes, well… you guessed it, run containers. What does the actual process look like though?

However, containers aren’t just “magically there” on a server. They’re compromised of several components that make it all work:

- Namespaces
- Cgroups
- Linux Security Modules (LSM)

The runtime is what’s responsible for running the container. Without it, a container wouldn’t exist. The same goes for Kubernetes. If there wasn’t a container runtime in a Kubernetes cluster, the container wouldn’t have the ability to run.

You’ll be diving more into this later on in the series, but at a high level, let’s look at the screenshot below running the `docker run` command.

![Screenshot](1.png)

What is this command doing in the background? How is a container actually running? 

First, as you can see on the screenshot above, a container image is pulled. A container image is built off of a certain standard, which you’ll learn about in an upcoming section.

As the image is being pulled, it’s running all of the commands and entrypoints and anything else that makes up the container image (you’ll learn more about creating a container image another day).

The container image is then saved/mounted on the operating system.

Before the container starts, cgroups and namespaces are used for segregation and resource limits/constraints (see Day 1 for more information about cgroups and namespaces). The kernel is alerted of the container attempting to start, which is when cgroups and namespaces kick into action.

SELinux policies and AppArmor policies are then configured.

And just like that, a container is up and running.