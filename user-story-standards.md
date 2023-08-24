# EIS-M Project User Story Standards 

The goal of this document is to establish user story minimum acceptable standards that define a common set of core documentation standards that can be used consistently across multiple product teams when developing features for an integrated eligibility system.

Defining minimum acceptable documentation standards enables product teams to communicate and document epics, features and user stories in a manner that is consistent across teams but flexible and efficient, to support rapid development and deployments.

Our consistency in approach will assist us with our primary objective to add value to the user in each Sprint. The prioritization of the user stories will be crucial as we discover user needs with each code delivery.

## Product Teams

Each team is a cross functional group of members comprised of business, policy, security, procurement and technical specialists tasked with implementing features to support goals and/or outcomes identified by the primary product team in accordance to its vision.  

## DOH Vision Statement

Alaska Department of Health (DOH) is developing a modern, integrated eligibility system that enables staff to more efficiently issue correct and timely benefits to Alaskans who need help meeting their basic needs.  Using agile development and modular procurements, DOH has the goal of implementing an eligibility system that not only meets state and federal standards, but is user friendly for our clients, our eligibility staff, and our technical staff.

Implementing our project’s vision can be decomposed into 4 work levels for execution:  Goal/Outcome -> Epics -> Features -> User Stories

![Worklevels](https://github.com/AlaskaDHSS/EIS-Modernization/blob/master/assets/worklevels.png)

Product Teams will be responsible for developing the Features and User Stories needed to address the Goal/Outcome assigned.
These elements will combine in an iterative process that will better meet our changing landscape of regulatory requirements and technical specifications. 

---
## Epic

An epic captures a large body of work. It is essentially a large user story that can be broken down in a number of smaller Features. 

## Feature

A feature is a tangible expression of functionality. It can take several sprints to complete a Feature. Features will be expressed as User Stories, which will contain tasks toward completing the story in Azure DevOps. The tasks themselves might be stories that are children of the parent Story. Each task corresponding to a Feature’s User Story will contribute to the fulfillment of that User Story.

Examples of Features for Unified Search:

* Find a Person’s program information using Last Name, First Name
* Find a Person’s information using SSN
* Find a Person’s information using Name 

## User Story

A user story describes a specific need, “who” the user is, “what” the user needs and “why” it is required in simple, concise terms.
User stories should be small enough to be independently executable.

### Key Characteristics of Stories:
* Contain high-level descriptions of desired functionality/goals
* Are “contracts for conversation”, no all-inclusive requirements
* Pulled into the Sprint Backlog from the Product Backlog
* Contain Acceptance Criteria to define “Done”
* Are vertical slices of the system’s functionality

### Field Validation

For any story in which field validation is necessary, the field validation must be documented in the story included in the acceptance criteria. The story itself may accomplish field validation, such as #578.

### Format

Stories should to be written in Gherkin following a basic template, and in a simplistic manner that identifies the need while providing context. 

Gherkin is a business readable and domain specific language that lets you describe software’s behavior without detailing how that behavior is implemented. The language serves two purposes – documentation and automated tests.  Its focus is the specific need, the “what” and “why” that is required, not the “how”.  In using this method, we allow for the possibility of creative, agile solutions. 

## Story Template Elements: Title, Description, Scenarios, Steps

### Title

The title consists of a one line, short descriptive text that should describe an activity.

### Description

The description illustrates the motivation behind the story. This illustration will illuminate what exactly the requirement is, as well as providing    guidance to the developers. The Description should be written in the following format:  
    * ‘As a’… <- Identifies Who? The End User, User Role or Persona
    * ‘I want to’… <- Identifies the What? The desired function
    * ‘So that’ or ‘Because’… <- Identifies the Why? The end result

### Scenarios

A scenario is a concrete example that illustrates a business rule or capability being achieved by that story.  Scenarios are used to test the intended functionality, serving as the basis for the acceptance criteria. 

Note: Stories often require more than one scenario that will illustrate completion of the story. 

Examples of Unified Search Scenarios:

One Scenario:
* A user navigates to the search page, enters a Social Security number, and returns an ARIES Client ID, and the SSN.

Multiple Scenarios:
* Search subject has one or more registered application numbers in ARIES which can be viewed on the person details page in descending Application received date order.
* Search subject does not have a registered application number in ARIES which can be viewed on the person details page.

### Steps

Each Scenario should contain the following elements, which can then be translated into steps for test cases:
#### Given

‘Given’ steps are used to describe the initial context of the system.  Also called “pre-conditions”, it sets the scene of the scenario. It is always something that has happened in the past.

#### When
‘When’ steps are used to describe an event, or an action. This can be a person interacting with the system, or it can be an event triggered by another system.

#### Then 

‘Then’ steps are used to describe an expected outcome, or result.
In the event there are multiple ‘Given’, ‘When’ and/or ‘Then’ steps, ‘And’ or ‘But’ can be used.

* Note: An ‘Or’ should not be documented within a scenario. ‘Or’ statement should be broken out into independent scenarios or if the behavior warrants, its own User Story or Feature. 

### Example 1:
Story Title:   Display “Category” only for APA, and Medicaid

Description: As a user, I want to understand the data labels in my search results.

Scenarios: 
1. Search subject is associated with a Medicaid case in ARIES, and the "Category" is visible in Person Details.
2. Search subject is associated with an APA case in EIS and the "Category" is visible in Person Details.
3. Search subject is associated with a Medicaid case in EIS, and the "Category" is visible in Person Details.
4. Search subject is associated with an ATAP case in EIS, and the "Category" label is not visible in Person Details.
5. Search subject is associated with a Food Stamps case in EIS, and the "Category" label is not visible in Person Details.

#### Steps:
Scenario 1: Search subject is associated with a Medicaid case in ARIES, and the "Category" is visible in Person Details.

Given I'm a user
-And I am viewing a person detail page
-And the search subject is associated with an ARIES case
-When ARIES case information is displayed
-Then I will see the "Category" for the ARIES case that the person is involved with.

Scenario 2: Search subject is associated with an APA case in EIS and the "Category" is visible in Person Details.

Given I'm a user
-And I am viewing a person detail page
-And the search subject is associated with an EIS case
-And that EIS case type is Adult Public Assistance
-When EIS case information is displayed
-Then I will see the "Category" for the EIS case that the person is involved with

Scenario 3: Search subject is associated with a Medicaid case in EIS, and the "Category" is visible in Person Details.

Given I'm a user
-And I am viewing a person detail page
-And the search subject is associated with an EIS case
-And that EIS case type is Medicaid
-When EIS case information is displayed
-Then I will see the "Category" for the EIS case that the person is involved with.

Scenario 4: Search subject is associated with an ATAP case in EIS, and the "Category" label is not visible in Person Details.

Given I'm a user
-And I am viewing a person detail page
-And the search subject is associated with an EIS case
-And that EIS case type is ATAP 
-When EIS case information is displayed
-Then I will NOT see a "Category" label for the EIS case that the person is involved with.

5. Search subject is associated with a Food Stamps case in EIS, and the "Category" label is not visible in Person Details.

Given I'm a user
-And I am viewing a person detail page
-And the search subject is associated with an EIS case
-And that EIS case type is Food Stamps (SNAP)
-When EIS case information is displayed
-Then I will NOT see a "Category" label for the EIS case that the person is involved with.

### Example 2

Story Title: User Search Returns No Result

Description: As a user, I want to know that that a person is not found in either system so that I can open a new case.

Scenario: A user navigates to the search page, enters search criteria, and returns "not found".

#### Steps
Given I'm a user
-And I have navigated to the Search page
-And I can see a way to enter search criteria
-And I can see a method to submit the information
When I enter search criteria
Then I see a message indicating that the client is not found

### Example 3

Story Title: Find Application Source in ARIES

Description: As a user, I need to see the source of an application in ARIES so that I can determine how to disposition the application.

Scenario:  Search subject is associated with an Application in ARIES, and the source of the application can be viewed in the Person Details page.

#### Steps
Given I'm a user
  -And I am viewing a person detail page
  -And that person is associated with an Application
When ARIES Application information is displayed
Then I will see the see the source of the application

#### Sizing
Each user’s story will be ‘sized’ so that the estimation of the feature or epic can be as accurate as possible for completion of the work. Methods of sizing will be chosen at the beginning of an increment, or contract.

#### Priority
Along with the size estimation, the priority of the story will help determine the direction of the work. Each story should be assigned a priority relative to the body of work, epic or feature, to be completed.


## Acceptance Criteria

Acceptance criteria for each User story is comprised of the elements in each scenario. Acceptance Criteria for Features consists of the acceptance of all of the associated User Stories. 

### Example:

Story Title: Find a name using SSN

Description: As a user, I want to find the name of a person using a Social Security Number so that I can update it.

Scenario: A user can enter a Social Security Number, and return one name along with the SSN 

Steps: 
Given I am logged in as a user
When I navigate to the search page
Then I see a search page
-And I see a search field to enter Social Security Number
-And I see a method to submit the data
When I enter a SSN
Then I see a First and Last Name
-And I see the SSN

#### Acceptance Criteria:
-There is a search page
-There is a method to enter SSN
-There is a method to submit a search
-A First and Last name is returned when a SSN is submitted 
