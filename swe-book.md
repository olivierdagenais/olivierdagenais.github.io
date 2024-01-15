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


## [Chapter 9: Code Review](https://abseil.io/resources/swe-book/html/ch09.html)

### Code Review Flow

> The primary end goal of a code review is to get another engineer to consent to the change, which we denote by tagging the change as "looks good to me" (LGTM).

> It's important to remember (and accept) that code itself is a liability.   It might be a necessary liability, but by itself, code is simply a maintenance task to someone somewhere down the line.

> As much as a code review of entirely new code should not come out of the blue, the code review process itself should also not be viewed as an opportunity to revisit previous decisions.

### How Code Review Works at Google

> There are three aspects of review that require "approval" for any given change at Google:
> - A correctness and comprehension check from another engineer that the code is appropriate and does what the author claims it does. (...)
> - Approval from one of the code owners that the code is appropriate for this particular part of the codebase (and can be checked into a particular directory). (...)
> - Approval from someone with language "readability" that the code conforms to the language's style and best practices, checking whether the code is written in the manner we expect. (...)

There's also a bit about ownership/stewardship, driven by `OWNERS` files in the repository's tree structure.

### Code Review Benefits

> (The "code review every change") mandate does have a cost and effect on engineering velocity given that it does slow down the introduction of new code into a codebase and can impact time-to-production for any given code change.

#### Code Correctness

> Having another set of eyes look over a change helps ensure that the change does what was intended.  Reviewers typically look for whether a change has proper testing, is properly designed, and functions correctly and efficiently.

> The investment in the time for code review saved time otherwise spent in testing, debugging, and performing regressions, provided that the code review process itself was streamlined to keep it lightweight.

> A reviewer shouldn't propose alternatives because of personal opinion. Reviewers can propose alternatives, but only if they improve comprehension (by being less complex, for example) or functionality (by being more efficient, for example). In general, engineers are encouraged to approve changes that improve the codebase rather than wait for consensus on a more "perfect" solution. This focus tends to speed up code reviews.

> As tooling becomes stronger, many correctness checks are performed automatically through techniques such as static analysis and automated testing (though tooling might never completely obviate the value for human-based inspection of code(...)). 

> (...) code review does not need to be "perfect" to achieve results.

> (...) more importance is attached to ensuring that a code change is understandable and makes sense over time and as the codebase itself scales.

#### Comprehension of Code

> A code review is often the first test of whether a given change is understandable to a broader audience.

> It is often useful to find a reviewer who has a different perspective from the author, especially a reviewer who might need, as part of their job, to maintain or use the code being proposed within the change.

#### Code Consistency

>  Code (...) needs to conform to some standards of consistency so that it can be understood and maintained. (...) A code review (...) should act to ensure code _health_.

> Consistency sometimes clashes with functionality; a readability reviewer may prefer a less complex change that may not be functionally "better" but is easier to understand.

> With a more consistent codebase, it is easier for engineers to step in and review code on someone else's projects.

#### Psychological and Cultural Benefits

> Code review also has important cultural benefits: it reinforces to software engineers that code is not "theirs" but in fact part of a collective enterprise. (...) The code review process forces an author to not only let others have input, but to compromise for the sake of the greater good.

> Code review, when it works best, provides not only a challenge to an engineer's assumptions, but also does so in a prescribed, neutral manner, acting to temper any criticism which might otherwise be directed to the author if provided in an unsolicited manner.

> (...) the process of code review often provides a much gentler introduction for most engineers to the expectations of the team.

> Often, the process involves an exchange of ideas and knowledge sharing (...), which benefits both the reviewer and the reviewee.

> The process of initiating a code review also forces all authors to take a little extra care with their changes. (...) Without code review, it's natural that many of us would cut corners, even with the full intention of correcting such defects later. (...) The little moment of reflection that comes before sending off your change is the perfect time to read through your change and make sure you're not missing anything.

#### Knowledge Sharing

> One of the most important, but underrated, benefits of code review is in knowledge sharing. (...) The review process allows reviewers to impart domain knowledge to the author, allowing the reviewer(s) to offer suggestions, new techniques, or advisory information to the author.

