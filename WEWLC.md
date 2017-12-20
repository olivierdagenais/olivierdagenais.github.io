Working Effectively With Legacy Code
====================================
A book summary by Olivier Dagenais

Preface
-------
> (p. xv) «[The teams] are trying very hard, but at the end of the day, because of schedule pressure, __the weight of history__, or a lack of any better code to compare their efforts to, many people are writing legacy code.»

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

Chapter 3: Sensing and Separation (p. 21)
---------------------------------
> (p. 21) «Generally, when we want to get tests in place, there are two reasons to break dependencies: sensing and separation.»

### Faking Collaborators (p. 23)

p. 23 Fake Objects

p. 27 Mock Objects

Chapter 4: The Seam Model (p. 29)
-------------------------

### A Huge Sheet of Text (p. 29)

### Seams (p. 30)

> (p. 31) «A seam is a place where you can alter behavior in your program without editing in that place.»

### Seam Types (p. 33)

> (p. 36) «Every seam has an enabling point, a place where you can make the decision to use one behavior or another.»

> (p. 44) «I like to reserve preprocessing seams and link seams for cases where dependencies are pervasive and there are no better alternatives.»

Chapter 5: Tools (p. 45)
----------------

### Automated Refactoring Tools (p. 45)

> (p. 45) «Refactoring (n.). A change made to the interval structure of software to make it easier to understand and cheaper to modify without changing its existing behavior.»

> (p. 46) «A change is a refactoring only if it doesn't change behavior.»

### Mock Objects (p. 47)

> (p. 47) «The web site www.mock-objects.com is a good place to find references for most of [the freely-available mock object libraries].»

### Unit-Testing Harnesses (p. 48)

> (p. 52) «If you need to find an xUnit port for your platform or language, go to www.xprogramming.com and look in the Downloads section.»

### General Test Harnesses (p. 53)

(p. 53) Framework for Integrated Tests (FIT)
> «FIT accepts HTML, runs tests defined in HTML tables in it, and produces HTML output.»

> «There is more information about FIT at http://fit.c2.com»
