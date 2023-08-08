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

## [Chapter 3: Knowledge Sharing](https://abseil.io/resources/swe-book/html/ch03.html)

> Most importantly, however, your organization needs a _culture of learning_, and that requires creating the psychological safety that permits people to admit to a lack of knowledge.

### Challenges to Learning

> - Lack of psychological safety
> - Information islands
>     - Information fragmentation
>     - Information duplication
>     - Information skew
> - Single point of failure (SPOF)
> - All-or-nothing expertise
> - Parroting
> - Haunted graveyards

### Philosophy

> Every expert was once a novice: an organization's success depends on growing and investing in its people.
> Written knowledge has scaling advantages, but so does targeted human help. A human expert can synthesize their expanse of knowledge. They can assess what information is applicable to the individual's use case, determine whether the documentation is still relevant, and know where to find it. Or, if they don't know where to find the answers, they might know who does.

### Setting the Stage: Psychological Safety

#### Mentorship
#### Psychological Safety in Large Groups

### Growing Your Knowledge

#### Ask Questions
#### Understand Context

### Scaling Your Questions: Ask the Community

#### Group Chats
#### Mailing Lists
#### YAQS: Question-and-Answer Platform

### Scaling Your Knowledge: You Always Have Something to Teach

#### Office Hours
#### Tech Talks and Classes
#### Documentation
#### Code

### Scaling Your Organization's Knowledge

#### Cultivating a Knowledge-Sharing Culture
#### Establishing Canonical Sources of Information
#### Staying in the Loop

### Readability: Standardized Mentorship Through Code Review

#### What Is the Readability Process?
#### Why Have This Process?

### Conclusion

### TL;DRs

## [Chapter 5: How to Lead a Team](https://abseil.io/resources/swe-book/html/ch05.html)

> Although this chapter is about people management and technical leadership, it is still worth a read if you're an individual contributor because it will likely help you understand your own leaders a bit better.

### Managers and Tech Leads (and Both)

#### The Engineering Manager

> Google decided early on, however, that its software engineering managers should have an engineering background.

#### The Tech Lead

> Most TLs are also individual contributors, which often forces them to choose between doing something quickly themselves or delegating it to a team member to do (sometimes) more slowly. The latter is most often the correct decision for the TL as they grow the size and capability of their team. 

#### The Tech Lead Manager

> The job of TLM is a tricky one and often requires the TLM to learn how to balance individual work, delegation, and people management.

### Moving from an Individual Contributor Role to a Leadership Role

> We're not here to attempt to convince you to become a manager, but rather to help show why the best leaders work to serve their team using the principles of humility, respect, and trust.

#### The Only Thing to Fear Is...Well, Everything

> Quantifying management work is more difficult than counting widgets you turned out, but just making it possible for your team to be happy and productive is a big measure of your job. Just don't fall into the trap of counting apples when you're growing bananas.

> Even if you're great at writing code, there's still an upper limit to the amount of code you can write. Imagine how much code a team of great engineers could write under your leadership!

#### Servant Leadership

> The cure for the "management" disease is a liberal application of "servant leadership," which is a nice way of saying the most important thing you can do as a leader is to serve your team, much like a butler or majordomo tends to the health and well-being of a household.

### The Engineering Manager

#### Manager Is a Four-Letter Word

> (...) numerous studies [suggest] that the anachronistic carrot and stick is ineffective and harmful to the productivity of creative people.

#### Today's Engineering Manager

> To frame this in the context of humility, respect, and trust: if a manager makes it obvious that they trust their employee, the employee feels positive pressure to live up to that trust. It's that simple.

> If your employees are so uninterested in their job that they actually need traditional-manager babysitting to be convinced to work, _that_ is your real problem.

> A good way to build a culture in which risk taking is accepted is to let your team know that it's OK to fail.

> In addition, it's important to see failure as an opportunity to learn and not to point fingers or assign blame. Failing fast is good because there's not a lot at stake.

> It's alright to fail, but fail as a team and learn from your failures. If an individual succeeds, praise them in front of the team. If an individual fails, give constructive criticism in private.

### Antipatterns

> We've observed these destructive patterns in a handful of bad managers that we've encountered in our careers, and in more than a few cases, ourselves.

#### Antipattern: Hire Pushovers

> Even though this will cement your position as the team leader and decision maker, it will mean a lot more work for you. (...) If you build a team of pushovers, you probably can't take a vacation; the moment you leave the room, productivity comes to a screeching halt.

#### Antipattern: Ignore Low Performers

> Google's Site Reliability Engineering (SRE) team has a motto: "Hope is not a strategy." And nowhere is hope more overused as a strategy than in dealing with a low performer. Most team leaders grit their teeth, avert their eyes, and just _hope_ that the low performer either magically improves or just goes away. Yet it is extremely rare that this person does either.

#### Antipattern: Ignore Human Issues

> Now that you're a manager, however, you ignore the human element of your team at your own peril.

#### Antipattern: Be Everyone's Friend

> Don't confuse friendship with leading with a soft touch: when you hold power over someone's career, they might feel pressure to artificially reciprocate gestures of friendship.

#### Antipattern: Compromise the Hiring Bar

> The cost of finding the appropriate person—whether by paying recruiters, paying for advertising, or pounding the pavement for references—pales in comparison to the cost of dealing with an employee who you never should have hired in the first place.

#### Antipattern: Treat Your Team Like Children

> The best way to show your team that you don't trust it is to treat team members like kids (...)

> (...) what about the costs of having a workforce that behaves like children or that has to waste valuable time formally requesting cheap office supplies? Surely  that's more  expensive than the price of a few pens and USB cables.

### Positive Patterns

> These patterns are not only those that we've had great success implementing, but the patterns that we've always respected the most in the leaders who we follow.

