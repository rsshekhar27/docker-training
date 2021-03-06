# Motivation and concepts

### A short story

Back in time, we used to have a server attached to an application. For every application we developed, we needed to build and configure a server for it. If we had 2 applications, we needed 2 servers. I'm talking about networking, backup, operating system installation and configuration. It was time, resource and money consuming.

Later on, virtualization was the thing. I'm refering to the virtualization as a method of divide the system resources between different applications. To use this type of virtualization, we need a Virtual Machine (VM).

The simplest definition of a VM is: A VM is an emulation of a physical computing environment.

So, instead of having one application attached to a physical machine, we will have a VM. For that, we will just need a powerful machine. As a result, things became cheaper. Problem solved!

Wait! What is the price of running a VM?

Virtual Machines waste a lot of resources. A VM requests for CPU, memory, hard disk, network and other hardware resources, which are managed by a virtualization layer (hypervisor) responsible for translating these requests to the underlying physical hardware.

Here is an image to exemplify the concept:

![Emulation](https://raw.githubusercontent.com/carlan/docker-training/master/docs/images/emulation.png)

### Vagrant: The virtual machine manager

While I'm talking about VM's, I think it's good to mention a tool called Vagrant.

Vagrant is a virtual machine manager, with it you can easily create, modify and delete virtual machines using the command line.

The creation of the virtual machines became faster with Vagrant. It offers a repository with virtual machines pre-installed to be downloaded and used as fast as your internet connection can download it.

But, under the hood, it's still a virtual machine.

### What is docker?

Almost every developer these days know there is _something_ called docker or at least heard the word docker before. Although, do you really know what docker is? It isn't that complicated, actually is pretty simple to understand.

Docker is a piece of software which aims to simplify the process of building, deploying, shipping and running applications in a controllable environment (sandbox).

For Docker, the sandbox environment is called _container_ and this is really important to know.

The container revolution started when the maintaners of the Linux Kernel added a feature called namespaces. Namespaces, among other things, can be used to create an isolated container that has no access to objects outside it. This enables multiple isolated executions within a single operating system kernel.

A container doesn't need to boot the operating system kernel like VM's because it's running on the atual operating system kernel. Also, the creation of a container is so fast as the instantiation of a class. Containers states (or images) are very small compared to VM's, so they are easy to distribute.

Here is an image for you to visualize:

![Container based virtualization](https://raw.githubusercontent.com/carlan/docker-training/master/docs/images/contenarization.png)

With docker you can abandon vitual machines and replace them with containers due to their lower overhead and potentially better performance.

Docker is technology agnostic, you can use docker with almost any language or framework. Here, on this presentation I'm going to use for example ~~Java~~ and Python, but I can easily run Ruby, Go, Scala, Smalltalk, Groovy.

### Docker containers

When I first heard the term _container_, I thought about that huge rectangle box with lots of stuff inside it that you put on a ship. If you think of it, it's kind of a standard way to ship stuff in a ship.

Well, containers in docker are very similar. A container is a stardard way to ship your code to different environments.

A running instance of an image is also know as a container.

### Docker images

As we just saw, an image is the basis of a container, a blueprint to get a container running. An image is built to be used in a container. Also, an image doesn't have a state and it never changes.

If you want to run a Java application, you'll need an operation system like Ubuntu or Windows, and you'll also need the Java installed in the image to run your application.
