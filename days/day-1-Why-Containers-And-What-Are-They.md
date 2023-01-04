## Before There Were VMs...

As with every new year that passes, new engineers and IT pros come into the industry. Whether they’re breaking into it right out of college or they decided to skip college and go straight to work. In any case, as with every new person comes fewer people that have worked in “older” infrastructure.

When engineers come into the world of tech now, they see a lot of:

- Containers
- Orchestration
- Automation

and overall abstraction.

Folks that are coming into tech in today’s world don’t want to sit on a datacenter floor and wire cables through various switches and routers. They don’t want to change out RAM on a server or dive into virtualization software.

They want to dive into the latest and greatest (cloud, containers, Kubernetes, etc.) and for good reason - because it’s the “hot” thing right now… and the “hot” thing leads to a better chance of getting a good job.

Although that’s fine, it can leave a lot to be desired for truly diving deep into containerization and orchestration.

Why?

Because the truth is - containers, Kubernetes, the cloud… it’s all based on (what feels like legacy in today’s world) legacy systems.

For example, servers are still servers in Kubernetes. Networking is still networking in Kubernetes. Storage is still storage in Kubernetes. Kubernetes isn’t creating any new foundations. It’s simply abstracting foundations, but you still need to know them.

Think about it like this…

Do you need to wire routers and switches in a datacenter if your organization is cloud based? No. Do you have to spend 18 hours in a datacenter solving network issues plugged into a Cisco router? No. Are the same problems we were solving plugged into a Cisco router for port issues in a datacenter the same port issues you’ll see in Kubernetes? **Yes**. Ports are ports. Routes are routes. Firewalls are firewalls.

Point being - the fundamentals and the foundation are still needed. Otherwise, you’re going to cause a massive amount of confusion to yourself.

That’s why I propose this…

Before moving on in this series, go through the blog post I wrote found here ([https://dev.to/thenjdevopsguy/prerequisites-to-learning-and-understanding-kubernetes-583p](https://dev.to/thenjdevopsguy/prerequisites-to-learning-and-understanding-kubernetes-583p)) and ensure that you’re at least 50% good with each of these topics. 

## What Are Containers
The flow, from a containers perspective (not counting Serverless), has gone something like:

Bare metal --> VMs --> Containers

Virtual Machines (VM) were revolutionary. VMs took bare metal servers that were typically at way less capacity than they could’ve been at (for example - buying an entire server for it to only run at 30% capacity), which resulted in a waste of resources and gave you the ability to use the wasted resources. Instead of having an application running on one bare metal server, you could have multiple virtual machines running on the bare metal server.

VMs virtualized hardware.

Containers, on the other hand, virtualize operating systems.

Where-as with virtual machines you had an entire operating system running with all of it’s bells and whistles, containers take operating systems and virtualize them by turning them into micro-sized bits that only run what they need to run.

For example, if you use an Ubuntu container image (more on container images another day), and you try to run basic Linux commands, some will work and some won’t. Why? Because the commands that don’t work aren’t needed for the container to run an application.

Speaking of applications - containers also virtualize the application level. A container takes every dependency needed for your application to run, along with the app itself and the commands needed to make it run, and runs it. You no longer need a full bare metal server or a virtual machine to run an application.

Now all you need to do is package it up into a container.

Containers have a lot of benefits:

- Way smaller form factors compared to a virtual machine.
- The ability to essentially “pick up” and run anywhere.
- Package up all dependencies and anything else you need to run your app, all while being in the size of megabytes.
- Better security as you as the engineer get to pick and choose what’s going to be in the container vs an operating system on a VM that you must abide by what’s installed by default (unless you write your own Linux kernel).
- Isolation. Containers give you the ability to isolate workloads that are running. You no longer have to worry about how many applications are running on a VM. Instead, they’re all running in separate containers.

Containers work in isolation and by specifying resources for each container by taking the Linux primitives - cgroups and namespaces.

**cgroups** give you the ability to specify how many resources you want a container to have. For example, a container can have X amount of memory and X amount of CPU. As you get to the Kubernetes piece, you’ll learn about requests, limits, and quotas, which directly utilize cgroups as well.

**Namespaces**, not to be confused with Kubernetes Namespaces (although it’s where k8s gets Namespaces from), allow you to isolate workloads and segregate them. It partitions Linux resources in a way that one set of processes see’s an entirely separate set of processes. Those “processes”, in this case, are containers.

## Container Use Cases
Here’s the thing about containers - sometimes they may not fit what you’re looking for.

Arguably, and usually, they do, but sometimes they don’t.

For example, using Serverless or Wasm (Web Assembly) may be a better option for your particular use case. It really all depends on what you’re trying to do.

Because of that, here are some good use cases where containers come into play.

1. Faster testing
2. Faster development
3. Utilized across multiple systems
4. Orchestration

From a testing perspective, there’s no denying that running a container locally to test a particular set of functionality is a far superior option in comparison to creating an entire virtual machine, installing/updating everything needed on the virtual machine, and then testing the application. Not only are containers faster in this instance, but they take up a lot less real estate. Same rules apply for faster development. If you have the smallest form factor to test and build functionality compared to needing a VM to do the same thing, development is far quicker.

Another huge use case with containers is that they’re usable across literally any system. Windows, and distribution of Linux, and any cloud. In fact, most (at least the big) cloud providers have services specifically to run containers. Once a container is built, it can run anywhere. It’s vendor agnostic.

Last but certainly not least, orchestrating containers is a far superior option from an ease of use perspective (containers and orchestration isn’t easy, it’s just more straightforward) in comparison to running applications on a VM. Orchestration systems give engineers repeatability that they don’t even have to build (self-healing, scheduling, declarative interaction, etc.).

In short, containers are great if you want to develop and test fast.

## Containers On Linux and Windows
As mentioned above, containers can run on both Windows and Linux. Typically, you’ll see containers running as Linux containers, but Windows containers still very much exist and are still being developed (I recently did a podcast episode with two engineers at Microsoft that focus on Windows containers).

You’ll usually see Windows containers for legacy applications as many new apps from a “Windows” perspective are built with .NET Core and other open-source systems.

Unless you’re building for a specific use case (like a legacy Windows app or an ARM app), you should default to Linux containers as they are the most widely adopted.

## Where Do Microservices Fit In?
Microservices should most likely be an entire day in this series in itself. However, this series isn’t necessarily geared towards microservices (maybe there should be a series that is?).

Sometimes you’ll see containers and microservices put into the same category.

The truth is, that’s simply not the case. You can run containers that aren’t a microservice. In fact, many containers that you see out there aren’t microservices.

Microservices, in short, are applications that don’t have dependencies on other parts of an application to run properly.

It’s often defined as “loosely coupled”.

Microservices are all about having independent services.

It allows for updating and working on a particular part of an application much easier. It also makes deploying a new version of the application much easier. One of the biggest benefits for microservices is that you can deploy one part of the app without touching the other part of the app, which results in not having to update the entire stack at the same time.