> Part of the code review process of feedback and confirmation involves asking questions on why the change is done in a particular way.

> [An] engineer's primary task is still programming, of course, but a large chunk of their time is still spent in code review.

### Code Review Best Practices

> Keeping the code review process running smoothly requires a number of best practices to ensure that code review is worth the effort put into the process.

#### Be Polite and Professional

> It is critically important to keep all feedback and criticism firmly in the professional realm.

> In general, reviewers should defer to authors on particular approaches and only point out alternatives if the author's approach is deficient. (...) Reviewers should be careful about jumping to conclusions based on a code author's particular approach. It's better to ask questions on why something was done the way it was before assuming that approach is wrong.

> Reviewers should be prompt with their feedback.

> It's important to treat each reviewer comment within a code review as a TODO item; a particular comment might not need to be accepted without question, but it should at least be addressed. If you disagree with a reviewer's comment, let them know, and let them know why and don't mark a comment as resolved until each side has had a chance to offer alternatives.

#### Write Small Changes

> Probably the most important practice to keep the code review process nimble is to keep changes small. A code review should ideally be easy to digest and focus on a single issue, both for the reviewer and the author. (...) Smaller changes also prevent engineers from wasting time waiting for reviews on larger changes, reducing downtime. These small changes have benefits further down in the software development process as well. It is far easier to determine the source of a bug within a change if that particular change is small enough to narrow it down.

> A set of small, incremental code changes can be easier to digest individually, but more difficult to comprehend within a larger scheme. (...) Consider the optimization for small changes just that: an optimization, and allow your process to accommodate the occasional larger change.

> "Small" changes should generally be limited to about 200 lines of code. A small change should be easy on a reviewer and, almost as important, not be so cumbersome that additional changes are delayed waiting for an extensive review. (...) A small initial review also can prevent much more expensive wasted effort on an incorrect approach further down the line.

> Because code reviews are typically small, it's common for almost all code reviews at Google to be reviewed by one and only one person. Were that not the case - if a team were expected to weigh in on all changes to a common codebase - there is no way the process itself would scale.

> Keeping changes small also allows the "approval" reviewers to more quickly approve any given changes. They can quickly inspect whether the primary code reviewer did due diligence and focus purely on whether this change augments the codebase while maintaining code health over time.

#### Write Good Change Descriptions

> A change description should indicate its type of change on the first line, as a summary. The first line is prime real estate and is used to provide summaries within the code review tool itself, to act as the subject line in any associated emails, and to become the visible line Google engineers see in a history summary within Code Search, so that first line is important.

> Although the first line should be a summary of the entire change, the description should still go into detail on what is being changed and why. A description of "Bug fix" is not helpful to a reviewer or a future code archeologist. If several related modifications were made in the change, enumerate them within a list (while still keeping it on message and small). The description is the historical record for this change, and tools such as Code Search allow you to find who wrote what line in any particular change in the codebase. Drilling down into the original change is often useful when trying to fix a bug.

> If, during the code review process, a new decision is reached, update the change description, or add appropriate comments within the implementation. A code review is not just something that you do in the present time; it is something you do to record what you did for posterity.

#### Keep Reviewers to a Minimum

> Most code reviews at Google are reviewed by precisely one reviewer.

> There is a tendency within the industry, and within individuals, to try to get additional input (and unanimous consent) from a cross-section of engineers. (...) The cost of additional reviewers quickly outweighs their value.

> In certain cases, it can be useful to get a particular change reviewed by multiple people, but even in those cases, those reviewers should focus on different aspects of the same change.

#### Automate Where Possible

> Opportunities to automate mechanical human tasks should be explored; investments in proper tooling reap dividends.

> One of the most important technological improvements regarding automation over the past few years is automatic static analysis of a given code change. Rather than require authors to run tests, linters, or formatters, the current Google code review tooling provides most of that utility automatically through what is known as _presubmits_. A presubmit process is run when a change is initially sent to a reviewer. Before that change is sent, the presubmit process can detect a variety of problems with the existing change, reject the current change (and prevent sending an awkward email to a reviewer), and ask the original author to fix the change first. Such automation not only helps out with the code review process itself, it also allows the reviewers to focus on more important concerns than formatting.

