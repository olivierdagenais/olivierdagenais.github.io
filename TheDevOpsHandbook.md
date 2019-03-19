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
