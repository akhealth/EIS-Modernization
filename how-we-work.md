# How We Work

## Principles

Our basic principles are those familiar to anybody who has contributed to a prominent open source project, or deployed code in a modern software environment.

* We look to the future. Our objective is that our systems are secure and open source, created and maintained in repositories where code may be inspected by like minded developers who place their trust in it, copy it for use for use by other agencies, and share discovered solutions that increase the functionality or safety of the code.
* We adhere to the basic practices of agile software development, using the Scrum development framework.
* We use a DevSecOps approach that allows us to rapidly develop and deploy improvements to our systems, infrastructure- and configuration-as-code, and CI/CD to ensure that our work is high-quality. We integrate security compliance into the process.
* We practice human-centered design. Everything that we produce is highly accessible, per WCAG 2.0. We build APIs before we build software atop it, and we believe that APIs require a well-designed interface.
* We include and enforce codes of conduct, to foster an open, collaborative, welcoming environment.
* We reduce system modifications to the smallest self-contained module, and procure each of those modifications via a unique RFP.
* Finally, we believe in having the relevant decision-makers at the table during all meetings, to maximize efficiency and maintain momentum.

## Product Team

There is a cross functional product team for the Alaska DOH modernization project (ARIES) comprised of business, policy, security, procurement and technical specialists who are working together to move the entire enterprise forward towards its goals. In addition to this high level team, each of our procurements will be managed by a more immediate set of people who will be working with the product owner and product managers on the Alaska DOH product team to deliver on the prioritized backlog for that particular procurement. This product team will be comprised of the following roles

* Product owner - Alaska
* Product manager(s) - Alaska
* User Experience designer - Vendor
* Visual designer - Vendor
* Researcher - Vendor
* Developers (Front-end, Back-end, Full-stack) - Vendor
* Technical lead - Vendor
* Scrum Master (or equivalent) - Vendor

This team will participate in all scrum ceremonies in service of prioritizing, defining and delivering value to the department and the public it serves.

## Meetings

There are two basic meeting rhythms: daily standups and agile sprint rituals. The sprint duration will be determined by the development team's leadership in consideration of the work to be done, and the resources available. The duration of a sprint is typically two weeks, resulting in semi-weekly agile sprint rituals.

We hold regular, tight 15-minute standups, at a frequency decided by the team.

As each sprint ritual begins, we conduct backlog grooming (prioritizing work in the backlog) and sprint planning (define the work to be done over the next sprint). Each sprint ends with a sprint review (demonstrate work done, and accept or reject that work) and a sprint retro. In the sprint retro, we review how the sprint went as far as people, relationships, processes and tools, identifying what went well and ways that we can improve quality and effectiveness. These are all held back-to-back, on the same day.

All meetings are held via video teleconference. A telephone bridge is maintained as a backup method of connecting, but participants are encouraged strongly to join via desktop webcam.

## Design Research

We recognize that the DPA field staff will be critical to helping us develop solutions that will deliver better service to Alaskans. In order to create an open and collaborative space for DPA staff to contribute, we will protect their privacy through the following:

