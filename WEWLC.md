Working Effectively With Legacy Code
====================================
A book summary by Olivier Dagenais

Preface
-------
> (p. xv) «[The teams] are trying very hard, but at the end of the day, because of schedule pressure, __the weight of history__, or a lack of any better code to comapre their efforts to, many people are writing legacy code.»

> (p. xvi) «To me, legacy code is simply code without tests.»

> (p. xvi) «Code without tests is bad code. It doesn't matter how well written it is; it doesn't matter how pretty or object-oriented or well-encapsulated it is.  With tests, we can change the behaviour of our code quickly and verifiably.  Without them, we really don't know if our code is getting better or worse.»

PART I: The Mechanics of Change (p. 1)
===============================

Chapter 1: Changing Software (p. 3)
----------------------------

### Four Reasons to Change Software (p. 4)

### Risky Change (p. 7)


Chapter 2: Working with Feedback (p. 9)
--------------------------------
> (p. 11) «A few minutes ago, we made a mistake and inverted the logic on a condition, but a test failed and we recovered in about a minute. (...) Do you want your feedback in a minute or overnight?»

### What Is Unit Testing? (p. 12)

> (p. 12) «Yes, we have to do [error localization] for unit tests also, but often the work is trivial because the tests are so small.»

> (p. 12) «Tests that take too long to run end up not being run.»

> (p. 13) «If we run our tests and they pass, and then we make a small change and they fail, we know precisely where the problem was triggered. It was something we did in that last small change. We can roll back the change and try again.»

> (p. 13) «A unit test that takes 1/10th of a second to run is a slow unit test.»

### Higher-Level Testing (p. 14)

### Test Coverings (p. 14)

p. 16 gives an example of **Primitive Parameter (385)**

> (p. 17) «The trick is to do these initial refactorings very conservatively.»

### The Legacy Code Change Algorithm (p. 18)
> 1. Identify change points
> 2. Find test points
> 3. Break dependencies
> 4. Write tests
> 5. Make changes and refactor

> (p. 20) «Remember that the things I describe in these chapters are "baby steps."»

> (p. 20) «Often the simplest things, [such as breaking down a large class just to make it easier to work with] can make a significant difference in applications, despite being somewhat mechanical.»
