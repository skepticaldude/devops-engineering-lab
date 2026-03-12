As you learned in the last module, DevOps philosophy emerged in part due to the siloed nature of software development and operations.

Developers generally aren't very familiar with the systems their code runs on, and operators have to deal with code that may be unstable.

And that code just keeps coming over to them at a high velocity from agile developers.

To be an effective team that isn't stuck in 'break-fix' mentality, the walls between the business, development, and operations teams need to be knocked down.

Software engineering as a discipline focuses on designing and building rather than operating and maintaining, despite estimates that 40-90% of total costs are incurred after launch.

If the majority of the total cost of ownership of software is maintaining it after it's in production, and developers aren't working on this, then who is?

SRE employs practices that effectively break down these silos and promote shared ownership between development and operations teams.

More importantly, these fundamentals help teams maintain reliability of their services.

There are several practices that support this, but in this course you'll learn about two specific ones: error budgets and service-level objectives, or SLOs.

SRE gets everyone to agree on 'how' to measure service reliability and 'what' to do if you fall

short, from individual contributors all the way up to VPs, thus ensuring that responsibility for reliability is shared.

In order to agree on a target for reliability, you'll first have to define what reliable means, and how you're determining it.
``` text 
A simplistic way to think about reliability is that it equals your service's 'good' time divided by its total time, which gives a numerical fraction of time that the service is available in working.
```
While this is relatively easy to measure and understand, it doesn't work very well for distributed, complex systems.

For example, how do you measure 'good' time of a server that currently doesn't receive requests?

Or what if one of three servers is down?

Does that mean your service is down, or is it up?

> The more sophisticated approach is to define availability as a number of 'good' interactions divided by the number of total interactions.

This leaves you with a numerical fraction of real users who experience a service that is available and working.

> In essence, service reliability is about determining the amount of reliability you are trying to reach and the amount of downtime you are willing to tolerate.

That amount of reliability you are willing to tolerate is your error budget.

If you're thinking that 100% reliability is what your goal should be, you'd be wrong.

If you spend all of your time targeting 100% reliability, you'll slow the release of new service features, which is what helps drive your business.

This is where the error budget comes in.

As long as the measured up time is above your target, meaning as long as you have error budget remaining, you can push new feature releases.

Alternatively, you can spend this remaining budget on something else, such as expected system changes, inevitable failures in hardware and networks, planned downtime, or risky experiments.

> Essentially, an error budget is an agreement that helps prioritize engineering work.

> Error budgets create a common incentive for developers and SREs to find the right balance between innovation and reliability.

Developer teams can manage the error budget on their own, knowing that unrealistic reliability targets will slow down innovation.

It creates a shared responsibility between teams for system uptime, as infrastructure failures take away developers' error budget.

Another SRE practice that ties to error budgets and creates shared responsibility between dev and ops teams are service-level objectives, or SLOs.

> SLOs are precise numerical targets for system reliability.

These targets are agreed upon between stakeholders, thereby sharing ownership of reliability, and hopefully mitigating any future confusion or conflict.

Since you want your dev teams to work at a high velocity, SLOs can help determine how fast is too fast.

Measuring SLO performance gives a real- time indication of the reliability cost of new features.

If everyone agrees that the SLO represents the point at which you are no longer meeting the expectations of your users,

then broadly speaking, being well within your SLO is a signal that you can move faster without causing those users pain.

## How can you define SLOs for your service?

Well, you first need to understand service-level indicators, or SLIs.

> An SLI tells you at any moment in time how well your service is doing.
>
> It's a quantifiable measure of service reliability.
>
> We recommend that SLIs are expressed as the number of good events divided by the number of valid events, times 100%.
>
> This gives you a range of 0% to 100%, where zero equals 'nothing works' and 100 equals 'nothing's broken.'

SLIs should map to user expectations, such as response time latency and quality, data processing, correctness and freshness, or storage latency and throughput.

And so, an SLO is your target for SLIs aggregated over time.

Assuming you've expressed your SLIs as a percentage between zero and 100, your SLO should generally be just short of 100%, like 99.9%, or 'three nines.'

SLOs draw the line between happy and unhappy customers.

A typical customer should be happy if you barely meet your SLO.

Anything below your SLO will result in an unhappy customer who's expectations for reliable service are not being met.

> Lastly, an SLA, which you are likely familiar with already, is the promise you make about your service's health to your customers.
>  
> It defines what your business is willing to do if you fail to meet your SLOs.
>
> For example, refunding money.

In the next video, we'll discuss the SRE cultural practices that align with the practices of SLOs and error budgets.
