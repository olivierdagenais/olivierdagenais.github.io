The DevOps Handbook
===================

A book summary by Olivier Dagenais

Preface
-------

### "Aha" moments (p. xi)

### Myth: DevOps is only for startups (p. xiv)

### Myth: DevOps replaces Agile (p. xv)

### Myth: DevOps is incompatible with ITIL (p. xv)

### Myth: DevOps is incompatible with Information Security & Compliance (p. xv)

### Myth: DevOps means eliminating IT operations, or "No Ops" (p. xvi)

### Myth: DevOps is just "Infrastructure as Code" or automation (p. xvi)

### Myth: DevOps is only for OSS (p. xvi)

Foreword (p. xix)
--------

Introduction (p. xxi)
------------

> (p. xxi) «...performing tens, hundreds, or even thousands of code deploys per day...»

> (p. xxi) «By adding the expertise of QA, IT Operations, and Infosec into delivery teams and automated self-service tools and platforms, teams are able to use that expertise in their daily work without being dependent on other teams.»

(p. xxiii) Agile & DevOps enables the same revolution to software that RapidResponse brought to planning: so fast, you can try things to see what happens.

> (p. xxiii) «...often deploy changes hundreds or even thousands of times per day.»

### The problem: something in your organization must need improvement (or you wouldn't be reading this book) (p. xxiv)

#### The core, chronic conflict (p. xxiv)

> (p. xxv) «Among them are the two following goals, which must be pursued simultaneously:
>
> - Respond to the rapidly changing competitive landscape
> - Provide stable, reliable, and secure service to the customer»

> (p. xxv) «Configured this way, Development and IT Operations have diametrically opposed goal and incentives.»

#### Downward spiral in three acts (p. xxvi)

> (p. xxvi) «...where everything becomes just a little more difficult, bit by bit - everybody gets a little busier, work takes a little more time, communications become a little slower, and work queues get a little longer.»

(it gets worse and worse)

#### Why does this downward spiral happen everywhere? (p. xxvii)

#### The costs: human and economic (p. xviii)

- burnout, powerlessness
- hopelessness, despair
- learned helplessness
- long hours, weekends
- lose best people
- opportunity cost

### The ethics of DevOps: there is a better way (p. xxix)

(solves all the problems)

#### Breaking the downward spiral with DevOps (p. xxx)

- during business hours
- fast feedback loops
- automated testing
- fix problems when found
- telemetry for alerts
- "everyone feels productive"
- "dark launch techniques" (feature toggles)
- "found and fixed early, when they are smaller, cheaper and easier to correct."

> (p. xxxi) «And, because everyone fully owns the quality of their work, everyone builds automated testing into their daily work and uses peer reviews to gain confidence that problems are addressed long before they can impact a customer.»

(p. xxxii)

- blameless post-mortems
- Netflix "chaos Monkey"-like
- "everyone has ownership in their work"

#### The business value of DevOps (p. xxxii)

- Better performance when using DevOps practices

> (p. xxxiii) «...high performers had lead times measured in minutes or hours...»

> (p. xxxiii) «They also had higher employee job satisfaction, lower rates of employee burnout, and their employees were 2.2 times more likely to recommend their organization to friends as a great place to work.»

#### DevOps helps scale developer productivity (p. xxxiii)

Mostly measured in deploys per day.

#### The universality of the solution (p. xxxv)

> (p. xxxv) «In the remainder of this book, we will describe how to replicate the transformation described in The Phoenix Project, as well as provide many case studies of how other organizations have used DevOps principles and practices to replicate those outcomes.»

### The DevOps Handbook: An essential Guide (p. xxxvi)

A summary of the 6 parts

PART I: The Three Ways (p. 1)
======================

Part 1: Introduction (p. 3)
--------------------

### A brief history (p. 3)

> (p. 3) «...the "convergence of DevOps"»

#### The lean movement (p. 4)

Value stream mapping, Kanban boards and total productive maintenance

