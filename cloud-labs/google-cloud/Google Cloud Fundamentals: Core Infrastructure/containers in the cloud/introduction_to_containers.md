In this section of the course we’ll explore containers and help you understand how they are used.

Infrastructure as a service, or IaaS, allows you to share compute resources with other developers by using virtual machines to virtualize the hardware.

This lets each developer deploy their own operating system (OS), access the hardware, and build their applications in a self-contained environment with access to RAM, file systems, networking interfaces, etc.

This is where containers come in.

The idea of a container is to give the independent scalability of workloads in PaaS and an abstraction layer of the OS and hardware in IaaS.

A configurable system lets you install your favorite runtime, web server, database, or middleware, configure the

underlying system resources, such as disk space, disk I/O, or networking, and build as you like.

But flexibility comes with a cost.

The smallest unit of compute is an app with its VM.

The guest OS might be large, even gigabytes in size, and take minutes to boot.

As demand for your application increases, you have to copy an entire VM and boot the guest OS for each instance of your app, which can be slow and costly.

> A container is an invisible box around your code and its dependencies with limited access to its own partition of the file system and hardware.
>
> It only requires a few system calls to create and it starts as quickly as a process.
>
> All that’s needed on each host is an OS kernel that supports containers and a container runtime.

In essence, the OS is being virtualized.

It scales like PaaS but gives you nearly the same flexibility as IaaS.

This makes code ultra portable, and the OS and hardware can be treated as a black box.

So you can go from development, to staging, to production, or from your laptop to the cloud, without changing or rebuilding anything.

As an example, let’s say you want to scale a web server.

With a container, you can do this in seconds and deploy dozens or hundreds of them, depending on the size of your workload, on a single host.

That's just a simple example of scaling one container running the whole application on a single host.

However, you'll probably want to build your applications using lots of containers, each performing their own function like microservices.

If you build them this way and connect them with network connections, you can make them modular, deploy easily, and scale independently across a group of hosts.

The hosts can scale up and down and start and stop containers as demand for your app changes or as hosts fail.
