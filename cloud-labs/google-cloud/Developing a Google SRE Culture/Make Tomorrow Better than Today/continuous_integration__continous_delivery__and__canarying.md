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
01:34
This stage involves continuous integration, testing automation, and deployment automation.
01:40
If you think of software development as a process, you can divide it into these categories: code, build, integrate, test, release, deploy, and operate.
01:55
In agile development, the process covers code and build.
01:59
DevOps philosophy spans from code to operate.
02:03
Continuous integration and continuous delivery fill in the middle with code to test; to release and to deploy.
02:11
So how does the practice of CI/CD help reduce the cost of failure when implementing gradual change?
02:17
It helps to overcome agile transformation challenges.
02:21
It minimizes code integration headaches.
02:24
It reduces human error.
02:27
It promotes higher code quality.
02:30
It's easier to recover after something goes wrong.
02:34
You can automate everything, which saves time and money.
02:38
It provides visibility on project completion.
02:41
Time to market is shorter.
02:44
It provides you with more metrics to review and act on.
02:48
The other practice SREs use for implementing gradual change is canarying.
02:54
You may have heard of the phrase "Canary in a coal mine," which is a metaphor for an advanced warning of danger.
03:00
Coal miners would bring canaries into coal mines to detect dangerous gases.
03:05
Canaries are smaller and breathe faster than humans, so if they died, the miners knew there was danger.
03:12
Let's simplify this metaphor a bit.
03:15
We have something large that we don't want to harm.
03:18
We have something small that we are okay losing.
03:22
The small thing detects danger as we go into the unknown.
03:26
Now let's see how this relates in terms of SRE practice in production systems.
03:31
We have a large service that we want to sustain.
03:35
We are okay losing a small portion of it.
03:38
We employ a production change with unknown impact to the small portion to detect danger.
03:44
So what exactly does this mean?
03:47
Canarying is deploying a change in service to a group of users who don't know
03:51
they are receiving the change, evaluating the impact to that group, then deciding how to proceed.
03:56
If the change contains bugs, the cost is much less than if it was rolled out to the whole system and can be reversed quickly.
04:04
So what are requirements for canarying?
04:07
The canary population should be large enough to be a representative subset when compared to the control population.
04:13
The difference between the canary and the control population should, to the greatest extent, practically possible be only the production change that you are testing.
04:23
The canary population should be small enough to not endanger the quality of service as a whole if the canary is broken.
04:31
The canary deployment should not be overly complicated, and impose significant cognitive load on the operator.
04:38
In other words, it should be easy enough to reason about the canary process so that's easy
04:43
to understand how it can impact current service health overall and easy to cancel in case of problems.
04:50
It's true that these three points are to some degree in conflict with each other.
04:55
This generic requirements also do not include any additional requirements specific to a service.
05:01
In the next video, we'll talk about the SRE cultural concepts of design thinking and prototyping, that relate to implementing gradual change.
