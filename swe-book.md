# [Software Engineering at Google](https://abseil.io/resources/swe-book)

Noteworthy excerpts from the book.

## [Chapter 1: What Is Software Engineering?](https://abseil.io/resources/swe-book/html/ch01.html)

### Time and Change

> Rather than take the natural approach by avoiding a painful task, sometimes the more responsible answer is to invest in making it less painful. It all depends on the cost of your upgrade, the value it provides, and the expected life span of the project in question.

### Policies That Don't Scale

Regarding upgrades to dependencies, such as compilers and libraries...

>  We've also learned that having a dedicated group of experts execute the change scales better than asking for more maintenance effort from every user: experts spend some time learning the whole problem in depth and then apply that expertise to every subproblem. Forcing users to respond to churn means that every affected team does a worse job ramping up, solves their immediate problem, and then throws away that now-useless knowledge. Expertise scales better.

### Policies That Scale Well

> One of our favorite internal policies is a great enabler of infrastructure teams, protecting their ability to make infrastructure changes safely. "If a product experiences outages or other problems as a result of infrastructure changes, but the issue wasn't surfaced by tests in our Continuous Integration (CI) system, it is not the fault of the infrastructure change." More colloquially, this is phrased as "If you liked it, you should have put a CI test on it," which we call "The Beyoncé Rule."

### Shifting Left

> One of the broad truths we've seen to be true is the idea that finding problems earlier in the developer workflow usually reduces costs.

### Software Engineering Versus Programming

> Programming is the immediate act of producing code. Software engineering is the set of policies, practices, and tools that are necessary to make that code useful for as long as it needs to be used and allowing collaboration across a team.

### TL;DRs

> Every task your organization has to do repeatedly should be scalable (linear or better) in terms of human input. Policies are a wonderful tool for making process scalable.

## [Chapter 2: How to Work Well on Teams](https://abseil.io/resources/swe-book/html/ch02.html)

### Help Me Hide My Code

> Can you spot a common theme to these requests? The answer is _insecurity_. People are afraid of others seeing and judging their work in progress.

### The Genius Myth

> Yet they all became leaders and symbols of the collective achievements of their communities. The Genius Myth is the tendency that we as humans need to ascribe the success of a team to a single person/leader.

> Being a genius is most definitely not an excuse for being a jerk: anyone — genius or not — with poor social skills tends to be a poor teammate.

### Hiding Considered Harmful

> If you spend all of your time working alone, you're increasing the risk of unnecessary failure and cheating your potential for growth.

> First of all, how do you even know whether you're on the right track?

#### Early Detection

> This is why people dip their toes in the water before jumping in the deep end: you need to make sure that you're working on the right thing, you're doing it correctly, and it hasn't been done before. The chances of an early misstep are high. The more feedback you solicit early on, the more you lower this risk.

#### The Bus Factor

> Bus factor (noun): the number of people that need to get hit by a bus before your project is completely doomed.

> Hopefully most engineers recognize that it is better to be one part of a successful project than the critical part of a failed project.

#### Pace of Progress

> Programmers work best in tight feedback loops: write a new function, compile. Add a test, compile. Refactor some code, compile. This way, we discover and fix typos and bugs as soon as possible after generating code.

> This is all bundled into the idea of "shifting left" in the developer workflow; the earlier we find a problem, the cheaper it is to fix it.

> Most engineers know the quote, "Many eyes make all bugs shallow," but a better version might be, "Many eyes make sure your project stays relevant and on track."

#### In Short, Don't Hide

### It's All About the Team

> Let's put this idea into simpler words: _software engineering is a team endeavor_.

#### The Three Pillars of Social Interaction

1. Humility
2. Respect
3. Trust

#### Why Do These Pillars Matter?

> The moral is this: do not underestimate the power of playing the social game. It's not about tricking or manipulating people; it's about creating relationships to get things done. Relationships always outlast projects. When you've got richer relationships with your coworkers, they'll be more willing to go the extra mile when you need them.

#### Humility, Respect, and Trust in Practice

1. Lose the ego
    1. > "The appearance of conforming gets you a long way."
2. Learn to give _and_ take criticism
    1. > To repeat ourselves: _you are not your code_.
    2. > Notice how you're using humility to make the question about you, not them. They're not wrong; you're just having trouble understanding the code. The suggestion is merely offered up as a way to clarify things for poor little you while possibly helping the project's long-term sustainability goals. You're also not demanding anything—you're giving your collaborator the ability to peacefully reject the suggestion. The discussion stays focused on the code itself, not on anyone's value or coding skills.
3. Fail fast and iterate
    1. > "Why would I fire you? I just spent $10 million training you!"
    2. > At Google, one of our favorite mottos is that "Failure is an option."

#### Blameless Post-Mortem Culture

> The key to learning from your mistakes is to document your failures by performing a root-cause  analysis and writing up a "postmortem," as it's called at Google (and many other companies).

> A proper postmortem should always contain an explanation of what was learned and what is going to change as a result of the learning experience.

> Don't erase your tracks—light them up like a runway for those who follow you!

> A good postmortem should include the following:
> * A brief summary of the event
> * A timeline of the event, from discovery through investigation to resolution
> * The primary cause of the event
> * Impact and damage assessment
> * A set of action items (with owners) to fix the problem immediately
> * A set of action items to prevent the event from happening again
> * Lessons learned

##### Learn patience

> Our patience and willingness to improvise new working styles not only saved the project, but also our friendship.

##### Be open to influence

> The more open you are to influence, the more you are able to influence; the more vulnerable you are, the stronger you appear.

> Choose your battles carefully: to be heard properly, you first need to listen to others.

> Sometimes, the best thing you can do is just say, "I don't know."

#### Being Googley

> Google eventually fixed the problem by explicitly defining a rubric for what we mean by "Googleyness"—a set of attributes and behaviors that we look for that represent strong leadership and exemplify "humility, respect, and trust":
> - Thrives in ambiguity
> - Values feedback
> - Challenges status quo
> - Puts the user first
> - Cares about the team
> - Does the right thing

### Conclusion

> Further, the creative nature of software development requires that people take risks and occasionally fail; for people to accept that failure, a healthy team environment must exist.

### TL;DRs

> - Be aware of the trade-offs of working in isolation.
> - Acknowledge the amount of time that you and your team spend communicating and in interpersonal conflict. A small investment in understanding personalities and working styles of yourself and others can go a long way toward improving productivity.
> - If you want to work effectively with a team or a large organization, be aware of your preferred working style and that of others.