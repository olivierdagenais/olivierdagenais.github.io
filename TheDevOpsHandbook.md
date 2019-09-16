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

PART II: Where to start (p. 47)
=======================

Part 2: Introduction (p. 49)
--------------------

> (p. 49) «...we will walk you through the process of initiating a DevOps transformation.»

### Chapter 5: Selecting which value stream to start with (p. 51)

> (p. 51) «...we must carefully pick and then protect those improvement projects that will most improve the state of our organization.» (Etsy)

> (p. 52) (Nordstrom) «Instead, they wanted to focus on very specific areas of the business so that they could experiment and learn. Their goal was to demonstrate early wins, which would give everyone confidence that these improvements could be replicated in other areas of the organization.»

> (p. 52) «They created a dedicated product [mobile application] team (...) they would no longer have to depend on and coordinate with scores of other teams (...)»

> (p. 53) «Over the following year, they eliminated testing as a separate phase of work, instead integrating it into everyone's daily work. [The practice of relying on a stabilization or hardening phase at the end of a project often has very poor outcomes, because it means problems are not being found and fixed as part of daily work and are left unaddressed, potentially snowballing into larger issues.] They doubled the features being delivered per month and halved the number of defects - creating a successful outcome.»

#### Greenfield vs. brownfield services (p. 54)

- greenfield: new, few constraints
- brownfield: previously established

> (p. 54) (National Instruments) «An example of a greenfield DevOps project is the Hosted LabVIEW product in 2009 at N.I., a thirty-year-old organization (...) a new team was created and allowed to operate outside of the existing IT processes (...) they were able to deliver Hosted LabVIEW to market in half the time of their normal product introductions.»

> (p. 55) «Brownfield projects often come with significant amounts of technical debt, such as having no test automation or running on supported platforms.»

> (p. 55) «...what predicted performance was whether the application was architected (or could be re-architected) for testability and deployability.»

> (p. 56) (Examples of brownfield transformations)

- CSG (2013)
- Etsy (2009)

#### Consider both systems of record and systems of engagement (p. 56)

- System of record: slower, regulatory, Type 1, "doing it right"
- System of engagement: faster, experimentation, Type 2, "doing it fast"

> (p. 57) «...high performing organizations are able to simultaneously deliver higher levels of throughput and reliability.»

> (p. 57) «By making these downstream systems safer to change, we help the entire organization more quickly and safely achieve its goals.»

#### Start with the most sympathetic and innovative groups (p. 57)

> (p. 58) «...we will focus our energy on creating successes with less risk-averse groups and build out our base from there...»

#### Expanding DevOps across our organization (p. 58)

> (p. 58) «...we must demonstrate early wins and broadcast our successes.  We do this by breaking up our larger improvement goals into small, incremental steps. This not only creates our improvements faster, it also enables us [to fail fast and retry].»

> (p. 59) «Ideal phases used by change agents to build and expand support:
>
> 1. Find innovators and early adopters
> 2. Build critical mass and silent majority
> 3. Identify the holdouts
>
> »

#### Conclusion (p. 60)

> (p. 60) Peter Drucker: «little fish learn to be big fish in little ponds.»

- start small to de-risk (early + quick wins)
- build support
- earn right to expand
- iterate to keep growing

Chapter 6: Understanding the work in our value stream, making it visible, and expanding it across the organization (p. 61)
-----------------------------------------------------

> (p. 61) «...\[Nordstrom\] learned that one of the most efficient ways to start improving any value stream is to conduct a workshop with all the major stakeholders and perform a value stream mapping exercise ... to help capture ll the steps required to create value.»

-> (p. 62) Nordstrom's workshop about the Cosmetics Business Office revealed that the COBOL/Mainframe portion was NOT what would improve the UX the most: «Processing time was further reduced to seconds» once they moved to an iPad app with the streamlined fields, performing a global optimization only possible with a 10 000-foot view, through experimentation.

#### Identifying the teams supporting our value stream (p. 63)

Potential members (contributors to value stream)

- product owner
- development
- QA
- operations
- infosec
- release managers
- technology executives or value stream manager

#### Create a value stream map to see the work (p. 63)

> (p. 64) «Our goal is... to sufficiently understand the areas in our value stream that are jeopardizing our goals of fast flow, short lead times and reliable customer outcomes. Ideally, we have assembled those people with the authority to change their portion of the value stream.»

> (p. 64) «...we should focus our investigation and scrutiny on the following areas:
>
> - places where work must wait [a long time]
> - places where significant rework is generated or received
>
> »

