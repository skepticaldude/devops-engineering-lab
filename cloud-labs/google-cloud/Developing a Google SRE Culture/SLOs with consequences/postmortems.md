[MUSIC] When working at high-velocity and development operations, or really at any speed, mistakes are inevitable.

That's why Google sees accepting failure as normal, as a pillar of DevOps philosophy.

But how exactly can you implement this philosophy in your organization?

. Experienced site reliability engineers are comfortable with failure, and know that incidents and outages are going to occur, even if they've taken all the necessary precautions.

Before an outage, SREs seek to eliminate ambiguity by building monitoring and observability in the

platform, and establishing and documenting processes for incident response and management, handoffs, and other outage activities.

This allows them to confidently focus on the relevant issue during an incident.

After an outage, it's important to understand why an incident occurred, and then take steps to make sure it doesn't happen again in the same way.

SREs do this by documenting and conducting a blameless postmortem.

Some people also call this a retrospective.

In fast-paced environments where new problems are being addressed constantly, it's easy to just address one incident

and then move on to the next without taking the time to actually learn from what happened.

To avoid doing this, SREs take a systematic approach to ensure that the team collectively learns from the incident.

> So what is the purpose of a postmortem?
>
> A postmortem's ultimate deliverable is a written record of the incident that consists of specific parts.
>
<ins> Details of the incident and its timeline. </ins>

* The actions taken to mitigate or resolve the incident.

* The incidents impact.

* It's trigger or root cause or causes.

* The follow-up actions to prevent its recurrence.

> Particularly, a blameless postmortem only focuses on the root causes of an incident without accusing a particular person or team, or their actions or behavior.

Specific people will write and review the postmortem, but everyone who had a role in the event

will be a part of the postmortem process so you can collect as much information as possible.

Now, you might be wondering why you should conduct a postmortem beyond identifying the root cause or causes.

If it was just about fixing it or preventing the issue, it might seem like it's unnecessary if you've already accomplished that goal.

A postmortem has several specific and important goals.

You want to ensure that all the root causes are properly understood by the team.

Almost all outages have multiple causes at their root.

Many times, each of those causes taken an isolation may not have been enough to cause a failure, but when combined, they lead to an incident.

Tactics like the five whys are used to probe deep into what caused an incident in all of the contributing factors, not just what first appears to be the culprit.

You want to define or take effective actions to prevent the issue from occurring again.

At this point, you've probably taken some actions to resolve the immediate user impact, but in the long or even short term, the outage might happen again.

You need to prevent recurrence and prioritize the work to do so.

You want to reduce the likelihood of stressful outages.

Every outage is a stressor on the team.

Google wants its SREs to spend their time improving its systems not dealing with incidents.

Good system hygiene, including outage prevention, is a key quality of life factor for your engineers.

You want to avoid multiplying complexity.

Much of the time, quick fixes are involved in solving incidents and preventing their immediate recurrence.

Each of those fixes is like a Band-Aid or patch on the system.

If you don't perform good postmortems and permanently prevent recurrence, over time, fixes will become interdependent and sticky as each one stacks on the other.

This makes the system more complex than necessary, and less maintainable, and ultimately increases the likelihood of future failure.

You want to learn from your mistakes and those of others.

Every failure is an opportunity to learn.

Good SREs are constructive pessimists, and a lot of their instincts come from experiencing past failure.

In addition to creating a documented record for your team to learn from, the practice of writing a postmortem provides additional value to your organization.

Focusing on blamelessness helps to increase the effectiveness of your teams.

They become 100% focused on preventing a problem from occurring, instead of worrying about being blamed if something goes wrong.

It also promotes a culture of psychological safety, which we will discuss in the next video.
