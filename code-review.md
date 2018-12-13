# Code Review Process

## Introduction

It is important to approach a code review with the right frame of mind:

* Expect to ask lots of questions, not as an interrogation, but as an ongoing conversation, taking place between DHSS and the vendor.
* This is an Agile process and, as such, we treat the output of every sprint as a completed product. Security, accessibility, UX, tests, browser compatibility, etc. are not features, to be implemented in future sprints, but are things that we expect to be incorporated constantly, and completed at the end of each sprint.
* Remember that we are all learning together here. If you see something in the code that you don’t understand, it’s incumbent on you to say so. Maybe you know something that the developer doesn’t, maybe the developer knows something that you don’t, but they only way to find out is to ask.

## What we look for

Code reviews are about keeping code clean and limiting technical debt. We will look for things that increase technical debt or create an environment where technical debt can be introduced easily later.

### Untested code
We’re mostly going to look at new and changed code. For changed code, we’ll check the existing tests to make sure they’ve been updated if necessary. For new code, we’ll check that new tests were created.

### Does not contain secrets
We look to ensure that new and/or changed code does not contain secrets (account names, passwords, private keys, private hostnames, service endpoints and other confidential secrets).

If a confidential secret is committed and is discovered during code review, it needs to be [removed from history](https://help.github.com/articles/removing-sensitive-data-from-a-repository/). Creating a new commit that deletes the secret but leaves it discoverable in the git history is not enough.

### All logical paths are tested
Tests should cover all branches of logical decisions (e.g., if statements). We’ll check this by looking at a code coverage report that shows which lines were executed.

### Logical AND and OR operations are tested
Boolean operations can be somewhat hidden logical paths. That is, a code coverage report will show every line is tested, but if boolean parts of a condition aren’t fully exercised, then some logical paths aren’t actually tested. We’ll check the tests to make sure they check both sides of logical operations.

### Test names describe what the tests are doing
Test names shouldn’t be overly technical. Ideally folks outside the development team can read the tests and know what’s passing and what’s failing. Test names should describe their behavior and not just be the name of the method being tested. We’ll check the test names to make sure they’re descriptive.

### Tests actually do what they’re supposed to
It’s easy to get to 100% code coverage without actually testing anything. We’ll look at the tests themselves to make sure they’re actually making the right assertions about the methods under test.

### Cyclomatic complexity, code depth, and method lengths are reasonable
We’ll use automated tools to do [static source analysis](https://18f.gsa.gov/2016/10/04/what-is-static-source-analysis/). Anywhere the metrics are higher than what we’d generally like, we’ll look at the code itself to see if they make sense. We’re going to take a more in-depth look when we a cyclomatic complexity above 10, a code depth above 5, or a method length above 25 lines.

### Opportunities to abstract and refactor
We’ll look for duplication in the code where it might make sense to break functionality into methods that can be reused.

### Unwieldy methods
Methods that are hard to reason about are also difficult to test, difficult to maintain, and prone to bugs. We’ll look out for methods that are complex and suggest either refactoring that method or possibly breaking it into smaller pieces.

### Meaningful method and variable names
Method names should accurately reflect what the method does, and variable names should pretty clearly indicate what data they’re holding. Don’t be afraid of long names.  This also applies to method argument names. Ideally, someone looking at a method signature should be able to infer what it does without any additional documentation. We’ll look at these names to be sure they make sense. Good naming practices contribute to self-documenting code and reduce the manual documentation burden.

### Commented-out code
With good version control, it should be unnecessary to comment out blocks of code — just delete them and get them from source history if you really need them again in the future.  Obviously it’s fine to comment out code while you’re developing, but once a feature is ready to merge, that former code should just be removed. We’ll be looking for these commented code blocks.

### Necessary comments
Comments in the code should describe complex bits of logic that aren’t easily glanceable — if someone new to the code can’t skim it and understand it, a comment might be in order. As we’re reviewing the code, if we find a bit we can’t understand quickly from the code and context, we’ll be looking for a comment that explains it. Comments should appear with the code they’re describing.

### Documented APIs
If code exposes a public API — whether that’s public methods on a class or HTTP endpoints in a REST service — those public methods should be documented.  We like documentation that can be extracted into some pretty markup (e.g., .NET’s XML comments, jsdoc, or [OAS](https://www.openapis.org/) — formerly Swagger). We’ll check that any public-facing methods have useful documentation.

### Adherence to the project’s style guide
The project should adopt a code style guide and code should conform. Which guide the team chooses is less important than the consistency that comes from actually using it.  We’ll check to make sure there’s a linter configured to check code style, that it passes, and that any exceptions are documented and explained in the code.

## What we’ll do

### We’ll be nitpicky
Code is a UX. Its users are other developers. In the spirit of user-centered design, we’ll be interested in the experience of future developers. We’ll look at code with this question in mind: “Would I want to work on this?”

### We’ll be thorough
After the work to write the code, it deserves for us to give it proper attention. We’ll take the time to carefully look over it and give our feedback.

### We’ll ask questions
If we’re not sure about something, we’ll ask for clarity. We may ask a lot.

### We’ll be kind
We wouldn’t want anyone being mean to us because of an oversight, mistake, or just a different idea, and we’ll extend that courtesy to others. Code reviews are really conversations, not dictates. We’ll make suggestions rather than simply saying, “that’s wrong.”

## Checklist

We use this list when performing a code review to ensure that all tasks have been completed.

- [ ] review the pull request itself, to get oriented
	- [ ] read the description of the pull request, which should summarize the changes made
	- [ ] read through every task on the Scrum board that's encompassed by this pull request
	- [ ] read the description of every commit that comprises the pull request
- [ ] deploy the site on your local system
	- [ ] test all functionality in all major browsers, emphasizing the functionality that this pull request addresses
		- [ ] the browser to test the most thoroughly is Internet Explorer 11 on Windows 10
		- [ ] also test in Edge, Chrome, and Firefox
	- [ ] use an automated audit tool for code quality and practices (recommended: Chrome Audit)
		- [ ] look at efficiency of page loads, asset sizes, HTTP connection management, etc.
	- [ ] review for accessibility
		- [ ] use an automated audit tool, such as Chrome Audit or aXe
	- [ ] navigate site only with the keyboard
	- [ ] use VoiceOver or Narrator to navigate the site with audio only
	- [ ] manually test anything that pa11y cannot test automatically (e.g., contrast of text over images)
- [ ] review static code analysis results, make sure everything is OK
- [ ] critically read all new code, in the context of existing code, [looking for problems](#what-we-look-for), e.g.:
	- [ ] make sure names of methods and variables are sensible
	- [ ] make sure code does not contain secrets
	- [ ] be suspicious of commented-out code
	- [ ] any code with a purpose that isn’t immediately clear should have a comment explaining it
	- [ ] check that code style is consistent
	- [ ] be suspicious of any code that accepts input from the outside world, ensure that it doesn’t enable any kind of buffer overflows or SQL injection attacks
- [ ] tests
	- [ ] look at code coverage of tests on VSTS
	- [ ] review all new tests for correctness, quality of naming
	- [ ] determine what code isn’t tested, review that carefully
- [ ] review documentation to ensure that it matches changes
- [ ] comment on VSTS
	- [ ] for comments that are tied to a particular line of code, use VSTS’s line-commenting functionality
	- [ ] for comments are are more general, comment on the pull request itself
- [ ] open a VSTS bug report for each feature-level bug (i.e., it’s working as designed, but designed wrong), putting it in the backlog
