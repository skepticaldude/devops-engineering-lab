[MUSIC] When working at high-velocity and development operations, or really at any speed, mistakes are inevitable.
00:13
That's why Google sees accepting failure as normal, as a pillar of DevOps philosophy.
00:18
But how exactly can you implement this philosophy in your organization?
00:22
. Experienced site reliability engineers are comfortable with failure, and know that incidents and outages are going to occur, even if they've taken all the necessary precautions.
00:33
Before an outage, SREs seek to eliminate ambiguity by building monitoring and observability in the
00:39
platform, and establishing and documenting processes for incident response and management, handoffs, and other outage activities.
00:47
This allows them to confidently focus on the relevant issue during an incident.
00:52
After an outage, it's important to understand why an incident occurred, and then take steps to make sure it doesn't happen again in the same way.
01:00
SREs do this by documenting and conducting a blameless postmortem.
01:04
Some people also call this a retrospective.
01:07
In fast-paced environments where new problems are being addressed constantly, it's easy to just address one incident
01:12
and then move on to the next without taking the time to actually learn from what happened.
01:19
To avoid doing this, SREs take a systematic approach to ensure that the team collectively learns from the incident.
01:27
So what is the purpose of a postmortem?
01:30
A postmortem's ultimate deliverable is a written record of the incident that consists of specific parts.
01:37
Details of the incident and its timeline.
01:40
The actions taken to mitigate or resolve the incident.
01:43
The incidents impact.
01:46
It's trigger or root cause or causes.
01:48
The follow-up actions to prevent its recurrence.
01:52
Particularly, a blameless postmortem only focuses on the root causes of an incident without accusing a particular person or team, or their actions or behavior.
02:03
Specific people will write and review the postmortem, but everyone who had a role in the event
02:07
will be a part of the postmortem process so you can collect as much information as possible.
02:14
Now, you might be wondering why you should conduct a postmortem beyond identifying the root cause or causes.
02:20
If it was just about fixing it or preventing the issue, it might seem like it's unnecessary if you've already accomplished that goal.
02:28
A postmortem has several specific and important goals.
02:31
You want to ensure that all the root causes are properly understood by the team.
02:36
Almost all outages have multiple causes at their root.
02:40
Many times, each of those causes taken an isolation may not have been enough to cause a failure, but when combined, they lead to an incident.
02:49
Tactics like the five whys are used to probe deep into what caused an incident in all of the contributing factors, not just what first appears to be the culprit.
02:57
You want to define or take effective actions to prevent the issue from occurring again.
03:03
At this point, you've probably taken some actions to resolve the immediate user impact, but in the long or even short term, the outage might happen again.
03:13
You need to prevent recurrence and prioritize the work to do so.
03:19
You want to reduce the likelihood of stressful outages.
03:23
Every outage is a stressor on the team.
03:25
Google wants its SREs to spend their time improving its systems not dealing with incidents.
03:32
Good system hygiene, including outage prevention, is a key quality of life factor for your engineers.
03:39
You want to avoid multiplying complexity.
03:42
Much of the time, quick fixes are involved in solving incidents and preventing their immediate recurrence.
03:49
Each of those fixes is like a Band-Aid or patch on the system.
03:53
If you don't perform good postmortems and permanently prevent recurrence, over time, fixes will become interdependent and sticky as each one stacks on the other.
04:03
This makes the system more complex than necessary, and less maintainable, and ultimately increases the likelihood of future failure.
04:12
You want to learn from your mistakes and those of others.
04:16
Every failure is an opportunity to learn.
04:19
Good SREs are constructive pessimists, and a lot of their instincts come from experiencing past failure.
04:27
In addition to creating a documented record for your team to learn from, the practice of writing a postmortem provides additional value to your organization.
04:35
Focusing on blamelessness helps to increase the effectiveness of your teams.
04:40
They become 100% focused on preventing a problem from occurring, instead of worrying about being blamed if something goes wrong.
04:47
It also promotes a culture of psychological safety, which we will discuss in the next video.