### Types of Code Reviews

> Code changes at Google generally fall into one of the following buckets (though there is sometimes overlap).

#### Greenfield Code Reviews

> A greenfield review is the most important time to evaluate whether the code will stand the test of time: that it will be easier to maintain as time and scale change the underlying assumptions of the code. (...) code is a liability, so the introduction of entirely new code should generally solve a real problem rather than simply provide yet another alternative. (...) A code review is not the time to debate design decisions already made in the past (and by the same token, a code review is not the time to introduce the design of a proposed API).

> To ensure that code is sustainable, a greenfield review should ensure that an API matches an agreed design (which may require reviewing a design document) and is tested fully, with all API endpoints having some form of unit test, and that those tests fail when the code's assumptions change. (...) The code should also have proper owners (one of the first reviews in a new project is often of a single OWNERS file for the new directory), be sufficiently commented, and provide supplemental documentation, if needed.  A greenfield review might also necessitate the introduction of a project into the continuous integration system. 

#### Behavioral Changes, Improvements, and Optimizations

> (...) the guidelines that apply to a greenfield review also apply: is this change necessary, and does this change improve the codebase? Some of the best modifications to a codebase are actually deletions! Getting rid of dead or obsolete code is one of the best ways to improve the overall code health of a codebase.

> (...) optimizations should of course ensure that they don't affect those tests and might need to include performance benchmarks for the reviewers to consult.

#### Bug Fixes and Rollbacks

> Inevitably, you will need to submit a change for a bug fix to your codebase. _When doing so, avoid the temptation to address other issues._ Not only does this risk increasing the size of the code review, it also makes it more difficult to perform regression testing or for others to roll back your change. A bug fix should focus solely on fixing the indicated bug and (usually) updating associated tests to catch the error that occurred in the first place.

> Addressing the bug with a revised test is often necessary. The bug surfaced because existing tests were either inadequate, or the code had certain assumptions that were not met. As a reviewer of a bug fix, it is important to ask for updates to unit tests if applicable.

> It also becomes critically important that any change that could cause a potential rollback (and that includes all changes!) be as small and atomic as possible so that a rollback, if needed, does not cause further breakages on other dependencies that can be difficult to untangle.

#### Refactorings and Large-Scale Changes

> Many changes at Google are automatically generated: the author of the change isn't a person, but a machine. (...) even machine-generated changes require review.

### Conclusion

> Code review acts as the glue connecting engineers with one another, and the code review process is the primary developer workflow upon which almost all other processes must hang, from testing to static analysis to CI. A code review process must scale appropriately, and for that reason, best practices, including small changes and rapid feedback and iteration, are important to maintain developer satisfaction and appropriate production velocity.

### TL;DRs

> - Code review has many benefits, including ensuring code correctness, comprehension, and consistency across a codebase.
> - Always check your assumptions through someone else; optimize for the reader.
> - Provide the opportunity for critical feedback while remaining professional.
> - Code review is important for knowledge sharing throughout an organization.
> - Automation is critical for scaling the process.
> - The code review itself provides a historical record. 


## [Chapter 12: Unit Testing](https://abseil.io/resources/swe-book/html/ch12.html)

> We use the term _unit test_ to refer to tests of relatively narrow scope, such as of a single class or method. Unit tests are usually small in size, but this isn't always the case.

Properties of unit tests:
- small (therefore fast and deterministic)
- easy to write
- promote high code coverage
- easy to understand why the fail
- useful as documentation & examples

> (...) we encourage engineers to aim for a mix of about 80% unit tests and 20% broader-scoped tests.

### The Importance of Maintainability

Because tests are meant to improce productivity, it is important that they NOT be _brittle_, nor _unclear_.

### Preventing Brittle Tests

> (...) a  brittle test is one that fails in the face of an unrelated change to production code that does not introduce any real bugs.

(a flaky test is one that fails intermittently, without any changes to production code)

#### Strive for Unchanging Tests

> Therefore, _the ideal test is unchanging_: after it's written, it never needs to change unless the requirements of the system under test change.

