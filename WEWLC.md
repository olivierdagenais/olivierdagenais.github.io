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

Chapter 11: I Need to Make a Change. What Methods Should I Test? (p. 151)
----------------------------------------------------------------

### Reasoning About Effects (p. 151)

> (p. 155) «Effect Sketches»

### Reasoning Forward (p. 157)

The effect sketches will help identify sense points (queries) and actions (commands) for our tests.

> (p. 157) «figuring out where change can be detected»

### Effect Propagation (p. 163)

> (p. 165) «Effects propagate in code in three basic ways: (...)»

> (p. 165) «Here is a heuristic that I use when looking for effects: (...)»

### Tools for Effect Reasoning (p. 165)

- private vs. protected/package/public for fields in Java/C#
- const vs. mutable in C++

### Learning from Effect Analysis (p. 167)

> (p. 168) «In general, programming gets easier as we narrow effects in a program.»

### Simplifying Effect Sketches (p. 168)

> (p. 171) «When we remove tiny pieces of duplication, we often end up getting effect sketches with a smaller set of endpoints.  This often translates into easier testing decisions.»

Chapter 12: I Need to Make Many Changes in One Area (p. 173)
---------------------------------------------------
(Do I have to break dependencies for all the classes involved?)

> (p. 173) «We can write tests at a single public method for changes in a number of privates methods (...) the structure of code below the tests can change radically as long as the tests pin down its behaviour.»

> (p. 174) «Higher-level tests can be useful in refactoring. (...) In fact, changes are often easier than you would expect because you can make changes to the tests and then make changes to the code, moving the structure along in small safe increments.»

> (p. 174) «Higher-level tests (...) shouldn't be a substitute for unit tests.»

### Interception Points (p. 174)

> (p. 174) «a point in your program where you can detect the effects of a particular change.»

> (p. 180) «A _pinch point_ is a narrowing in an **effect sketch (155)**, a place where it is possible to write tests to cover a wide set of changes.»

### Judging Design with Pinch Points (p. 182)

> (p. 183) «Using effect sketches to find hidden classes.»

> (p. 183) «Writing tests at pinch points is an ideal way to start some invasive work in part of a program. (...) After you write your **Characterization tests (186)**, you can make changes with impunity.»

### Pinch Point Traps (p. 184)

- unit tests that become integration tests

> (p. 184) «When you start to notice that your tests are too large, you should break down the class you are testing, to make smaller independent pieces that can be tested more easily.»

Chapter 13: I Need to Make a Change, but I Don't Know What Tests to Write (p. 185)
-------------------------------------------------------------------------

> (p. 185) «The way to win is to concentrate effort on not putting bugs into code in the first place.»

> (p. 185) «In the natural flow of development, tests that _specify_ become tests that _preserve_.»

> (p. 185) «(...) bolster the area we want to change with tests to provide some kind of safety net.»

### Characterization Tests (p. 186)

> (p. 186) «[Characterization Tests] document the actual current behaviour of the system (...)»

> (p. 186) «In nearly every legacy system, what the system does is more important than what it is supposed to do.»

> (p. 186) «...our goal right now is to get tests in place that help us make changes more deterministically.»

#### Algorithm
1. Use a piece of code in a test harness.
2. Write an assertion that you know will fail. (i.e. `expected == "fred"`)
3. Let the failure tell you what the [actual current] behaviour is.
4. [change the expected to match actual]
5. Repeat

> (p. 188) «...write tests until we are satisfied we understand it.»

Will the tests sense «any problems that we can cause?»

#### The Method Use Rule (p. 189)

> (p. 189) «Before you use a method in a legacy system, check to see if there are tests for it.  If there aren't, write them.»

### Characterizing Classes (p. 189)

1. «If you don't understand an area of code, consider introducing a **Sensing variable (301)** to characterize it.»
2. «...stop to make a _list of things that can go wrong_.  See if you can formulate tests that trigger them.»

> (p. 190) «Make sure you document the important things that you discover as tests.»

#### When you find bugs (p. 190)
> (p. 190) «[While characterizing legacy code] what should you do when you find a bug?  Code is new?  Fix it.  Code is deployed?  Someone could be relying on the defect.  Document it, find out.»

