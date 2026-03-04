## KUBERNETES
A product that helps manage and scale containerized applications is Kubernetes.

So to save time and effort when scaling applications and workloads, Kubernetes can be bootstrapped using Google Kubernetes Engine (GKE).

So, what is Kubernetes?

>[!NOTE]
>
> Kubernetes is an open-source platform for managing containerized workloads and services.
>
> It makes it easy to orchestrate many containers on many hosts, scale them as microservices, and easily deploy rollouts and rollbacks.
>
> At the highest level, Kubernetes is a set of APIs that you can use to deploy containers on a set of nodes called a cluster.

The system is divided into a set of primary components that run as the control plane and a set of nodes that run containers.

>[!WARNING]
>
> In Kubernetes, a node represents a computing instance, like a machine.
>
> Note that this is different to a node on Google Cloud which is a virtual machine running in Compute Engine.

You can describe a set of applications and how they should interact with each other, and Kubernetes determines how to make that happen.

Deploying containers on nodes by using a wrapper around one or more containers is what defines a Pod.

>[!NOTE]
>
> A Pod is the smallest unit in Kubernetes that you can create or deploy.
>
> It represents a running process on your cluster as either a component of your application or an entire app.

Generally, you only have one container per Pod, but if you have multiple containers with a hard

dependency, you can package them into a single Pod and share networking and storage resources between them.

The Pod provides a unique network IP and set of ports for your containers and configurable options that govern how your containers should run.

One way to run a container in a Pod in Kubernetes is to use the kubectl run command, which starts a Deployment with a container running inside a Pod.

>[!NOTE]
>
>A Deployment represents a group of replicas of the same Pod and keeps your Pods running even when the nodes they run on fail.
>
> A Deployment could represent a component of an application or even an entire app.

To see a list of the running Pods in your project, run the command: `$ kubectl` get pods.

Kubernetes creates a Service with a fixed IP address for your Pods, and a controller says "I need to attach

an external load balancer with a public IP address to that Service so others outside the cluster can access it."

In GKE, the load balancer is created as a network load balancer.

Any client that reaches that IP address will be routed to a Pod behind the Service.

>[!NOTE]
>
> A Service is an abstraction which defines a logical set of Pods and a policy by which to access them.

As Deployments create and destroy Pods, Pods will be assigned their own IP addresses, but those addresses don't remain stable over time.

>[!NOTE]
> A Service group is a set of Pods and provides a stable endpoint (or fixed IP address) for them.

For example, if you create two sets of Pods called frontend and backend and put them

behind their own Services, the backend Pods might change, but frontend Pods are not aware of this.

They simply refer to the backend Service.

>[!TIP]
>
>To scale a Deployment, run the kubectl scale command.

In this example (VIDEO REFERENCE), three Pods are created in your Deployment, and they're placed behind the Service and share one fixed IP address.

You could also use autoscaling with other kinds of parameters.

For example, you can specify that the number of Pods should increase when CPU utilization reaches a certain limit.

So far, we’ve seen how to run imperative commands like expose and scale.

This works well to learn and test Kubernetes step-by-step.

But the real strength of Kubernetes comes when you work in a declarative way.

Instead of issuing commands, you provide a configuration file that tells Kubernetes what you want your desired state to look like, and Kubernetes determines how to do it.

You accomplish this by using a Deployment config file.

You can check your Deployment to make sure the proper number of replicas is running by using either kubectl get deployments or kubectl describe deployments.

To run five replicas instead of three, all you do is update the Deployment config file and run the kubectl apply command to use the updated config file.

You can still reach your endpoint as before by using kubectl get services to get the external IP of the Service and reach the public IP address from a client.

The last question is, what happens when you want to update a new version of your app?

Well, you want to update your container to get new code in front of users, but rolling out all those changes at one time would be risky.

So in this case, you would use kubectl rollout or change your deployment configuration file and then apply the change using kubectl apply.

New Pods will then be created according to your new update strategy.

Here’s an example configuration that will create new version Pods individually and wait for a new Pod to be available before destroying one of the old Pods.
