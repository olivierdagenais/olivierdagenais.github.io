Unit Testing Basics
===================

Ground rules
------------
I'm assuming object-oriented programming languages, which usually means one class per file.  If you somehow don't have classes, perhaps the way your organize your files can still inform how you organize the corresponding tests.

### Terminology

<dl>
    <dt>Class Under Test</dt>
    <dd>
        I call "class under test" (often abbreviated as <code>cut</code> in code) to mean the class that's the focus point of the tests.
    </dd>
    <dt>Test Class</dt>
    <dd>
        Correspondingly, there's the test class, a class that's created for the sole purpose of containing the [unit] tests for a given class.  Sometimes called <em>test fixture</em>.
    </dd>
    <dt>Test Method</dt>
    <dd>
        A method in a test class that sets up a given scenario, calls the method under test, and then checks that the result is as expected.  Obviously, the method under test must be visible to your test class for this to work, but there are tricks you can do to your class under test to shuffle your code around to make it more testable (see <em>Refactor</em>).
    </dd>
    <dt>Refactor</dt>
    <dd>
        «The subtle science and exact art» of modifying code <strong>without</strong> changing its behaviour, usually to make it easier to write tests but also to make it easier for humans to understand.
    </dd>
    <dt>Unit Test</dt>
    <dd>
        A test that exercises a single unit.  See the <strong>Units only!</strong> section.
    </dd>
    <dt>Integration Test</dt>
    <dd>
        A test that exercises two or more units.  Contrast with <strong>Unit test</strong>.
    </dd>
    <dt>Test Double</dt>
    <dd>
        From Martin Fowler's <a href="https://www.martinfowler.com/bliki/TestDouble.html">Test Double</a> page:
        <blockquote cite="https://www.martinfowler.com/bliki/TestDouble.html">
        Test Double is a generic term for any case where you replace a production object for testing purposes.
        </blockquote>
    </dd>
</dl>

### Conventions
As hinted by the **Terminology** section, the easiest way to match a class under test with a test class is for them to be related by name.  Generally, that's by creating a test class that starts with the same name as the CUT and then ends with `Test`.  For example, a `MavenExporter` class would have a `MavenExporterTest` class.

In Java, especially with Maven, you can have both classes be in the same package, even if they are going to be compiled separately.  In C#, a similar effect is achieved by making the members with `internal` visibility accessible to your test project via the [assembly-level `InternalsVisibleTo` attribute](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.internalsvisibletoattribute?view=netframework-4.7.2)

If you're going to need to create [test doubles]

Units only!
-----------
When we're talking about unit tests (sometimes also called Level 0 or even L0 tests), it usually implies a few restrictions:
1. A single unit is being exercised.  Generally, we mean a single method in a single class.  Other methods can be in play to help with the scenario's set-up, but those will generally be called on the CUT.  While it's possible to write tests that exercise the _interactions_ between two classes, these are generally called **integration tests**.
2. No I/O.  That means no network, no external database, no files, no directories, no sub-processes.  Again, while tests that perform I/O are possible, these are generally called **integration tests**.
3. They are small, simple and run fast.  How fast?  Execution time for each test is usually measured in milliseconds, topping out at a couple hundred milliseconds.  Slower tests are generally called **integration tests**.

We place a lot of emphasis on unit tests because they force you to improve your code to make it easier to write many tests that are both small & fast, which is infinitely better than having a few large & slow tests, because the complexity of a test (and of the method under test) is strongly correlated with the length of the test method.  And trust me, you want your tests to run FAST because then you can run them all the time and catch any errors as soon as possible, while they are easier to correct.

### Arrange, Act, Assert
Each test method should have three parts, generally separated by a blank line so it's immediately obvious to the reader where the set-up is (i.e. "arrange"), the call to the method under test (i.e. "act") and then the verification of the result against expected values (i.e. "assert").

#### Example
This is a test of the "retry" functionality added as part of [feat: retry checkout of global pipeline library #47](https://github.com/jenkinsci/workflow-cps-global-lib-plugin/pull/47).  Although there is considerable set-up, we can still see that the 3 sections are represented:

```java
@Test public void retry() throws Exception {
    final SCMSource scmSource = new FailingSCMSource();
    final SCMSourceRetriever retriever = new SCMSourceRetriever(scmSource);
    final LibraryConfiguration libraryConfiguration = new LibraryConfiguration("retry", retriever);
    final List<LibraryConfiguration> libraries = Collections.singletonList(libraryConfiguration);
    GlobalLibraries.get().setLibraries(libraries);
    final WorkflowJob p = r.jenkins.createProject(WorkflowJob.class, "p");
    final String script = "@Library('retry@master') import myecho; myecho()";
    final CpsFlowDefinition def = new CpsFlowDefinition(script, true);
    p.setDefinition(def);
    r.jenkins.setScmCheckoutRetryCount(1);

    WorkflowRun b = r.assertBuildStatus(Result.FAILURE, p.scheduleBuild2(0));

    r.assertLogContains("Failing 'checkout' on purpose!", b);
    r.assertLogContains("Retrying after 10 seconds", b);
}
```

What to test
------------

### Verification vs. validation

Verification is checking if we did things right; in other words if the functionality is free of errors.

Validation is checking if we did the right things; in other words if the functionality satisfies the needs of the users.

It's quite possible to have functionality that is implemented without errors (i.e. builds a car without defects - verification passes) but isn't what the user wanted (i.e. the user wanted a bicycle - validation fails).

In general, it will be much easier for unit tests to verify functionality rather than to validate it.  This is because of the difficulty in representing what the users want, especially at the unit test level.  If you have an incredibly detailed specification that makes this possible, great, otherwise you may have to craft acceptance tests.

Test-Driven Development
-----------------------
If you've gotten this far, you must be ready for the ultimate discipline of software development: writing the test _first_, watching it fail because the corresponding functionality hasn't been implemented yet and then implementing _just enough_ of the functionality to make the test pass.
