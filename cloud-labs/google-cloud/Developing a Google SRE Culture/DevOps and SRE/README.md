So what is DevOps?

To understand what it is, you first need to understand why DevOps exists.

Traditionally, IT teams consist of developers and operators.

Developers are responsible for writing code for systems and operators are responsible for ensuring that those systems operate reliably, so customers are happy.

Developers are expected to be agile and are often pushed to write and deploy new code as quickly as possible.

Essentially, developers want to work faster, innovating, and succeeding or failing quickly.

This resulted in developers throwing their code over the wall to operators who then had to

deal with code that was written without much understanding of how it would run in production.

Operators who are expected to keep systems stable would prefer to work slower, focusing on reliability and consistency.

Quite understandably, this way of working wasn't sustainable between these two groups.

Their priorities caused tension between the two teams, and they were not necessarily aligned with the needs of the business.

As a way to knock down the wall and close the gap between developers and operators, a culture instead of practices known as DevOps was born.
01:19
Let's take a look at how Google categorizes DevOps.

There are five key areas.

The first is to reduce organizational silos.

You can increase and foster collaboration by breaking down barriers across teams.

Second, you need to accept failure is normal.

Computers are inherently unreliable, so you can't expect perfect execution, and when you introduce humans into the system, you get even more imperfection.

Things failing will inevitably become part of the process.

Third, you'll want to implement gradual change.

Small incremental changes are easier to review, and if a gradual change does release a bug

in production, it allows you to reduce the time to recover making it simple to roll back.
02:07
Fourth, you need to leverage tooling and automation.
02:11
Identifying manual work that you can then automate is key to helping your IT team work efficiently and focus on the tasks that matter.
02:19
Finally, you'll want to measure everything.
02:22
Measurement is a critical gauge for success.
02:25
There's no way to tell whether what you're doing is successful if you have no way to measure it.
02:31
It's important to understand that DevOps is a philosophy versus a development methodology or technology.
02:38
Although DevOps philosophy highlights critical ways for IT teams to operate, it doesn't give explicit guidance on how an organization should implement practices to be successful.
02:49
That's where SRE comes in.
02:52
So what is SRE?
02:54
SRE evolved at Google in early 2000's separately from DevOps.
02:59
Back in 2003, Benjamin Treynor Sloss, currently a VP of engineering at Google, was tasked
03:05
with managing a team of engineers who are responsible for keeping Google's websites up and running.
03:10
You're probably wondering, "Wait, so a bunch of software engineers who write the code now also
03:16
have to be responsible for running their production systems? But doesn't the Ops team do that?"
03:21
Well the answer at least traditionally is yes.
03:26
However, this team only had software engineers, so Ben had them spend some of their time on operations tasks in addition to development tasks.
03:34
So they could better understand how their code ran and production.
03:37
This way of working is what led the team to site reliability engineering and the associated job role were SREs, who are generally engineers, are responsible for operations.
03:49
Just as DevOps aims to close the gap between software development and software operations, this new SRE approach is a concrete way to solve problems that the DevOps philosophy addresses.
04:01
Note that SRE is both a practice and a role.
04:05
Not every organization that follows SRE principles necessarily must have engineers with the title SRE.
04:12
This course mostly focuses on the practices and principles themselves, things like titles and team structures are implementation details.
04:20
Several SRE practices align to Google's categorizations of DevOps, and in addition to implementing SRE technical practices, you'll also want to implement cultural practices.
04:31
Without a culture to sustain them, it is not possible to maintain the practical aspects of SRE.
04:37
Let me explain where these fundamentals fit into the key areas of DevOps we discussed.
04:42
With regard to reducing organizational silos, SREs share ownership of production with developers.
04:49
Together they define service level objectives or SLOs and error budgets, and share responsibility of how they determine reliability and prioritize work.
04:59
Culturally, this promotes shared vision and knowledge as a well as a need for improved collaboration and communications.
05:07
Complex systems fail in interesting and complex ways.
05:11
Accepting failure as normal state is an important practice within SRE.
05:16
A blameless postmortem is held after an incident to improve the understanding of the failure mode
05:21
and to identify effective preventive actions to reduce the likelihood or impact of a similar incident.
05:28
Learning from incidents in this matter requires a culture of psychological safety and blamelessness.
05:34
When implementing gradual change, SREs aim to reduce the cost of failure by rolling out changes to a small percentage of users before making them generally available.
05:43
Culturally, this promotes more of design thinking and prototyping.
05:48
Next, in order to leverage tooling and automation.
05:52
SREs focus on toil automation reducing the amount of manual repetitive work.
05:57
Automating this year's job away can undoubtedly be met by resistance, that's why teams need to talk
06:03
about and understand the psychology of change and how to address resistance to change within the team.
06:09
Finally, measuring everything means that SREs work to measure everything related to toil, reliability, and the health of their systems.
06:18
To foster these practices, organizations need a culture of goal setting, transparency, and data-driven decision-making.
06:26
Before diving into each of these pillars as they relate to SRE, I want to acknowledge
06:30
that sometimes people can see these practices aligning with different or many of the pillars of DevOps.
06:37
It is likewise important to acknowledge that the language and definitions across different organizations, are less critical than
06:43
driving towards the goal of your organization, and the outcomes you are trying to deliver for your customers.
06:49
In other words, we may disagree on the precise terminology, but many of the underlying principles are the same.
06:56
The goal of SRE is to serve the business and the user, not the other way round.
07:01
The next three modules will dig a bit deeper into all of these SRE practices and cultural concepts.