> Fundamentally, there are four kinds of changes:
> 1. Pure refactorings (tests shouldn't change)
> 2. New features (tests should only be added)
> 3. Bug fixes (tests should only be added)
> 4. Behavior changes (tests could need to change)

Only the last one should result in test changes.

#### Test via Public APIs

> If tests work the same way as the system's users, by definition, change that breaks a test might also break a user.

> Testing only these contracts means that you're free to do whatever internal refactoring of the system you want without having to worry about making tedious changes to tests.

> Defining an appropriate scope for a unit  and hence what should be considered the public API is more art than science (...)

> At Google, we've found that engineers sometimes need to be persuaded that testing via public APIs is better than testing against implementation details. (...) Testing against public APIs won't completely prevent brittleness, but it's the most important thing you can do to ensure that your tests fail only in the event of meaningful changes to your system.

#### Test State, Not Interactions

> With _state testing_, you observe the system itself to see what it looks like after invoking with it. With _interaction testing_, you instead check that the system took an expected sequence of actions on its collaborators in response to invoking it.

The former is preferred because the latter is more brittle.

> (...) we tend to prefer the use of real objects in favor of mocked objects, as long as the real objects are fast and deterministic.

### Writing Clear Tests

> A clear test is one whose purpose for existing and reason for failing is immediately clear to the engineer diagnosing a failure. (...) Clear tests also bring other benefits, such as documenting the system under test and more easily serving as a basis for new tests.

#### Make Your Tests Complete and Concise

> A test is _complete_ when its body contains all of the information a reader needs in order to understand how it arrives at its result. A test is _concise_ when it contains no other distracting or irrelevant information.

> (...) it can often be worth violating the DRY (Don't Repeat Yourself) principle if it leads to clearer tests.

#### Test Behaviors, Not Methods

> (...) rather than writing a test for each method, write a test for each _behavior_. A behavior is any guarantee that a system makes about how it will respond to a series of inputs while in a particular state.

##### Structure tests to emphasize behaviors

> When a test does want to validate each step in a multistep process, it's acceptable to define alternating sequences of when/then blocks. Long blocks can also be made more descriptive by splitting them up with the word "and."

##### Name tests after the behavior being tested

> A good name describes both the actions that are being taken on a system and the expected outcome.

#### Don't Put Logic in Tests

> Clear tests are trivially correct upon inspection (...) if you feel like you need to write a test to verify your test, something has gone wrong!

> (...) in test code, stick to straight-line code over clever logic, and consider tolerating some duplication when it makes the test more descriptive and meaningful.

#### Write Clear Failure Messages

> A good failure message contains much the same information as the test's name: it should clearly express the desired outcome, the actual outcome, and any relevant parameters.

> Good libraries can help make it easier to write useful failure messages.

[Truth - Fluent assertions for Java and Android](https://truth.dev/)

### Tests and Code Sharing: DAMP, Not DRY

> (...) DRY doesn't have quite as much benefit when it comes to test code.

> (...) test code should often strive to be DAMP—that is, to promote "Descriptive And Meaningful Phrases." A little bit of duplication is OK in tests so long as that duplication makes the test simpler and clearer.

> DAMP is not a replacement for DRY; it is complementary to it.

#### Shared Values

Rather than declaring "constants" of special instances (which might be tricky to name descriptively enough), make it easier to create instances via helper methods, the _Builder_ pattern and/or [AutoValue](https://github.com/google/auto/tree/main/value)/[Record Classes](https://docs.oracle.com/en/java/javase/16/language/records.html).

#### Shared Setup

Beware configuring values in test setup methods that are used in tests.  Only configure default values that aren't used in tests.

#### Shared Helpers and Validation

Beware creating helper methods, used at the end of every test, that assert on many things at once.  They make the tests more brittle and less focused on specific behaviours.  Assertion helpers are OK.

#### Defining Test Infrastructure

> Test infrastructure needs to be treated as its own separate product, and accordingly, _test infrastructure must always have its own tests_.

> A huge number of \[third-party test infrastructure] libraries are available, and standardizing on them within an organization should happen as early and universally as possible.

### Conclusion

> (...) careless use of unit testing can result in a system that requires much more effort to maintain and takes much more effort to change without actually improving our confidence in said system.

### TL;DRs

- Strive for unchanging tests.
- Test via public APIs.
- Test state, not interactions.
- Make your tests complete and concise.
- Test behaviors, not methods.
- Structure tests to emphasize behaviors.
- Name tests after the behavior being tested.
- Don't put logic in tests.
- Write clear failure messages.
- Follow DAMP over DRY when sharing  code for tests.

## [Chapter 13: Test Doubles](https://abseil.io/resources/swe-book/html/ch13.html)

### The Impact of Test Doubles on Software Development

> To use test doubles, a codebase needs to be designed to be _testable_ - it should be possible for tests to swap out real implementations with test doubles.

> Unit tests that use test doubles often need to be supplemented by larger-scope tests that exercise the real implementation.

### Test Doubles at Google

> One lesson we learned the hard way is the danger of overusing mocking frameworks, which allow you to easily create test doubles.

### Basic Concepts

#### An Example Test Double

> Although this test double doesn't look very useful, using it in a test still allows us to test some of the logic in the `makePayment()` method. For example, we can validate that the method behaves properly when the credit card is expired because the code path that the test exercises doesn't rely on the behavior of the credit card service.

#### Seams

> Code is said to be _testable_ if it is written in a way that makes it possible to write unit tests for the code.  A seam is a way to make code testable by allowing for the use of test doubles - it makes it possible to use different dependencies for the system under test rather than the dependencies used in a production environment.

> (...) when a class utilizes [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection), any classes it needs to use (i.e., the class's _dependencies_) are passed to it rather than instantiated directly, making it possible for these dependencies to be substituted in tests.

> Writing testable code requires an upfront investment. (...) Code written without testing in mind typically needs to be refactored or rewritten before you can add appropriate tests.

#### Mocking Frameworks

> A _mocking framework_ is a  software  library that makes it easier to create test doubles within tests; it allows you to replace an object with a _mock_, which is a test double whose behavior is specified inline in a test.

> Although mocking frameworks facilitate easier usage of test doubles, they come with some significant caveats given that their overuse will often make a codebase more difficult to maintain.

### Techniques for Using Test Doubles

> There are three primary techniques for using test doubles.

#### Faking

> A [fake](http://xunitpatterns.com/Fake%20Object.html) is a lightweight implementation of an API that behaves similar to the real implementation but isn't suitable for production; for example, an in-memory database.

> Using a fake is often the ideal technique when you need to use a test double, but a fake might not exist for an object you need to use in a test, and writing one can be challenging because you need to ensure that it has similar behavior to the real implementation, now and in the future.

#### Stubbing

> [Stubbing](http://xunitpatterns.com/Test%20Stub.html) is the process of giving behavior to a function that otherwise has no behavior on its own—you specify to the function exactly what values to return (that is, you stub the return values).

> Stubbing is typically done through mocking frameworks to reduce boilerplate that would otherwise be needed for manually creating new classes that hardcode return values.

#### Interaction Testing

> [Interaction testing](http://xunitpatterns.com/Behavior%20Verification.html) is a way to validate how a function is called without actually calling the implementation of the function.  A test should fail if a function isn't called the correct way—for example, if the function isn't called at all, it's called too many times, or it's called with the wrong arguments.

> Similar to stubbing, interaction testing is typically done through mocking frameworks.  This reduces boilerplate compared to manually creating new classes that contain code to keep track of how often a function is called and which arguments were passed in.

### Real Implementations

> Although test doubles can be  invaluable testing tools, our first choice for tests is to use the real implementations of the system under test's dependencies; that is, the same implementations that are used in production code.

#### Prefer Realism Over Isolation

> We prefer realistic tests because they give more confidence that the system under test is working properly.

> Using real implementations can cause your test to fail if there is a bug in the real implementation. This is good! You _want_ your tests to fail in such cases because it indicates that your code won't work properly in production.

#### How to Decide When to Use a Real Implementation

> A real implementation is preferred if it is fast, deterministic, and has simple dependencies.

> (...) you need to take the following considerations into account:
> 1. Execution time: use real implementation until it is too slow to use, also build & test in parallel if you can
> 2. Determinism: use real implementation unless it is flaky
> 3. Dependency construction; consider the same object graph (and injection) than production for authenticity

### Faking

> If using a real implementation is not feasible within a test, the best option is often to use a fake in its place (...) because it behaves similarly to the real implementation (...)

#### Why Are Fakes Important?

> (...) they execute quickly and allow you to effectively test your code without the drawbacks of using real implementations.

#### When Should Fakes Be Written?

> A fake requires more effort and more domain experience to create because it needs to behave similarly to the real implementation. (...) the team that owns the real implementation should write and maintain a fake.

Fakes are worth the investment if hundreds of users would use them, less so for a handful of users.

#### The Fidelity of Fakes

> If the behavior of a fake doesn't match the behavior of the real implementation, a test using that fake is not useful (...)

> (...) the fake must have perfect fidelity to the real implementation, but _only from the perspective of the test_.

> It is best to have the fake fail fast in \[the case of rare edge cases]; for example, raise an error if an unsupported code path is executed. 

#### Fakes Should Be Tested

> A fake without tests might initially provide realistic behavior, but without tests, this behavior can diverge over time as the real implementation evolves.

#### What to Do If a Fake Is Not Available

> If a fake is not available, first ask the owners of the API to create one.

> If the owners of an API are unwilling or unable to create a fake, you might be able to write your own. One way to do this is to wrap all calls to the API in a single class and then create a fake version of the class that doesn't talk to the API.

### Stubbing

> (...) stubbing is a way for a test to hardcode behavior for a function that otherwise has no behavior on its own.

#### The Dangers of Overusing Stubbing

> (...) overuse of stubbing can result in major losses in productivity for engineers who need to maintain these tests.
> 1. Tests become unclear (due to extra code)
> 2. Tests become brittle (implementation details leak into tests)
> 3. Tests become less effective (stubs may differ from real implementation)

#### When Is Stubbing Appropriate?

> A test that requires many functions to be stubbed can be a sign that stubbing is being overused, or that the system under test is too complex and should be refactored.

### Interaction Testing

#### Prefer State Testing Over Interaction Testing

> In contrast to interaction testing, it is preferred to test code through [state testing](http://xunitpatterns.com/State%20Verification.html).

If you're not careful, you end up exposing details of the implementation to your tests and make them very brittle.

#### When Is Interaction Testing Appropriate?

> (If you) cannot perform state testing because you are unable to use a real implementation or a fake (e.g., if the real implementation is too slow and no fake exists).

> If you are not able to perform state testing in a unit test, strongly consider supplementing your test suite with larger-scoped tests that do perform state testing.

#### Best Practices for Interaction Testing

> Prefer to perform interaction testing only for _state-changing_ functions (that have side-effects on the world, like sending an e-mail)

> Avoid overspecification (focus on testing behaviours over methods, one behaviour per test)

### Conclusion

Test doubles are meant to make tests run faster, but be careful to not make tests unclear, brittle and/or less effective.

### TL;DRs

> - A real implementation should be preferred over a test double.
> - A fake is often the ideal solution if a real implementation can't be used in a test.
> - Overuse of stubbing leads to tests that are unclear and brittle.
> - Interaction testing should be avoided when possible: it leads to tests that are brittle because it exposes implementation  details of the system under test.

## [Chapter 20: Static Analysis](https://abseil.io/resources/swe-book/html/ch20.html)

> Static analysis refers to programs analyzing source code to find potential issues such as bugs, antipatterns, and other issues that can be diagnosed _without executing the program_. (...) Through static analysis at Google, we codify best practices, help keep code current to modern API versions, and prevent or reduce technical debt.  Examples of these analyses include verifying that naming conventions are upheld, flagging the use of deprecated APIs, or pointing out simpler but equivalent expressions that make code easier to read.

### Characteristics of Effective Static Analysis

#### Scalability

> Instead of analyzing entire large projects, we focus analyses on files affected by a pending code change, and typically show analysis results only for edited files or lines. (...) Google static analysis infrastructure avoids bottlenecking analysis results by showing them directly to relevant engineers.

#### Usability

> (...) we generally focus on newly introduced warnings; existing issues in otherwise working code are typically only worth highlighting (and fixing) if they are particularly important (security issues, significant bug fixes, etc.)

> If the analysis author can save time (e.g., by providing a fix that can be automatically applied to the code in question), the cost in the trade-off goes down.

> A further strength of homogenizing everything in one workflow is that a dedicated tools team can update tools along with workflow and code, allowing analysis tools to evolve with the source code in tandem.

### Key Lessons in Making Static Analysis Work

#### Focus on Developer Happiness

> (...) we also keep track of how well analysis tools are performing. If you don't measure this, you can't fix problems. We only deploy analysis tools with low false-positive rates (...)

> Furthermore, _perception_ is a key aspect of the false-positive rate. If a static analysis tool is producing warnings that are technically correct but misinterpreted by users as false positives (e.g., due to confusing messages), users will react the same as if those warnings were in fact false positives.

#### Make Static Analysis a Part of the Core Developer Workflow

> At Google, we integrate static analysis into the core workflow via integration with code review tooling. Essentially all code committed at Google is reviewed before being committed; because developers are already in a change mindset when they send code for review, improvements suggested by static analysis tools can be made without too much disruption. (...) static analysis can save reviewer time by highlighting common issues automatically; static analysis tools help the code review process (and the reviewers) scale.

#### Empower Users to Contribute

> Static analysis is an opportunity to leverage expertise and apply it at scale by having domain experts write new analysis tools or individual checks within a tool.

### Tricorder: Google's Static Analysis Platform

> (...) the key difference between Tricorder and previous attempts was our relentless focus on having Tricorder deliver only valuable results to its users.

> There are four criteria for new Tricorder checks:
> 1. Be understandable
> 2. Be actionable and easy to fix
> 3. Produce less than 10% effective false positives
> 4. Have the potential for significant impact on code quality

#### Integrated Tools

> [Error Prone](http://errorprone.info/) and [clang-tidy](https://clang.llvm.org/extra/clang-tidy/) extend the compiler to identify AST antipatterns for Java and C++, respectively.

> Other analyzers showcase relationships between disparate files in a corpus.

> (...) many projects have enabled a binary size checker that warns when changes significantly affect a binary size.

#### Integrated Feedback Channels

> With Tricorder, we display the option to click a "Not useful" button on an analysis result; this click provides the option to file a bug directly against the analyzer writer about why the result is not useful with information about analysis result prepopulated.

#### Suggested Fixes

> Automated fixes serve as an additional documentation source when the message is unclear and, as mentioned earlier, reduce the cost to addressing static analysis issues. (...) We take the approach that style issues in particular should be fixed automatically; for example, by formatters that automatically reformat source code files.

#### Per-Project Customization

Don't allow users to customize analysis just for them; ask them why they would want to "customize" and it will usually turn up as a defect/improvement.

#### Presubmits

> Because developers can choose to ignore static analysis warnings displayed in code review, Google additionally has the ability to add an analysis that blocks committing a pending code change, which we call a _presubmit check_.

#### Compiler Integration

> When possible, we try to push static analysis into the compiler.

> To enable a new check, we first need to clean up all instances of that problem in the codebase so that we don't break the build for existing projects just because the compiler has evolved.

I remember reading a blog post that claims it's this discipline in keeping code tidy that causes Google to break so many things and kill off projects so aggressively.

> We also aim to never issue compiler warnings. We have found repeatedly that developers ignore compiler warnings. We either enable a compiler check as an error (and break the build) or don't show it in compiler output.

#### Analysis While Editing and Browsing Code

(...) IDE analyses require quick analysis times (typically less than 1 second and ideally less than 100 ms), and so some tools are not suitable to integrate here. (...) IDE integration tends to be messier than plugging into the review process.

### Conclusion

> Static analysis can be a great tool to improve a codebase, find bugs early, and allow more expensive processes (such as human review and testing) to focus on issues that are not mechanically verifiable.

### TL;DRs

> 1. Focus on developer happiness.
> 2. Make static analysis part of the core developer workflow.
> 3. Empower users to contribute.
