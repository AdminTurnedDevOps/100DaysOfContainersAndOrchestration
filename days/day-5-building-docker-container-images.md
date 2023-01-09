## What Are Docker Container Images
There are several ways to build container images:
- Skaffold
- Cloud Native Buildpacks
- Docker

and a few other methods.

In this section, you're going to learn about building container images with Dockerfiles because the Dockerfile method continues to be the most popular in organizations.

So, what are Container Images?

In short, container images are packaged up binaries of your code.

Think about what it takes to run an application. You must have:
- Dependencies
- Particular ports open
- Some type of base/golden image to run the application on
- The application binary itself running on the server
- Any commands that are needed to run the app

Inside a Dockerfile, it's not much different. You'll have a base image that you're building your container image off of, ports that are needed to run the app, any dependencies/prerequisites to run the app, and the application binary itself.

**An important note** about base images is that they aren’t full-fledged operating systems. They’re more like “watered-down” versions of an OS. A lot of the time, simple commands that you’re used to running on an OS won’t work on a container. Why? Because it was removed as it wasn’t needed to run an app workload.

The different is that all of the above isn't running on a server. It's "installed" or "copied" to a container image, which is a bite-sized chunk compared to VMs.

If you have an infrastructure background, a Docker Image can be thought of as a golden image. It holds everything you need to run the application/workload of your choosing.

## Showcasing An App

## Dockerfile Properties/Instructions
Below goes over the usual properties that you’ll see in a Dockerfile. For the full explanation, check out the link found [here](https://www.notion.so/Day-5-49a95a177e834146afb31de6cdbc61f8).

### FROM

`FROM` sets the base image for the container image that you’re building. Just like you need an operating system on a server to run any workload, you need a base image for the container image that you’re building. You can use a specific image, for example, a `golang` image for a Go app, or you can use a more universal option like the `ubuntu` base image.

### RUN

`RUN` has two methods:

- Run from a Shell (i.e. `/bin/bash`)
- Run an executable/binary

`RUN` executes commands in a new layer on top of the current image and it commits the results to the container.

### CMD

`CMD` works very similarly in terms of exception like the `RUN` command does, and it also allows you to input parameters at runtime.

The difference between `CMD` and `RUN` is an image build step. Once `RUN` is run, the results will be committed to the container image.

`CMD` is the command the container executes once the container is started. There can only be one `CMD` per Dockerfile.

### LABEL

`LABEL` adds metadata to the container image. For example, specifying a key/value pair like `version=1.0`.

### EXPOSE

`EXPOSE` what ports to listen to at runtime. For example, if your app listens on port `8080`, you’ll want to expose port `8080`.

### ENV

`ENV` is for environment variables, so any key/value pairs that your app needs.

### ADD

`ADD` copies files to a specific location. For example, if you want to copy code to the `WORKDIR` (you’ll learn about that coming up) or another directory.

### ENTRYPOINT

`ENTRYPOINT`, again, is much like `RUN` and `CMD` in terms of running an executable and specifying parameters that runtime.

The difference is that `ENTRYPOINT` specifies a container that will run as an executable (an executable inside of an executable… bit of inception here).

### WORKDIR

`WORKDIR` sets the working directory as the default location for anything running with `RUN`, `CMD`, `ENTRYPOINT`, `COPY`and `ADD`. Essentially, it’s the default location where any commands or executables will be run from.

### HEALTHCHECK

`HEALTHCHECK` tells Docker to test a container and see if it’s still working.

For example:

```jsx
HEALTHCHECK --interval=5m --timeout=3s \
  CMD curl -f http://localhost/ || exit 1
```

## Building A Dockerfile

## Building The Container Image

