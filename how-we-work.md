# How We Work

## Principles

Our basic principles are those familiar to anybody who has contributed to a prominent open source project, or deployed code in a modern software environment.

* We produce open source software, created and maintained in repositories where it may be inspected by the public who places their trust in it and copied for use by other agencies.
* We adhere to the basic practices of agile software development, using the Scrum development framework.
* We use DevSecOps to automate and measure our deployment process, relying on continuous integration, continuous delivery, and continuous security to ensure that our work is high-quality. 
* We practice human-centered design. Everything that we produce is highly accessible, per WCAG 2.0. We build APIs before we build software atop it, and we believe that APIs require a well-designed interface. 
* We include and enforce codes of conduct, to foster an open, collaborative, welcoming environment. 
* We reduce system modifications to the smallest self-contained module, and procure each of those modifications via a unique RFP.
* Finally, we believe in having the relevant decision-makers at the table during all meetings, to maximize efficiency and maintain momentum.

## Product Team

There is a cross functional product team for the Alaska DHSS modernization project (ARIES) comprised of business, policy, security, procurement and technical specialists who are working together to move the entire enterprise forward towards its goals. In addition to this high level team, each of our procurements will be managed by a more immediate set of people who will be working with the product owner and product managers on the Alaska DHSS product team to deliver on the prioritized backlog for that particular procurement. This product team will be comprised of the following roles

* Product owner - Alaska
* Product manager(s) - Alaska
* User Experience designer - Vendor
* Visual designer - Vendor
* Researcher - Vendor
* Developers (Front-end, Back-end, Full-stack) - Vendor
* Technical lead - Vendor

This team will participate in all scrum ceremonies in service of prioritizing, defining and delivering value to the department and the public it serves.

## Meetings

There are two basic meeting rhythms: daily standups and semi-weekly agile sprint rituals.

Every day, at 9 AM AKT, we hold a tight 15-minute standup.

Every two weeks we hold sprint rituals. Each two-week sprint begins with backlog grooming (prioritizing work in the backlog) and sprint planning (define the work to be done over the next two weeks). Each sprint ends with a sprint review (demonstrate work done, and accept or reject that work) and a sprint retro (review the process of how people performed in this sprint). These are all held back-to-back, on the same day.

All meetings are held via video teleconference. A telephone bridge is maintained as a backup method of connecting, but participants are encouraged strongly to join via desktop webcam.

## Definition of Done

So that we can work more efficiently and be confident in the quality of the work we are delivering, we have a clear definition of what it means for a user story to be done, or production-ready. 

* for delivering a user story to the product team
  * The delivered functionality should match the acceptance criteria of the user story
  * All tests must pass in the staging environment (unit, integration, feature)
  * Test coverage must be greater than the percentage described in the Quality Assurance Plan
  * The delivered functionality should be 508 compliant
  * Security requirements must be met 
  * All documentation must be up to date (diagrams, training documentation, API documentation, help text, etc)
  * The delivered functionality should be compatible with the latest versions of IE, Firefox, Chrome and Safari 

* for product team to accept the user story and ship it
  * Someone from the product team has verified the functionality in staging
  * At least xx real users have tested the feature and no show stopper bugs have been found [Assume that this maps to a light QA process, not to an existing, more involved UAT process]

## Accepting Vendor Work

Work is accepted in the form of a pull request, at the conclusion of each sprint, after the sprint review and retro. For that work to be accepted, it must meet the following standards.

## Testing Strategy

