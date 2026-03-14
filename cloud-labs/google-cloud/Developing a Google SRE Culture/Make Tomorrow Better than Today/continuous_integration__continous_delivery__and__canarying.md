In the world of IT, there are different perspectives on how to approach software development.

Culturally, developers tend to focus on moonshot thinking, where they can implement massive software changes that create breakthroughs and could fundamentally change society, but have a high likelihood of failing.

In contrast, SREs focus on gradual change, where they can test smaller changes that will have less impact on users if they fail.

The DevOps pillar of implementing gradual change is practically implemented by SREs in a few different ways to reduce the cost of failure.

SREs believe that change is best when it is small and frequent.

Although change is risky, it's less disruptive to users when rolled out in smaller waves.

Google SRE culture focuses on practices of continuous integration, continuous delivery, or CI/CD, and canarying.

Let's first define CI/CD.

## Continuous Integration

Continuous integration, usually refers to building, integrating, and testing code within the development environment.

The main goal of this practice is to enable engineers to work on code and test more often.

As a result, code quality increases and critical issues can be avoided earlier.

## Continuous Delivery

Continuous delivery just means that you can deploy to production frequently, but may choose not to, usually due to businesses preferring a slower rate of deployment.

This stage involves continuous integration, testing automation, and deployment automation.

If you think of software development as a process, you can divide it into these categories: code, build, integrate, test, release, deploy, and operate.

In agile development, the process covers code and build.

DevOps philosophy spans from code to operate.

Continuous integration and continuous delivery fill in the middle with code to test; to release and to deploy.

> So how does the practice of CI/CD help reduce the cost of failure when implementing gradual change?

* It helps to overcome agile transformation challenges.

* It minimizes code integration headaches.

* It reduces human error.

* It promotes higher code quality.

* It's easier to recover after something goes wrong.

* You can automate everything, which saves time and money.

* It provides visibility on project completion.

* Time to market is shorter.

* It provides you with more metrics to review and act on.

## Canarying

The other practice SREs use for implementing gradual change is canarying.

You may have heard of the phrase "Canary in a coal mine," which is a metaphor for an advanced warning of danger.

Coal miners would bring canaries into coal mines to detect dangerous gases.

Canaries are smaller and breathe faster than humans, so if they died, the miners knew there was danger.

Let's simplify this metaphor a bit.

* We have something large that we don't want to harm.

* We have something small that we are okay losing.

* The small thing detects danger as we go into the unknown.

Now let's see how this relates in terms of SRE practice in production systems.

* We have a large service that we want to sustain.

* We are okay losing a small portion of it.

* We employ a production change with unknown impact to the small portion to detect danger.

So what exactly does this mean?

> Canarying is deploying a change in service to a group of users who don't know they are receiving the change, evaluating the impact to that group, then deciding how to proceed.
>
> If the change contains bugs, the cost is much less than if it was rolled out to the whole system and can be reversed quickly.

## Requirements for Canarying

So what are requirements for canarying?

1. The canary population should be large enough to be a representative subset when compared to the control population. The difference between the canary and the control population should, to the greatest extent, practically possible be only the production change that you are testing.

2. The canary population should be small enough to not endanger the quality of service as a whole if the canary is broken.

3. The canary deployment should not be overly complicated, and impose significant cognitive load on the operator.

In other words,
1. it should be easy enough to reason about the canary process,
2. so that's easy to understand how it can impact current service health overall and
3. easy to cancel in case of problems.

>[!Note]
> It's true that these three points are to some degree in conflict with each other.
>
> This generic requirements also do not include any additional requirements specific to a service.

In the next video, we'll talk about the SRE cultural concepts of design thinking and prototyping, that relate to implementing gradual change.
