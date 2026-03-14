# Measuring Everything in DevOps and SRE

The final pillar of **DevOps philosophy** is **measuring everything**.

Measurement allows teams to clearly understand what is happening with their services and systems.

At Google, measuring everything serves **three main goals**:

1. Help the IT team understand the **current status of a service objectively**
2. Enable teams to **analyze data and identify improvements**
3. Support collaboration between **IT teams and the business** to make better decisions

By measuring operational data, organizations become **data-driven**, enabling more informed decisions.

> You cannot improve what you do not measure.

---

# Core Measurement Practices in SRE

Within **Site Reliability Engineering (SRE)**, measurement focuses on three key areas:

- Measuring **reliability**
- Measuring **toil**
- **Monitoring** systems

---

# Measuring Reliability

Reliability can be quantified using:

- **Service Level Indicators (SLIs)**
- **Service Level Objectives (SLOs)**
- **Error Budgets**

Choosing the right **SLIs** is critical because they should reflect **user experience** rather than internal system metrics.

### Example: User Experience vs System Metrics

Users typically do not care about internal system failures such as:

- Database downtime
- Load balancer misconfiguration
- High CPU usage

What users actually experience is something like:

- A slow website
- Failed requests
- Unavailable services

Therefore, the best SLIs measure **user-visible behavior**.

For example:

- Request latency
- Request success rate
- Availability

---

# Good vs Bad Metrics

Not all metrics are equally useful.

### Poor Metrics

Metrics such as:

- CPU utilization
- Memory usage
- Load average

may not correlate directly with **user satisfaction**.

These metrics can fluctuate widely during both normal operation and outages, making them unreliable indicators.

This makes it difficult to set meaningful thresholds.

---

### Good Metrics

Good metrics:

- Closely reflect **user experience**
- Show **clear differences between normal operation and outages**
- Have **low variance**

Because of this, they make it easier to set reliable thresholds for monitoring and alerting.

---

# Measuring Toil

Toil is work that is:

- Manual
- Repetitive
- Automatable
- Tactical
- Lacks long-term value
- Directly tied to running a service

Measuring toil helps organizations **identify opportunities for automation and improvement**.

### Steps for Measuring Toil

#### 1. Identify Toil

Determine which tasks qualify as toil.

This should involve:

- Stakeholders
- Engineers performing the work

---

#### 2. Choose a Unit of Measurement

Measure toil in terms of **human effort**.

Common units include:

- Minutes
- Hours

These are objective and universally understood.

---

#### 3. Track Continuously

Measure toil:

- Before automation efforts
- During improvements
- After changes are implemented

Measurement should be streamlined using **tools or scripts** so that collecting data does not create additional toil.

---

# Simple Ways to Track Toil

You can begin by measuring simple indicators such as:

- Number of support tickets
- Number of alerts
- Alert statistics (cause and resolution)
- Estimated human time spent resolving issues

Tracking these metrics can reveal the **primary sources of operational toil**.

---

# Benefits of Measuring Toil

Measuring toil provides several advantages:

- Encourages **automation and reduction efforts**
- Helps teams make **data-driven decisions**
- Increases time spent on **engineering projects**
- Improves **team morale**
- Reduces **burnout and attrition**
- Reduces **context switching**
- Improves **productivity**
- Enhances **process clarity and standardization**
- Supports **technical skill growth**
- Reduces **training time**
- Decreases **human error**
- Improves **security**
- Shortens **response times to user requests**

---

# Monitoring Systems

Monitoring provides visibility into a system's health and behavior.

It allows teams to:

- Detect problems
- Diagnose system failures
- Maintain service reliability

---

# What Should You Monitor?

A best practice in SRE is to **alert on symptoms rather than causes**.

Users care about the **impact of a problem**, not its internal cause.

For example:

Users experience:

- Slow responses
- Failed requests
- Service downtime

They do not care whether the issue was caused by:

- A router reboot
- A database overload
- High CPU utilization

Monitoring symptoms reduces **alert noise** and helps teams focus on real user impact.

---

# Alerting with Error Budgets

Google recommends triggering alerts based on **error budget consumption**.

Examples:

- **High burn rate**: Spending 10 hours of error budget within 1 hour may trigger a page.
- **Moderate burn rate**: Spending 3 days of error budget over 3 days might only generate a ticket.

This approach ensures that engineers are alerted **only when reliability goals are at risk**.

---

# Exceptions to Symptom-Based Alerts

Some issues may not immediately affect users but still require attention.

Example:

- **Capacity alerts**

If a system is nearing its resource limits, teams should receive alerts even before users notice a problem.

---

# The Four Golden Signals

Google recommends monitoring four key signals for most systems:

1. **Latency** – The time it takes to process a request
2. **Traffic** – The demand placed on the system
3. **Errors** – The rate of failed requests
4. **Saturation** – The level of resource utilization

These signals provide a clear picture of system health.

---

# Key Takeaway

Measurement and monitoring are essential SRE practices that enable teams to:

- Maintain service reliability
- Reduce operational toil
- Improve decision-making
- Focus on business-critical development work

---

# Next Topic

The next topic explores the cultural foundations that support measurement, including:

- **Goal setting**
- **Transparency**
- **Data-driven decision making**
