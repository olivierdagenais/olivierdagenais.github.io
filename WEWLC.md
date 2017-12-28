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

PART II: Changing Software (p. 55)
==========================

Chapter 6: I Don't Have Much Time and I Have to Change It (p. 57)
---------------------------------------------------------

> (p. 57) «You don't know how long that work might have taken you if you hadn't written the tests.  You also don't know how much time it would've taken you to debug if you made a mistake, time you could have saved if you had tests in place.»

(p. 58) An experiment where a team spends an iteration with tests covering every change. «Ultimately, this is going to make your work go faster...»

(p. 59) «Pay now or pay more later.»

### Sprout Method (p. 59)

Write feature as new, tested method and call the new method as needed.

> (p. 62) «It is far preferable to adding code inline.»

> (p. 62) «When [**Pass Null (111)**] won't work [because constructor has a lot of arguments], consider making the sprout a public static method.  You might have to pass in instance variables of the source class as arguments, but it will allow you to make your change.»

### Sprout Class (p. 63)

Useful when **Sprout Method (59)** wouldn't work because there are many outputs.

### Wrap Method (p. 67)

Kind of like "extract method" refactoring & **Sprout Method (59)** so that the old code is in a new method alongside the new method for the new code and both new methods are called from the original method, in sequence.

### Wrap Class (p. 71)

Also known as Decorator Pattern.

(p. 75) Compares **Sprout Method (59)** to **Wrap Method (67)**, when you would use each.

### Summary (p. 76)

> (p. 76) «Yes, it is [more complicated] for now.  But when you really start to break out those 10 or 15 responsibilities in that wrapped class, it will look far more appropriate.»

Chapter 7: It Takes Forever to Make a Change (p. 77)
--------------------------------------------

### Understanding (p. 77)

### Lag Time (p. 78)

> (p. 78) «Systems that are broken up into small, well-named and understandable pieces enable faster work.»

### Breaking Dependencies (p. 79)

> (p. 80) «When we have these clusters of classes under test, we have the option of changing the physical structure of out project to make builds easier.  We do this by moving the clusters off to a new package or library.  Builds do become more complex when we do this, but here is the key:  As we break dependencies and section off classes into new packages or libraries, the overall cost of a rebuild of the entire system grows slightly, but the average time for a build can decrease dramatically.»

### Summary (p. 85)

Most of the chapter centers on introducing interfaces to speed up compilation time for platforms that support incremental compilation.

Chapter 8: How Do I Add a Feature? (p. 87)
----------------------------------

> «In general, it's better to confront the beast than hide from it.  If we can get code under test, we can use the techniques in this chapter to move forward in a good way.»

### Test-Driven Development (p. 88)

- the algorithm omits small commits
    - this is difficult w/o DVCS but even TFVC has tfgit!

> (p. 92) «Often, when we want to add features to particularly awful code, it's easier to understand our modifications if we put them in some new place and can see them side by side with the old code.»

> (p. 93) «Remove Duplication»

Make the tests pass first, then make the code better without changing behaviour, something that's easier to do w/TDD because all your behaviour is tested.

> (p. 94) «[with TDD] we are either writing code or refactoring; we are never doing both at once.»

### Programming by Difference (p. 94)

### Summary (p. 104)

Chapter 9: I Can't Get This Class into a Test Harness (p. 105)
-----------------------------------------------------

### The Case of the Irritating Parameter (p. 106)

(p. 108) Refers to **Extract Interface (362)**

> (p. 110) «The FakeConnection class is a little weird.» (It's a tool)

(p. 111) Refers to **Pass Null (111)**

(p. 112) Refers to **Null Object Pattern** and **Subclass and Override Method (401)**

### The Case of the Hidden Dependency (p. 113)

- **Parameterize Constructor (379)** & **Preserve Signatures (312)**
- **Extract and Override Getter (352)**
- **Extract and Override Factory Method (350)**
- **Supersede Instance Variable (404)**

### The Case of the Construction Blob (p. 116)

- **Extract and Override Factory Method (350)**
- **Supersede Instance Variable (404)**

### The Case of the Irritating Global Dependency (p. 118)

- (p. 122) **Introduce Static Setter (372)**
- Relax Singleton property, enforce unique instance w/o private constructor
- (p. 124) Protected constructor is an excellent trade-off
- (p. 125) **Extract Interface (362)**
- **Subclass and Override Method (401)**
- Eliminate global variables

### The Case of the Horrible Include Dependencies (p. 127)

C++-specific; include hell

### The Case of the Onion Parameter (p. 130)

- **Pass Null (111)**
- **Extract Interface (362)**

### The Case of the Aliased Parameter (p. 133)

- **Extract Interface (362)**
- **Subclass and Override Method (401)**

> (p. 136) «In many languages, we can create classes "on the fly" like this in methods.  Although I don't like to do it often in production code, it is very convenient when we are testing.  We can make special cases very easily.»

Chapter 10: I Can't Run This Method in a Test Harness (p. 137)
-----------------------------------------------------

> (p. 137) «If the method doesn't use much instance data, we can use **Expose Static Method (345)** to get access to the code.»

> (p. 137) «If the method is pretty long and difficult to deal with, we can use **Break Out Method Object (330)** to move the code to a class that we can instantiate more easily.»

### The Case of the Hidden Method (p. 138)

> (p. 138) «If we need to test a private method, we should make it public.»

(p. 138) An idea is to move private methods to a new class, as public methods.  Keep an instance of that new class as a semi-private field in the original class.

> (p. 139) «Good design is testable, and design that isn't testable is bad.»

(p. 140) Another idea is to increase the visibility from private to protected, then subclass for testing.

> (p. 141) «It might sound kind of sadistic, but the pain that we feel working in a legacy code base can be an incredible impetus to change.»

### The Case of the "Helpful" Language Feature (p. 141)

A collection of a sealed/final class means we need **Adapt Parameter (326)** or **Skin and Wrap the API (205)**.

(p. 143) «The only annoyance...» might be avoided with `IEnumerable<IHttpPostedFile>` and some LINQ extension methods.

### The Case of the Undetectable Side Effect (p. 144)

> (p. 145) «Perform a set of **Extract Method (415)** refactorings to divide up the work in this method.»

#### Command/Query Separation (p. 147)
> (p. 147) «A method should be a command or a query, but not both.  A command is a method that can modify the state of the object but that doesn't return a value.  A query is a method that returns a value but that does not modify the object.»

> (p. 148) «After those extractions, we can **Subclass and Override Method (401)**.»

> (p. 150) «Remember that it is okay to extract methods with poor names or poor structure to get tests in place.  Safety first.  After the tests are in place, you can make the code much cleaner.»