### Targeted Testing (p. 190)

> (p. 190) «When you write a test for a branch, ask yourself whether there is any other way that the test could pass, aside from executing that branch.  If you are not sure, use a **Sensing variable (301)** or the debugger to find out whether the test is hitting it.»

### A Heuristic for Writing Characterization Tests (p. 195)

Write enough tests to convince yourself you understand the current code under test and the changes you're about to make.

Chapter 14: Dependencies on Libraries Are Killing Me (p. 197)
----------------------------------------------------

> (p. 197) «Avoid littering direct calls to library classes in your code.  You might think that you'll never change them, but that can become a self-fulfilling prophecy.»

> (p. 197) «...sometimes the best thing you can do is write a thin wrapper over the classes that you need to separate out.»

(p. 198) prefer virtual methods, for easier testing (pretend it's non-virtual in production)

Chapter 15: My Application Is All API Calls (p. 199)
-------------------------------------------

> (p. 199) «There are many different things to consider when choosing to integrate code we can't change easily.»

(p. 200) Mailing List Server example

> (p. 203) «The first step is to identify the computational core of code.»

> (p. 205) «When we have a system that looks like it is nothing but API calls, it helps to imagine that it is just one big object and then apply the responsibility-separation heuristics in Chapter 20 [Class Is Too Big]»

#### How do we move forward? (p. 205)
1. Skin and wrap the API
2. Responsibility-based extraction

#### How do we choose between [the two]? (p. 206)
1. Skin and wrap the API
    1. API is relatively small
    2. You want to completely separate out dependencies on a third-party library
    3. You don't have tests, and you can't write them because you can't test through the API
    4. More work, but very useful to isolate from 3rd-party libraries
2. Responsibility-based extraction
    1. API is more complicated
    2. You have a tool that provides a safe extract method support, or you feel confident that you can do the extractions safely by hand

Chapter 16: I Don't Understand the Code Well Enough to Change It (p. 209)
----------------------------------------------------------------

### Notes/Sketching (p. 210)

> (p. 210) «When reading through code gets confusing, it pays to start drawing pictures and making notes.»

### Listing Markup (p. 211)

Drawing on a code printout.

#### Separating Responsibilities

#### Understanding Method Structure

#### Extract Methods

#### Understand the Effects of a change

### Scratch Refactoring (p. 212)

Mess with code to understand it, then revert changes.

### Delete Unused Code (p. 213)

Chapter 17: My Application Has No Structure (p. 215)
-------------------------------------------

> (p. 216) «The brutal truth is that architecture is too important to be left exclusively to a few people.»

### Telling the Story of the System (p. 216)

Explain architecture with few words; it tends to suggest a simpler architecture.

> (p. 217) «...it helps everyone understand what would've been ideal and what things are expediencies.»

> (p. 217) «...having a simple story of how a system works just serves as a roadmap[, a way of getting your bearing as you search for the right places to add features.]»

#### What is the architecture of JUnit?

### Naked CRC (p. 220)

Class Responsibility Collaborations

Explain something with blank cards using pointing and motion.

> (p. 223) «There are just two guidelines in Naked CRC
> 1. Cards represent instances, not classes.
> 2. Overlap cards to show a collection of them.»

### Conversation Scrutiny (p. 224)

> (p. 224) «Listen to conversations about your design.»

Chapter 18: My Test Code Is in the Way (p. 227)
--------------------------------------

### Class Naming Conventions (p. 227)

> (p. 227) «...it makes sense to make the unit test class name a variation of the class name. (...) I like the `Test` suffix convention. (...) each class lines up next to its test class.»

* fake classes «use the prefix `Fake`»
* testing subclasses use the prefix `Testing`

### Test Location (p. 228)

(p. 229) The Java example encourages the same package; we might want to override the default namespace for .NET test projects to achieve the same effect.

Chapter 19: My Project Is Not Object Oriented.  How Do I Make Safe Changes? (p. 231)
---------------------------------------------------------------------------

> (p. 231) «get a large chunk of the code under test before doing anything else and then use those tests to get some feedback while developing.»

> (p. 231) «look for a **Pinch Point (180)** and then use the **Link Seam (36)** to break dependencies well enough to get the code in a test harness.»

### An Easy Case (p. 232)

`Set-WriteTime` C code from Linux

### A Hard Case (p. 232)

`scan_packets` C code calls 3rd-party `ksr_notify()`
* **Link Seam (36)**
* use macro preprocessor

### Adding New Behavior (p. 236)

* Use **Test-Driven Development (88)**
> (p. 236) «Often the work of trying to formulate a test for each piece of code that we're thinking of writing leads us to alter its design in good ways.»

(p. 237) `send_command` vs. `form_command`
* kind of like applying **Command/Query Separation (147)**

(p. 238) Use function pointers on a struct to create an abstraction/seam

### Taking Advantage of Object Orientation (p. 239)

* **Encapsulate Global References (339)**
* **Preserve Signatures (312)**
* **Parameterize Constructor (379)**

### It's All Object Oriented (p. 242)

> (p. 244) «The old C system was, in reality, just one big object.»

Chapter 20: This Class Is Too Big and I Don't Want It to Get Any Bigger  (p. 245)
-----------------------------------------------------------------------

TL;DR: Big classes happen.  Break them up.  Why?  Single Responsibility Principle (SRP).  Otherwise: confusion, conflicts & concealment.  Starts off with SRP and an example class called `RuleParser`, which, it turns out, has 4 responsibilities.

(p. 246) **Sprout Class (63)** and **Sprout Method (59)** help prevent making it worse.

> (p. 246) «The key remedy for big classes is refactoring.»

#### Single Responsibility Principle (SRP) (p. 246)

> (p. 246) «Every class should have a single responsibility; it should have a single purpose in the system, and there should be only one reason to change it.»

#### `RuleParser` class (p. 247)

### Seeing Responsibilities (p. 249)

#### Heuristic #1: Group Methods (p. 249)
> «Look for similar method names. (...) try to find ones that seem to go together.»

#### Heuristic #2: Look at Hidden Methods (p. 250)
> «If a class has many [private and protected methods], it often indicates that there is another class dying to get out.»

> (p. 250) «...if you have the urge to test a private method, the method shouldn't be private...»

#### Heuristic #3: Look for Decisions that can change (p. 251)
> «...extract methods that reflect what you intend at a high level.»

* method grouping is probably easier

#### Heuristic #4: Look for internal relationships (p. 251)
> «Are certain instance variables used by some methods and not others?»

* Suggests clusters of methods that could be extracted.  Try _sketching_ it out.

> (p. 252) «Usually there is some sort of "lumping" in a class.»

#### Heuristic #5: Look for the primary responsibility (p. 260)

#### Interface Segregation Principle (ISP) (p. 263)

* Extract interfaces out of big classes

#### Heuristic #6: When All Else Fails, Do Some Scratch Refactoring (p. 264)

> (p. 264) «If you are having a lot of trouble seeing responsibilities in a class, do some scratch refactoring.»

#### Heuristic #7: Focus on the Current Work (p. 265)
> «Pay attention to what you have to do right now.  If you are providing a different way of doing anything, you might have identified a responsibility that you should extract and then allow substitution for.»

### Other Techniques (p. 265)

Read.  Read books, read other people's code.

### Moving Forward (p. 265)

#### Strategy (p. 266)
> (p. 266) «The best approach to breaking down big classes is to identify the responsibilities, make sure that everyone else on the team understands them, and then break down the class on as-needed basis.  When you do that, you spread out the risk of the changes and can get other work done as you go.»

#### Tactics (p. 266)
* SRP at implementation level, then SRP at interface level
* But first, tests!
    * look at fields & methods to get an idea of what tests to write
    * Chapter 9: I Can't Get This Class into a Test Harness (p. 105)
    * Chapter 10: I Can't Run This Method in a Test Harness (p. 137)

(p. 267) How to extract a class without tests

### After Extract Class (p. 268)
«In practice, the biggest danger for teams extracting classes from a big class is getting overambitious.»