#### Lose the Ego

> You can still have self-confidence and opinions without being an egomaniac.

> Part of "losing the ego" is trust: you need to trust your team. 

> If you have a good team and you let it set the bar for the quality and rate of its work, it will accomplish more than by you standing over team members with a carrot and a stick.

> We can assure you that you will not get everything right, nor will you have all the answers, and if you act like you do, you'll quickly lose the respect of your team.

> Try to appreciate inquiry: when someone questions a decision or statement you made, remember that this person is usually just trying to better understand you.

> The last part of losing the ego is a simple one, but many engineers would rather be boiled in oil than do it: apologize when you make a mistake. (...) You are absolutely going to make mistakes, and whether or not you admit it, your team is going to know you've made a mistake.

#### Be a Zen Master

> (...) you would do well to be less vocally skeptical while still letting your team know you're aware of the intricacies and obstacles involved in your work. Mediating your reactions and maintaining your calm is more important as you lead more people (...)

> As a leader, your job is to inspire, but inspiration is a 24/7 job. Your visible attitude about absolutely everything - no matter how trivial - is unconsciously noticed and spreads infectiously to your team.

> The person asking for advice typically doesn't want _you_ to solve their problem, but rather to help them solve it, and the easiest way to do this is to ask this person questions. (...)  try to help the person solve the problem on their own by trying to refine and explore the problem.

#### Be a Catalyst

> One of the most common things a team leader does is to build consensus.  This might mean that you drive the process from start to finish, or you just give it a gentle push in the right direction to speed it up.

#### Remove Roadblocks

> jumping in to help the team get moving again (from being stuck due to a roadblock) is a common leadership technique.

> In many cases, knowing the right person is more valuable than knowing the right answer.

#### Be a Teacher and a Mentor

> A good mentor must balance the trade-offs of a mentee's time learning versus their time contributing to their product as part of an effective effort to scale the team as it grows.

> (...) giving your mentee enough information is what you're supposed to be doing, but if you overexplain things or ramble on endlessly, your mentee will probably tune you out rather than politely tell you they got it.

#### Set Clear Goals

> If you're going to get your team moving rapidly in one direction, you need to make sure that every team member understands and agrees on what the direction is. (...)  If you're going to have clear goals, you need to set clear priorities and help your team decide how it should make trade-offs when the time comes.

> The easiest way to set a clear goal and get your team pulling the product in the same direction is to create a concise mission statement for the team.

#### Be Honest

> If a team member approaches you about something you can't share, it's OK to just tell them you know the answer but are not at liberty to say anything. Even more common is when a team member asks you something you don't know the answer to: you can tell that person you don't know.

> We _strongly_ advise against using the compliment sandwich, not because we think you should be unnecessarily cruel or harsh, but because most people won't hear the critical message, which is that something needs to change. (...) kindness and empathy are critical if you want the recipient to hear the criticism and not immediately go on the defensive.

> When you're providing direct feedback or criticism, your delivery is key to making sure that your message is heard and not deflected.

#### Track Happiness

> As a leader, one way you can make your team more productive (and less likely to leave) in the long term is to take some time to gauge their happiness.

> A good simple way to track your team's happiness is to ask the team member at the end of each one-on-one meeting, "What do you need?"

### The Unexpected Question

> It can also be worthwhile as a leader to pay some attention to your team's happiness outside the office.

> A big part of tracking your team members' happiness is tracking their careers.

> Tracking happiness comes down to not just monitoring careers, but also giving your team members opportunities to improve themselves, be recognized for the work they do, and have a little fun along the way.

### Other Tips and Tricks

1. Delegate, but get your hands dirty
    > (...) one of the easiest ways to gain the team's respect and get up to speed on what they're doing is to get your hands dirty—usually by taking on a grungy task that no one else wants to do.
1. Seek to replace yourself
    > (...)  if you want a member of your team to replace you, you need to hire people capable of replacing you, which we usually sum up by saying that you need to "hire people smarter than you."
1. Know when to make waves
    Don't delay taking action on a difficult situation, especially if there's discomfort to address it.
1. Shield your team from chaos
    > (...) the chaos had always been present, but my previous manager had shielded me and the rest of my team from it.
1. Give your team air cover
    > Share as much information as you can with your team, but don't distract them with organizational craziness that is extremely unlikely to ever actually affect them.
1. Let your team know when they're doing well
    > Just as you let someone know when they screw up, be sure to let them know when they do well, and be sure to let them (and the rest of the team) know when they knock one out of the park.
1. It's easy to say "yes" to something that's easy to undo

### People Are Like Plants

> And so your team members are also like plants: some need more light, and some need more water (and some need more…fertilizer). It's your job as their leader to determine who needs what and then give it to them—except instead of light, water, and fertilizer, your team needs varying amounts of motivation and direction.

#### Intrinsic Versus Extrinsic Motivation

> There are two types of motivation: _extrinsic_, which originates from outside forces (such as monetary compensation), and _intrinsic_, which comes from within.  In his book _Drive_, Dan Pink explains that the way to make people the happiest and most productive isn't to motivate them extrinsically (e.g., throw piles of cash at them); rather, you need to work to increase their intrinsic motivation. Dan claims you can increase intrinsic motivation by giving people three things: autonomy, mastery, and purpose.

### Conclusion

> (...) the most important skills an effective manager brings to the table are social ones. Good managers enable their engineering teams by helping them work well, keeping them focused on proper goals, and insulating them from problems outside the group, all while following the three pillars of humility, trust, and respect.

### TL;DRs

* Don't "manage" in the traditional sense; focus on leadership, influence, and serving your team.
* Delegate where possible; don't DIY (Do It Yourself).
* Pay particular attention to the focus, direction, and velocity of your team.
