# Code Review Process

## Introduction

It is important to approach a code review with the right frame of mind:

* Expect to ask lots of questions, not as an interrogation, but as an ongoing conversation, taking place between DHSS and the vendor.
* This is an Agile process and, as such, we treat the output of every sprint as a completed product. Security, accessibility, UX, tests, browser compatibility, etc. are not features, to be implemented in future sprints, but are things that we expect to be incorporated constantly, and completed at the end of each sprint.
* Remember that we are all learning together here. If you see something in the code that you don’t understand, it’s incumbent on you to say so. Maybe you know something that the developer doesn’t, maybe the developer knows something that you don’t, but they only way to find out is to ask.


## Checklist

- [ ] deploy the site on your system
	- [ ] test all functionality in all major browsers, emphasizing the functionality that this pull request addresses
		- [ ] the browser to test the most thoroughly is Internet Explorer 11 on Windows 10
		- [ ] Chrome, Firefox, Safari, mobile Chrome, and mobile Safari
	- [ ] use an automated audit tool for code quality and practices (recommended: Chrome Audits)
	- [ ] review for accessibility
		- [ ] use an automated audit tool, such as Chrome Audit or 
	- [ ] navigate site only with the keyboard
	- [ ] use VoiceOver to navigate the site with audio only
	- [ ] manually test anything that pa11y cannot test automatically (e.g., contrast of text over images)
	- [ ] look at efficiency of page loads, asset sizes, HTTP connection management, etc.
- [ ] tests
	- [ ] look at code coverage of tests on VSTS
	- [ ] review all new tests for correctness, quality of naming
	- [ ] determine what code isn’t tested, review that carefully
- [ ] review static code analysis results, make sure everything is OK
- [ ] critically read all new code, in the context of existing code
	- [ ] make sure names of methods and variables are sensible
	- [ ] be suspicious of commented-out code
	- [ ] any code with a purpose that isn’t immediately clear should have a comment explaining it
	- [ ] check that code style is consistent
	- [ ] be suspicious of any code that accepts input from the outside world, ensure that it doesn’t enable any kind of buffer overflows or SQL injection attacks
- [ ] review documentation to ensure it matches changes
- [ ] comment on VSTS
	- [ ] for comments that are tied to a particular line of code, use VSTS’s line-commenting functionality
	- [ ] for comments are are more general, comment on the pull request itself
