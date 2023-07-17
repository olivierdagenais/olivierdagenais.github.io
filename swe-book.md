# [Software Engineering at Google](https://abseil.io/resources/swe-book)

Noteworthy excerpts from the book.

## [Chapter 1: What Is Software Engineering](https://abseil.io/resources/swe-book/html/ch01.html)

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