- (p. 65) start w/«high-level process blocks»
    - lead time
    - process time
    - % C/A (percent complete + accurate, based on consumer)
- pick metrics to improve & understand problem
- draw ideal value stream map (3-12 month target)
- experiment & iterate

#### Creating a dedicated transformation team (p. 66)

Need:

- "disruptive innovation" to improve the status quo
- [dedicated team] "that is able to operate outside of the rest of the organization that is responsible for daily operations"
- "clearly defined, measurable, system-level result"
- sole focus, not partial commitment
- generalists
- connected people
- separate physical space

##### Agree on a shared goal (p. 68)

- 6-24 months
- an agile-like process is described for iterative progress & value

##### Keep our improvement planning horizon short

- measurable improvements within weeks
- flexibility
- short feedback loop, virtuous cycle
- learn faster
- easier start
- faster sharing
- less risk of being cancelled due to lack of visible progress

##### Reserve 20% of cycles for non-functional requirements and reducing technical debt (p. 69)

- refactoring
- automation
- non-functional requirements

(p. 70) Figure 11: Positive-negative value vs. visible-invisible

Marty Cagan and the "20% tax".

##### Case Study: Operation InVersion at LinkedIn (2011) (p. 71)

> (p. 71) «...where they stopped all feature development for two months in order to overhaul their computing environments, deployments, and architecture.»

> (p. 72) «...have a series of automated systems examine the code for any bugs...»

- "safer system of work"
- "your job ... is to help your company win"

##### Increase the visibility of work (p. 73)

#### Use tools to reinforce desired behaviour (p. 73)

- Dev & Ops
    - shared goals
    - common backlog
    - shared vocabulary
    - work prioritized globally
- "...instead of each silo using a different \[work queue\] (e.g. Development uses JIRA while Operations uses Service Now)"
- "...it will be obvious when ongoing incidents should halt other work..."
- encourages technical debt in backlog, almost separate
- chat rooms for sharing & searching
    - be careful of interruptions

Chapter 7: How to design our organization and architecture with Conway's Law in mind (p. 77)
------------------------------------------------------------------------------------------

> (p. 77) Conway's Law: «organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations...»

-> flexibility is inversely proportional to organization size

> (p. 78) «Done poorly [organizing our teams work work], Conway's Law will prevent teams from working safely and independently...»

"Sprouter" at Etsy tightly-coupled the front-end, middle and back-end teams such that they were often blocked on one another.

(p. 79) They moved business logic to the application layer "removing the need for Sprouter".

- decreased handoffs & coordinations
- increased speed & success of deployments & productivity

### Organizational Archetypes (p. 80)

3 structures of orgs: (Roberto Fernandez)

1. Functional: optimize for expertise & cost
2. Matrix: combine functional & market
3. Market: optimize for quick response

### Problems often caused by overly functional orientation ("Optimizing for cost") (p. 81)

> (p. 81) «In traditional IT operations, organizations...»
>
> - have «long lead times» due to handoffs
> - often have «little visibility or understanding of how their work relates to any value stream goals...»

> (p. 81) «In addition to long queues and long lead times, this situation results in poor handoffs, large amounts of re-work, quality issues, bottlenecks, and delay.»

> (p. 82) «However, as we increase the number of Development teams and their deployment and release frequencies, must functionally-oriented organizations will have difficulty keeping up and delivering satisfactory outcomes, especially when their work is being performed manually.»

### Enable market-oriented teams ("Optimizing for speed") (p. 82)

> (p. 82) «...to achieve DevOps outcomes, we need to reduce the effects of functional orientation and enable market orientation so we can have many small teams working safely and _independently_, quickly delivering value to the customer.»

> (p. 82) «...we won't do a large, top-down reorganization... Instead, we will embed the functional engineers and skills into each service team, or provide their capabilities [via self-service].»

### Making functional orientation work (p. 83)

> (p. 84) «Many of the most admired DevOps organizations retain functional orientation of Operations including Etsy, Google, and GitHub.»

> (p. 84) Mike Rother: «Toyota's success \[lies\] in developing capability and habits in its people.»

### Testing, operations, and security as everyone's job, every day (p. 84)

> (p. 84) «In high-performing organizations, everyone within the team shares a common goal - quality, availability, and security aren't the responsibility of individual departments but are a part of everyone's job, every day.»

(p. 85) Facebook improved deployments via on-call duty rotation for _everybody_.

### Enable every team member to be a generalist (p. 85)