* Interview notes will be anonymized. The keeper of the key to participants is the state project UI/UX coordinator. (Joan Smith = Participant 1).
* The full product team needs to understand the expectation for privacy around research materials.
* Anonymized raw notes will be available to the small product team doing the work, but not beyond.
* Synthesized notes and conclusions (still anonymous) can be shared publicly, including on Azure DevOps/GitHub as they are fully decontextualized.
* Non-researchers on the product team can and should be involved with research.
* Only research facilitators/observers can be included in synthesis.
* We will inform research participants of these matters at the beginning of research sessions and ask for their consent. See [Research Participant Agreement](https://github.com/AlaskaDHSS/EIS-Modernization/blob/master/assets/20220627Design_Research_Participant_Agreement_ARIES.pdf). 
* An overview of our approach to user research, driven by usability testing, is [here](UsabilityResearch.md)

## Definition of Done

So that we can work more efficiently and be confident in the quality of the work we are delivering, we have a clear definition of what it means for a user story to be done, or production-ready.

* for delivering a user story to the product team
  * Story needs to be written in a way that is clear from both a development and a testing standpoint. Stories will need to be reviewed     by the product team during creation. (this can be a subset of the whole product team)
  * Acceptance criteria should include the relevant tests needed (unit, security, performance, acceptance, etc)
  * Acceptance criteria should include the objective of the story, for use in approval by PO or tech team or both
  * The delivered functionality should match the acceptance criteria of the user story
  * All tests must pass in the staging environment (unit, integration, feature)
  * Test coverage must be greater than the percentage described in the Quality Assurance Plan
  * The delivered functionality should be 508 compliant
  * Security requirements must be met
  * All documentation must be up to date (diagrams, training documentation, API documentation, help text, etc)
  * The delivered functionality should be compatible with the latest versions of Edge, Firefox, Chrome and Safari

* for product team to accept the user story and ship it
  * The product team has verified the functionality in staging

## Accepting Vendor Work

Acceptance of work happens through the sprint as work is completed. The procedure is as follows:

1. Development team completes work - See "for for delivering a user story to the product team" in [Definition of Done](#definition-of-done) above
2. Development team creates pull request to staging - See [Pull Request Process](/azure-devops/GitBranchingStrategy.md)
3. The product team has verified the functionality against acceptance criteria in a deployed instance for a feature level pull request
4. Code review takes place - See [Code Review Process](code-review.md)
5. Pull request merged to staging DOH product team to accept the user story and ship it" in _Definition of Done_ above, and [Testing Strategy](#testing-strategy)
7. Product team creates pull request to master
8. DOH product owner and network services deployment team merges pull request to master

## Processes

### Tech Strategy
We will move the programs currently in EIS off the mainframe within 5 years. This is a goal of the EIS modernization project. Strategies have been organized in themes. For more details about how we will do this work, see [EIS Replacement Project Technical Strategy](/tech-strategy.md).


### Testing Strategy

We practice testing at three levels: unit tests, integration tests, and feature tests. 

* **Unit** - Unit tests must be created for all new code, during the sprint in which the code is written, with coverage of at least 90%.

* **Integration** - Because all new work is integrating with the existing ARIES code base, new code must include tests that verify that interfaces are functioning as designed.

* **Feature** - New features must have functional definitions of the thing that they are to perform, and a description of human-performable actions to verify that they perform that thing.

For more information about how to create and maintain unit, integration and feature tests, see [18F’s “Automated Testing Playbook”](https://automated-testing-playbook.18f.gov/).

### Pull Request Process
Documented in our [Git Branching Strategy](/azure-devops/GitBranchingStrategy.md).

### Code Review Process

Documented in our [Code Review Process](code-review.md).

### DevSecOps

We rely on [DevSecOps](DevSecOps.md) for automation and monitoring of code integration, testing, and deployment. Our DevSecOps pipeline is built atop Azure DevOps (not GitHub) for deployment to Azure. We practice continuous integration, continuous deployment, and continuous testing (including security testing). All new code has tests developed simultaneously, with cumulative test coverage of not less than 90%. See “Accepting Vendor Work” for more.
For details, see our [“Why DevSecOps?” document](https://github.com/AlaskaDHSS/DevSecOpsMvp/blob/master/DevSecOps.md), in Github.

## Tools

* **GitHub** - We use our [GitHub organization](https://github.com/AlaskaDHSS) for storing both software and collaboratively-maintained text.

* **Azure DevOps** - We use our [Azure DevOps](https://alaskadhss.visualstudio.com/) repository much like our GitHub repository, but for repositories that either need to be kept private and for repositories that are deployed to Azure.

* **Microsoft Teams** - We use [Microsoft Teams](https://teams.microsoft.com/l/team/19%3a3ac701697e2f4d279a28c0e33b00a092%40thread.skype/conversations?groupId=6bf46ba5-dd04-4ed8-b1c2-c9152ecddecd&tenantId=20030bf6-7ad9-42f7-9273-59ea83fcfa38) for communication that falls outside of the structure of Azure DevOps or GitHub, but that doesn’t rise to the level of email, or for communication that it’s helpful for everybody else to be able to observe.