- Manufacturing lead time => quality, customer satisfaction, employee happiness
- Small batch sizes of work => short lead times

Lean principles:

- constancy of purpose
- scientific thinking
- flow
- pull
- quality at the source
- leading with humility
- respecting every individual

#### The Agile Manifesto (p. 4)

- light-weight
- deliver frequently
- small batch sizes
- incremental releases
- small self-motivated teams
- high-trust

#### Agile infrastructure and velocity movement (p. 5)

#### The continuous delivery movement a.k.a. continuous deployment (p. 5)

#### Toyota kata (p. 5)

> (p. 5) «...the improvement kata requires creating structure for the daily, habitual practice of improvement work, because daily practice is what improves outcomes.»

Chapter 1: Agile, continuous delivery, and the three ways (p. 7)
---------------------------------------------------------

### The manufacturing value stream (p. 7)

> (p. 7) «value stream [is defined as] "the sequence of activities an organization undertakes to deliver upon a customer request"»

- fast & predictable lead times:
    - small batch sizes
    - reducing work in progress
    - preventing rework
    - constantly optimizing our system

### The technology value stream (p. 8)

> (p. 8) «...the process required to convert a business hypothesis into a technology-enabled service that delivers value to the customer.»

#### Focus on deployment lead time (p. 8)

(p. 9) The earliest we can possibly test is with TDD, helping "build quality into every part of our value stream"

##### Defining lead time vs. processing time (p. 9)

```text
                     lead time
 ________________________/\____________________________________
/                                                              \
|------------------------------|--------------------------------|
ticket                       work                            work
created                     started                     completed
                               \________________ ______________/
                                                V
                                          process time
```

#### The common scenario: deployment lead times requiring months (p. 10)

> (p. 10) «This is especially common in large, complex organizations that are working with tightly-coupled, monolithic applications, often with scarce integration test environments, long test and production environment lead times, high reliance on manual testing, and multiple required approval processes.»

#### Our DevOps ideal: deployment lead times of minutes (p. 10)

> (p. 11) «This is most easily achieved when we have architecture that is modular, well encapsulated, and loosely-coupled so that small teams are able to work with high degrees of autonomy, with failures being small and contained, and without causing global disruptions.»

#### Observing "% C/A" as a measure of rework

- [percent complete and accurate] ... reflects the quality of the output of each step in our value stream

### The three ways: the principles underpinning DevOps (p. 11)

> (p. 11) «The First Way enables fast left-to-right flow of work from Development to Operations to the customer.»

- visible
- frequent
- optimize globally
- small batches
- quality

(p. 12) Practices:

- continuous build, integration, test & deployment
- creating environments on demand
- limiting work in progress
- building systems & organizations that are safe to change

> (p. 12) «The Second Way enables the fast and constant flow fo feedback from right to left at all stages of our value stream.»

=> shorten & amplify feedback loops

> (p. 12) «The Third Way enables the creation of a generative, high-trust culture that supports a dynamic, disciplined, and scientific approach to experimentation and risk-taking, facilitating the creation of organizational learning, both from our successes and failures.»

### Conclusion (p. 13)

- value streams
- lead time
- The Three Ways

Chapter 2: The First Way: The Principles of Flow (p. 15)
------------------------------------------------

> (p. 15) «...to deliver value to customers quickly.»

> (p. 15) «By speeding up the flow (...), we reduce the lead time required to fulfill internal and external customer requests, further increasing the quality of our work while making us more agile and able to out-experiment the competition.»

### Make our work visible (p. 15)

> (p. 15) «We cannot easily see where flow is being impeded or where work is piling up in front of constrained work centers.»

> (p. 16) «Ideally, our Kanban board will span the entire value stream, defining work as completed only when it reaches the right side of the board.  Work is not done when Development completes the implementation of a feature - rather it is only done when our application is running successfully in production, delivering value to the customer.»

### Limit work in process (WIP) (p. 17)