> (p. 85) «In extreme cases of a functionally-oriented (...) \[over-specialization\] causes siloization (...)) then requires multiple handoffs and queues between the different areas of the infrastructure, leading to longer lead times...»

> (p. 85) «We don't want to create specialists who are "frozen in time", only understanding and able to contribute to that one area of the value stream.»

> (p. 86) «...\[provide\] opportunities for engineers to learn all the skills necessary to build and run the systems they are responsible for, and regularly rotating people through different roles.»

> (p. 86) «...generalists can do orders of magnitude more work than their specialist counterparts, and it also improves our overall flow of work by removing queues and wait time.»

> (p. 87) «the business benefits of \[generalists\] enabling faster flow are overwhelming.»

> (p. 87) «Investing in cross-training is the right thing for \[employees'\] career growth, and makes everyone's work more fun.»

- also in line with growth mindset!
- invest in people you already have

### Fund not projects, but services and products (p. 87)

> (p. 87) «create stable service teams with ongoing funding to execute their own strategy and road map of initiatives.  (...) see the long-term consequences of decisions they make (a form of feedback)»

> (p. 88) «Our goal with a product-based funding model is to value the achievement of organizational and customer outcomes, such as revenue, customer lifetime value, or customer adoption rate...»

### Design team boundaries in accordance with Conway's Law (p. 88)

> (p. 88) «Ideally, our software architecture should enable small teams to be independently-productive, sufficiently decoupled from each other so that work can be done without excessive or unnecessary communication and coordination.»

### Create loosely-coupled architectures to enable developer productivity and safety (p. 89)

> (p. 89) «Having architecture that is loosely coupled means that services can update in production independently, without having to update other services.»

> (p. 89) «Bounded contexts: \[independent\] services interact with their peers strictly through APIs and thus don't share data structures, database schemata, or other internal representations of objects (...) also enables easier testing.»

### Keep team sizes small (the "two-pizza team" rule) (p. 90)

-> 5-10 people

1. reduce communication
2. limits growth rate for product/service
3. enables autonomy, maximizing key business metric
4. failure is OK (safe environment)

(p. 90) Case study: API enablement at Target (2015)

> (p. 92) «...we wanted people with kickass engineering skills...»

### Conclusion (p. 93)

Align software architecture with organizational structure

Chapter 8: How to get great outcomes by integrating operations into the daily work of development (p. 95)
---------------------------------------------------------------------------------------------------

> (p. 95) «Our goal is to enable market-oriented outcomes where many small teams can quickly and independently deliver value to the customer.»

> (p. 95) «We can \[do this\] by better integrating Ops capabilities into Dev teams, making both more efficient and productive.»

Big Fish Games used to have centralized Ops and they extended into Dev teams via "Ops liaison".

(p. 96) 3 strategies:

1. Self-service capabilities
2. Embed Ops in service teams
3. Assign Ops liaisons otherwise

### Create shared services to increase developer productivity (p. 97)

a.k.a.: platform, toolchain

> (p. 97) «In almost all cases, we will not mandate that internal teams use these platforms and services...» (they have to compete w/external vendors)

> (p. 97) Netflix: «It's okay for people to be dependent on our tools, but it's important that they don't become dependent on us.»

### Embed Ops engineers into our service teams (p. 99)

Disney mixed ops, dev, test and infosec.

> (p. 99) «It has totally changed the dynamics of how we work.»

> (p. 100) «\[Embedded ops engineers\] will take part in all of the Dev team rituals, such as planning meetings, daily standups, and demonstrations where the team shows off new features and decides which ones to ship.»

Also great for cross-training & automation.

### Assign an Ops liaison to each service team (p. 100)

a.k.a. "designated ops", might be shared between teams, acts as a consultant/advocate.  Also attends meetings, etc.

### Integrate Ops into Dev rituals (p. 101)

Match the methodology, such as agile.

#### Invite Ops to our Dev standups (p. 102)

#### Invite Ops to our Dev retrospectives (p. 102)

> (p. 102) «This is one of the primary mechanisms where organizational learning and the development of countermeasures occurs, with resulting work implemented immediately or added to the team's backlog.»

-> feedback

> (p. 104) «We must remind everyone that improvement of daily work is more important than daily work itself, and that all teams must have dedicated capacity for this (...)»

-> pay down technical & process debt

#### Make relevant Ops work visible on shared kanban boards (p. 104)

- transparency to identify critical paths (such as blocked work) and work necessary to deliver value (i.e. deploy code) developed earlier
- visibility!

### Conclusion (p. 104)

### Part II conclusion (p. 105)