We practice testing at three levels: unit tests, integration tests, and feature tests. For details about how we create and maintain unit, integration and feature tests, see [18F’s “Automated Testing Playbook”](https://automated-testing-playbook.18f.gov/).

### Unit

Unit tests must be created for all new code, during the sprint in which the code is written, with coverage of at least 90%.

### Integration

Because all new work is integrating with the existing ARIES code base, new code must include tests that verify that interfaces are functioning as designed.

### Feature

New features must have functional definitions of the thing that they are to perform, and a description of human-performable actions to verify that they perform that thing.

## Pull Request Process

Documented in our [DevSecOpsMVP repo](https://github.com/AlaskaDHSS/DevSecOpsMvp/blob/master/vsts/GitBranchingStrategy.md).

## Code Review Process

Code reviews are about keeping code clean and limiting technical debt. We will look for things that increase technical debt or create an environment where technical debt can be introduced easily later.

### What we look for

#### Untested code
We’re mostly going to look at new and changed code. For changed code, we’ll check the existing tests to make sure they’ve been updated if necessary. For new code, we’ll check that new tests were created.

#### All logical paths are tested
Tests should cover all branches of logical decisions (e.g., if statements). We’ll check this by looking at a code coverage report that shows which lines were executed.

#### Logical AND and OR operations are tested
Boolean operations can be somewhat hidden logical paths. That is, a code coverage report will show every line is tested, but if boolean parts of a condition aren’t fully exercised, then some logical paths aren’t actually tested. We’ll check the tests to make sure they check both sides of logical operations.

#### Test names describe what the tests are doing
Test names shouldn’t be overly technical. Ideally folks outside the development team can read the tests and know what’s passing and what’s failing. Test names should describe their behavior and not just be the name of the method being tested. We’ll check the test names to make sure they’re descriptive.

#### Tests actually do what they’re supposed to
It’s easy to get to 100% code coverage without actually testing anything. We’ll look at the tests themselves to make sure they’re actually making the right assertions about the methods under test.

#### Cyclomatic complexity, code depth, and method lengths are reasonable
We’ll use automated tools to do [static source analysis](https://18f.gsa.gov/2016/10/04/what-is-static-source-analysis/). Anywhere the metrics are higher than what we’d generally like, we’ll look at the code itself to see if they make sense. We’re going to take a more in-depth look when we a cyclomatic complexity above 10, a code depth above 5, or a method length above 25 lines.

#### Opportunities to abstract and refactor
We’ll look for duplication in the code where it might make sense to break functionality into methods that can be reused.

#### Unwieldy methods
Methods that are hard to reason about are also difficult to test, difficult to maintain, and prone to bugs. We’ll look out for methods that are complex and suggest either refactoring that method or possibly breaking it into smaller pieces.

#### Meaningful method and variable names
Method names should accurately reflect what the method does, and variable names should pretty clearly indicate what data they’re holding. Don’t be afraid of long names.  This also applies to method argument names. Ideally, someone looking at a method signature should be able to infer what it does without any additional documentation. We’ll look at these names to be sure they make sense. Good naming practices contribute to self-documenting code and reduce the manual documentation burden.

#### Commented-out code
With good version control, it should be unnecessary to comment out blocks of code — just delete them and get them from source history if you really need them again in the future.  Obviously it’s fine to comment out code while you’re developing, but once a feature is ready to merge, that former code should just be removed. We’ll be looking for these commented code blocks.

#### Necessary comments
Comments in the code should describe complex bits of logic that aren’t easily glanceable — if someone new to the code can’t skim it and understand it, a comment might be in order. As we’re reviewing the code, if we find a bit we can’t understand quickly from the code and context, we’ll be looking for a comment that explains it. Comments should appear with the code they’re describing.

#### Documented APIs
If code exposes a public API — whether that’s public methods on a class or HTTP endpoints in a REST service — those public methods should be documented.  We like documentation that can be extracted into some pretty markup (e.g., .NET’s XML comments, jsdoc, or [OAS](https://www.openapis.org/) — formerly Swagger). We’ll check that any public-facing methods have useful documentation. 

#### Adherence to the project’s style guide
The project should adopt a code style guide and code should conform. Which guide the team chooses is less important than the consistency that comes from actually using it.  We’ll check to make sure there’s a linter configured to check code style, that it passes, and that any exceptions are documented and explained in the code.

### What we’ll do

#### We’ll be nitpicky
Code is a UX. Its users are other developers. In the spirit of user-centered design, we’ll be interested in the experience of future developers. We’ll look at code with this question in mind: “Would I want to work on this?”

#### We’ll be thorough
After the work to write the code, it deserves for us to give it proper attention. We’ll take the time to carefully look over it and give our feedback.

#### We’ll ask questions
If we’re not sure about something, we’ll ask for clarity. We may ask a lot.

#### We’ll be kind
We wouldn’t want anyone being mean to us because of an oversight, mistake, or just a different idea, and we’ll extend that courtesy to others. Code reviews are really conversations, not dictates. We’ll make suggestions rather than simply saying, “that’s wrong.”

## Tools

#### Trello
We use [Trello](https://trello.com/b/siAFtoWJ/alaska-medicaid-eligibility-information-system-replacement-eis-r-project) as our Scrum board.

#### GitHub
We use our [GitHub organization](https://github.com/dhssalaska) for storing both software and collaboratively-maintained text.

#### Visual Studio Team Services
We use our [Visual Studio Team Services](https://alaskadhssba.visualstudio.com/) repository much like our GitHub repository, but for repositories that either need to be kept private and for repositories that are deployed to Azure.

#### Slack
We use the [TTS Slack](https://gsa-tts.slack.com/) for communication that falls outside of the structure of Trello or GitHub, but that doesn’t rise to the level of email, or for communication that it’s helpful for everybody else to be able to observe.

## Processes

#### DevSecOps
We rely on [DevSecOps](https://github.com/dhssalaska/acq-alaska-dhss-modernization/blob/master/DevSecOps.md) for automation and monitoring of code integration, testing, and deployment. Our DevSecOps pipeline is built atop VSTS (not GitHub) for deployment to Azure. We practice continuous integration, continuous deployment, and continuous testing (including security testing). All new code has tests developed simultaneously, with cumulative test coverage of not less than 90%. See “Accepting Vendor Work” for more.
For details, see our [“Why DevSecOps?” document](https://github.com/dhssalaska/DevSecOpsMvp/blob/master/DevSecOps.md), in Github.