> (p. 17) «However, interrupting technology workers is easy, because the consequences are invisible to almost everyone, even though the negative impact to productivity may be far greater than in manufacturing.»

-> limit WIP for each "column"

> (p. 18) «Nothing can be worked on until it is represented first in a work card, reinforcing that all work must be made visible.»

> (p. 18) «[If blocked], a far better action would be to find out what is causing the delay and help fix that problem.» (Facebook's motto)

> (p. 18) «Stop starting. Start finishing.»

### Reduce Batch Sizes (p. 18)

> (p. 19) «The result [of large batch sizes] is long lead times and poor quality - if a problem is found in one body panel, the entire batch has to be scrapped.»

-> how do you deal with changeover costs???

> (p. 20) «Small batch sizes result in less WIP, faster lead times, faster detection of errors, and less rework.»

=> Single piece flow -> continuous deployment

### Reduce the number of handoffs (p. 21)

> (p. 21) «Each of these steps is a potential queue where work will wait when we rely on resources that are shared between different value streams (e.g., centralized operations). The lead times for these requests are often so long that there is a constant escalation to have work performed within the needed timelines.»

> (p. 21) «...reduce the number of handoffs, either by automating significant portions of the work or by reorganizing teams to they can deliver value to the customer themselves instead of having to be constantly dependent on others.»

### Continually identify and elevate our constraints (p. 21)

> (p. 22) «...there is always one and only one constraint; any improvement not made at that constraint is an illusion.»

Typical transformations constraint progression:

1. Environment creation
2. Code deployment
3. Test setup & run
4. Overly tight architecture

> (p. 23) «After all these constraints have been broken, our constraint will likely be Development or the product owners.  Because (...) small teams (...), this is where we want our constraint to be.»
[High performers]
-> maximize developer productivity

### Eliminate hardships and waste in the value stream (p. 23)

(p. 24) Categories of waste and hardship

- Partially done work (loses value w/time)
- Extra processes (do not add value)
- Extra features ("gold plating")
- Task switching (context switching)
- Waiting (any delay)
- Motion (i.e. handoffs)
- Defects (the longer the time to resolve, the more difficult)
- Nonstandard or manual work (i.e. snowflakes)
- Heroics

> (p. 25) «...systematically do what is needed to alleviate or eliminate these burdens and hardships to achieve our goal of fast flow.»

### Conclusion (p. 25)

Chapter 3: The Second Way: the Principles of Feedback (p. 27)
-----------------------------------------------------

> (p. 27) «We make our system of work safer by creating fast, frequent, high-quality information flow throughout our value stream and our organization, which includes feedback and feedforward loops.»

### Working safely within complex systems (p. 27)

> (p. 28) «...because failure is inherent and inevitable in complex systems, we must design a safe system of work (...) where we can perform work without fear, confident that any errors will be detected quickly...»

Safer when:

- complex work is managed ... reveal problems
- problems are swarmed and solved
- new local knowledge is exploited globally
- leaders create other leaders

### See problems as they occur (p. 29)

-> easily invalidate assumptions

> (p. 29) «...every work operation is measured and monitored, and any defects or significant deviations are quickly found and acted upon.»

> (p. 30) «...wherever work is performed, at __all stages of the technology value stream...__»

> (p. 30) «...telemetry... \[for\] production environment(s) ... \[to\] detect when they are not operating as expected... \[and to\] measure our intended goals...»

### Swarm and solve problems to build new knowledge (p. 30)

> (p. 30) Goal: «contain problems before they \[can\] spread \[and then prevent them\]»

> (p. 31) «Instead of working around the problem or scheduling a fix "when we have more time", we swarm to fix it immediately...»

- prevent downstream spread (cost + effort go up)
- prevent new work that might mean new errors (i.e. don't push on top of broken build)
- prevent recurrence (cost + effort go up)

-> swarming => learning

### Keep pushing quality closer to the source (p. 32)

Ineffective quality controls:

- handoff for manual tasks (instead of self-service automation)
- approvals from people not participating
- extensive documentation
- handoff of large batches of work

> (p. 33) «...push quality (...) to where the work is performed...»

Via:

- peer reviews
- automated quality checking (such as code analysis)
- running tests on demand

> (p. 34) «...make quality everyone's responsibility...»

### Enable optimizing for downstream work centers (p. 34)

-> make it difficult/impossible to get it wrong

> (p. 34) «According to Lean, our most important customer is our next step downstream.»

-> the real customer (external) should be next!

### Conclusion (p. 35)

Chapter 4: The third way: The principles of continual learning and experimentation (p. 37)
-------------------------------------------------------------------------------------

> (p. 37) «...with systemic quality and safety problems, work is typically rigidly defined and enforced.»

> (p. 37) «...there is also often a culture of fear and low trust...»

> (p. 37) «In contrast (...) performing experiments (...) to generate new improvements...»

> (p. 37) «By applying a scientific approach to both process improvement and product development, we learn from our successes and failures...»

> (p. 38) «We reserve time for the improvement of daily work and to further accelerate and ensure learning. (...) to force continual improvement.  We even simulate and inject failures in our production services under controlled conditions to increase our resilience.»

-> Netflix chaos monkey!

### Enabling organizational learning and a safety culture (p. 38)

safety culture -> just culture

culture of fear => stop reporting problems => downward spiral

##### 3 types of culture (p. 39)

- pathological (fear and threat)
- bureaucrative (rules and processes)
- generative (actively seeking and sharing information)

> (p. 40) «When accidents and failures occur, instead of looking for human error we look for how we can redesign the system to prevent the accident from happening again.»

##### blameless post-mortem (p. 40)

- how it occurred
- best countermeasures to improve system
- ideally preventing it
- enable faster detection & recovery

### Institutionalize the improvement of daily work (p. 40)

> (p. 40) «...when we avoid fixing our problems, relying on daily workarounds, our problems and technical debt accumulates until all we are doing is performing workarounds (...) with no cycles left for doing productive work.»

> (p. 41) «Even more important than daily work is the improvement of daily work.»

> (p. 41) «Kaizen blitzes: periods when engineers self-organize into teams to work on fixing any problem they want»

-> virtuous cycle: fix more and more problems, earlier & cheaper

### Transform local discoveries into global improvements (p. 42)

> (p. 42) «The \[Naval Reactors\] is known for their intense commitment to scripted procedures and standardized work and the need for _incident reports for any departure from procedure or normal operations_ to accumulate learnings, no matter how minor the signal - they constantly update procedures and system designs based on these learnings.»

-> deviations from checklists, DRY, SOLID, TDD, etc. identified in code reviews

##### Create global knowledge (p. 43)

- searchable blameless post-mortem reports
- shared libraries for best code

### Inject resilience patterns into our daily work (p. 43)

> (p. 43) «...relentless and constant experimentation in their daily work [to increase capacity and identify vulnerabilities]»

> (p. 44) «...improvement rituals not only \[improve\] performance but also \[improve\] resilience...»

-> anti-fragility

introduce tension

- reduce deployment lead times
- increase test coverage
- decrease test execution times
- increase developer productivity
- "game day exercises" (disaster recovery practice)

### Leaders reinforce a learning culture (p. 44)

> (p. 44) «...the leader's role is to create the conditions so their team can discover greatness in their daily work.»

> (p. 45) «Leaders must elevate the value of learning and disciplined problem-solving.»

1. State True North goals
2. Create iterative, shorter term goals
3. Establish target conditions at the value stream
4. Frame the scientific experiment from conditions
    1. State problem
    2. Hypothesis re: countermeasure solving problem
    3. How to test hypothesis
    4. Interpret results
    5. Inform the next iteration

### Conclusion (p. 46)

- organizational learning
- high trust
- accept that failures occur
- talk about problems safely
- improve daily work
- convert local learning to global
- inject tension into daily work ("don't get comfy")

### Part I Conclusion (p. 46)
