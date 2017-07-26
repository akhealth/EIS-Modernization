[DRAFT] STATEMENT OF WORK (SOW) FOR ALASKA DHSS SEARCH TOOL
=========================================

#### June 6, 2017

### 1.0 BACKGROUND
The background for this project as a whole is detailed in the project [README](/README.md). 
In short, for this first acquisition, we want to focus on something that is relatively 
straightforward, while still providing value to our beneficiaries and constituents. 
The product team has decided that building a robust person search would create a positive
impact in a way that introduces the least risk to existing systems. We will learn a lot
during this first acquisition that will help us tackle more invasive and risky acquisitions
later on.

### 2.0 OBJECTIVES

Alaska DHSS goals for the person search are as follows:

-   Decreased burden on DPA field staff as they process incoming applications for program benefits

-   Get a better sense of the nature of pending work by revealing all unworked applications for a given person or household

-   Increase the number of applications processed per worker, per day, so that potential beneficiaries can get their benefits sooner

-   Decrease time necessary for DPA field staff to get critical information on outstanding applications or ongoing assistance cases

-   Build the foundation for a performant and flexible search API that can be reused throughout the application for any view


### 3.0 SCOPE

The scope of this contract is for the Contractor to continuously deliver iterations of a search tool that finds information for a given person across multiple systems (EIS, ARIES) and returns search results to workers that accurately reflect the status of all program applications for a given person or household. The search tool will be used in production so that workers can give feedback as early and frequently as possible. At the end of the engagement, the search tool will already be in use by DPA workers.

The State of Alaska will provide documentation on how to access data sources, how to interact with existing authentication systems, and how to continuously deploy work to a staging environment.


### 4.0 REQUIREMENTS

The Contractor shall provide the following services:

-   Contractor shall review existing research artifacts and conduct additional user research 
    in order to determine user needs so that interfaces/data views that are most useful can be provided.
     
-   Contractor shall conduct usability testing and gather feedback from DPA workers on an ongoing basis as solutions are explored and software is delivered, and incorporate feedback.
    
-   Contractor shall ensure that DPA field staff can search for needed information
    using a variety of search inputs, individually and in combination.

-   Contractor shall ensure that DPA field staff can get a comprehensive view 
    across systems (EIS, ARIES) of relevant and useful data in a single search result.

-   Contractor shall provide DPA field staff with the ability to refine 
    search results by filtering.

-   Contractor shall ensure that the search results help DPA field staff reliably 
    identify potential unworked applications for the same family or individual.

-   Contractor shall ensure that DPA field staff can easily get to the search tool 
    from within the existing ARIES system, and get to where they need to go 
    from search result using Single Sign On (SSO) or current authentication scheme.

-   Contractor shall continuously deliver working software for use in the Alaska 
    production environment.


### Additional requirements:

-   Contractor shall use proven open source libraries that are well supported and 
    documented so that future vendors can contribute more easily. Before any libraries
    are chosen, we will evaluate them to determine if they meet these conditions.
    
-   Contractor shall abide by best practices around unit and integration testing 
    for both front-end and back-end components.
    
-   Contractor shall ensure the design aligns with the [modular product design strategy](/modular-experience.md) 
    from the beginning so that future vendors can integrate more easily 
    with the overall experience.
    
-   Contractor shall ensure pages load efficiently across geographies and display/function properly on different device types and using various modern and necessary browsers.

-   All software code delivered under this order shall comply with the
    [18F open source policy](https:/github.com/18F/open-source-policy/) in 
    effect as of the date of award.

-   All software code delivered under this order shall comply with the
    [18F accessibility guidelines](https://pages.18f.gov/accessibility/)
    in effect as of the date of award.
    
-   APIs should comply with the [18F API standards](https://github.com/18F/api-standards)

-   Work will be conducted in two-week sprints and reviewed at the end of each sprint for acceptability before moving on.
    
-   Contractor shall ensure that system documentation is as automated as possible so 
    that it does not have to be updated manually
    
-   Contractor shall work with the State of Alaska to ensure that support and operations
    teams are trained

### Note the following tasks are not required:

Vendor will not be required to handle any of the following tasks:

-   Provide or configure hosting of the data or the site

-   Directly create, update, or delete the data


### 5.0 OPERATIONAL REQUIREMENTS

#### 5.1 Project Management

The contractor shall provide a Project Manager point of contact for
the Alaska product team for problem resolution, Program
Management reporting in accordance with Program Management
methodologies, and staffing requirements. Sprint plans will be
developed collaboratively with the Product Owner and 18F.

#### 5.2 Impact Reports

The contractor shall be responsible for providing notification to the
Alaska product team when there are activities or issues
outside of the contractor’s control, which directly impact the
contractor’s performance. This notification shall be provided in
writing or via email within 24 hours of the anticipated or known
impact.

#### 5.3 Status Reports

In lieu of a typical status report, the following are required to
document progress over the course of the period of performance for
each sprint:

-   Links to relevant Github branches, pull requests, and/or commits

-   Screenshots of any available visualization (as appropriate)

-   Screenshot, links, or other documentation from the contractor’s
    project management system reflecting completed features, including
    number and percentage of completed sprint tasks (e.g. percentage of
    tasks completed)

-   Access to the contractor’s project management tool to view
    development status

#### 5.4 Daily Operations

Daily operations will be managed by the contractor’s project manager,
but coordinated to and communicated with the Alaska product team. They
may include:

-   Daily standup via video

-   Chat operations via Slack

-   Manage and update user stories + workflow tasks in shared project
    management platform


#### 5.5 Transition

##### 5.5.1 Transition Plan [TO BE UPDATED ONCE PM REQUIREMENTS ARE SET]

The Contractor shall:

a)  Ensure and agree that all deliverables, products, licenses, designs,
    data, documentation, tests, user research notes, source code,
    configuration settings and files, and materials developed throughout
    this contract will be the property of the State of Alaska and in
    the public domain.

b)  Two weeks prior to contract conclusion, provide a brief Transition
    Plan for all deliverables, products, and materials in coordination
    with the COR, Alaska Product Manager and Product Owner from Alaska.

c)  Coordinate with the COR and potentially another vendor, and
    implement the Transition Plan according to the COR’s direction.
    
##### 5.5.2 Transition Activities [TO BE UPDATED ONCE PM REQUIREMENTS ARE SET]

During the transition to the State of Alaska and/or a new contractor, the
Contractor shall perform all necessary transition activities,
including, but not limited to, continued full services to 18F and
other customers; participation, at discretion of COR, meetings with
the State of Alaska or new contractor to effect a smooth transition and
provide detailed information on the operation of all deliverables;
training of new personnel (contractor or State) during transition
period, appropriate close-out of outstanding technical and related
work.

Final report shall include list of sprint tasks completed,
documentation, and link to code repository. Should
the Contractor be terminated prior to the end of the period of
performance, the Contractor shall transfer all project materials to
the COR within two weeks of the COR’s request.

#### 5.6 Deliverables

##### Table 1 List of Deliverables
**Deliverable** | **Due Date** | **Description**
--- | --- | ---
Code & Status Reports | 1 business day after each sprint | Demonstration of progress throughout each sprint.
Code Repository of Product | End of call order | Version-controlled Open Source repository of code that comprises prototype.
Research | A research plan shall be delivered during the first sprint. Research-related records shall be delivered at the end of the second sprint and every applicable sprint. thereafter | A summary of research conducted and results found. If applicable, next steps or recommendations based on research.
Design Deliverables | End of every applicable sprint | Mock ups and/or design files if applicable, or design changes reflected in the Development Prototype.
Development View | End of second sprint and every sprint thereafter | In-progress development view, accessible on the web via staging server / development server.
Transition Plan | To be worked on no later than the second to last sprint of the initial Period of Performance | Work with the Alaska product team to make sure there is a clear plan for handing off the code repository.

The contractor shall submit all deliverables to the Alaska product team.

##### 5.6.1 Delivery Instructions [Defer to Nick/Simon]

Code deliverables shall be submitted via the Github repository. A copy
of any document deliverables shall be submitted to the Alaska product team.

##### 5.6.2 Inspection and Acceptance of Services [Defer to Nick/Simon]

All periodic reports and task deliverables shall be inspected, tested
(where applicable), reviewed, and accepted by the Alaska product team within 5
days of the conclusion of each sprint.

Only the Alaska product team has the authority to
inspect, accept, or reject all deliverables. 

Acceptance of services and deliverables will be based on the criteria laid out in the quality acceptance plan.
##### 5.6.3 System Documentation

The Contractor shall consult with the Alaska product team to determine what is
appropriate, effective, and essential for system documentation. The
State requires, at a minimum, that the contractor will generate
comprehensive and complete documentation, both within the code itself,
within the source code version control system (e.g., through proper
use of descriptive commit messages, issue tracking, pull requests,
etc.), and as appropriate, in separate documentation, provide
artifacts, and create new user stories based on each sprint.

##### 5.6.4. Quality Assurance

The Contractor shall comply with the acceptable quality levels (AQL) in the attached quality assurance plan (QAP) (update link to QAP on Github)

#### 5.7 Personnel

- Project manager
- Technical lead
- Developers (Front-end, Back-end or full stack)
- Researcher
- User experience designer
- Visual designer

##### 5.7.1. Desired Skills and Knowledge

The Contractor shall have knowledge and skills in the following areas

Microsoft Technology:
- ASP.NET web applications
- .NET Core framework
- C# language
- SQL Server

General Technology:
- HTML, CSS
- Javascript
- Responsive design
- SQL (language)
- Git
- Service-based architecture
- API creation and usage
- Automated unit and integration testing

##### 5.7.2 Key Personnel

The following requirements related to personnel must be met:

a)  The Contractor shall assign to perform this contract those persons
    whose résumés are submitted with its quotation and who are
    identified in the Contractor’s quotation as Key Personnel.

b)  At a minimum, a Project Manager and a Technical Lead must be
    identified and designated as Key Personnel.
    
*The Project Manager* will be a direct liaison to the Alaska product team. The Project Manager is responsible for the supervision and management of the Contractor’s personnel, technical assistance, and interface. Desired
skills/experience for the Project Manager include:
    
    -   Experience in technical leadership.
    
    -   Ability to rapidly prioritize competing requirements.
    
    -   Ability to understand and simplify customer requirements.
    
    -   Ability to communicate end user feedback to technical and 
        design leads.
        
    -   Strong communication skills.
    
    -   Proven knowledge of industry standards.
    
The *Technical Lead* must have a full understanding of the technical
approach discussed in the interview and is responsible for ensuring that 
the contractor follows the proposed approach.

#### 5.8 Additional Considerations 

##### 5.8.1 Potential Organizational Conflicts (ALASKA HAS SIMILAR CLAUSE)

[Add Alaska language]

#### 5.9 OTHER REQUIREMENTS

##### 5.9.1 Type of Contract

This is a Labor Hour Contract not to exceed budget ceiling.

##### 5.9.2 Period of Performance (POP) (WILL BE UPDATED)

The period performance for this contract is delivery of the final
product *[TBD]* calendar days after the award. 

##### 5.9.3 Place and Hours of Performance (UPDATE WITH AK SPECIFICS)

[Add Alaska language]

##### 5.9.4 Special Terms and Conditions

###### 5.9.4.1 Section 508 Compliance Requirement (CONFIRM 508 APPLIES TO AK)

The contractor shall support the Government in its conformance with
Section 508 throughout the development and implementation of the work
to be performed.

Section 508 of the Rehabilitation Act of 1973, as amended (29 U.S.C.
794d) requires that when Federal agencies develop, procure, maintain,
or use electronic information technology, Federal employees with
disabilities have access to and use of information and data that is
comparable to the access and use by Federal employees who do not have
disabilities, unless an undue burden would be imposed on the agency.
Section 508 also requires that individuals with disabilities, who are
members of the public seeking information or services from a Federal
agency, have access to and use of information and data that is
comparable to that provided to the public who are not individuals with
disabilities, unless an undue burden would be imposed on the agency.

The following standard is applicable for compliance:

   1194.22 Web-based Intranet and Internet Information and Applications.

The contractor should review the following websites for additional 508
information:
[http://www.section508.gov/index.cfm?FuseAction=Content&ID=12](http://www.section508.gov/index.cfm?FuseAction=Content&amp;ID=12)
<http://www.access-board.gov/508.htm>

<http://www.w3.org/WAI/Resources>


#### 6.0 Government Furnished Items (VALIDATE WITH TECH TEAM - RELEASE AS MUCH AS POSSIBLE)

The Government will furnish the data and scripts needed at time of
award. No other hardware or software will be provided by the Government.

#### 6.1 Transparency Policy

Vendors are advised that Alaska will publish on a publicly available
website documents associated with this requirement, including any
Requests for Quotation (including amendments), Question and Answer
exchanges with vendors (source-identifying information removed), and
other relevant information that is not confidential/proprietary in
nature or source selection sensitive information that would otherwise
implicate procurement integrity concerns. During the performance of
this contract, Alaska will similarly publish source code, data related
to project management (e.g., user stories, milestones, and performance
metrics), and top-line spending data.

#### 6.2 Data Rights and Ownership of Deliverables

It is Alaska's intent that any data or deliverable created as a result of
the work performed under the contract be committed to the public
domain.

It is the intention of Alaska to commit the following, but not limited
to, items to the public domain: all data, documents, graphics and code
created under this contract including but not limited to, plans,
reports, schedules, schemas, metadata, architecture designs, and the
like; new open source software created by the contractor and forks or
branches of current open source software where the contractor has made
a modification; new tooling, scripting configuration management,
infrastructure as code, or any other final changes or edits to
successfully deploy or operate the software.

The contractor shall use open source technologies wherever possible, in
support of the [18F Source Code Policy](https://github.com/18F/open-source-policy). All licenses must be expressly
listed in the deliverable. Regardless of license(s) used (e.g., MIT,
GPL, Creative Commons 0) the license(s) shall be clearly listed in the
documentation.

If the contractor needs to use work that does not have an open source
license, the contractor is required to request permission from Alaska, 
in writing, before utilizing that work in any way in connection with the
order. If approved, all licenses shall be clearly set forth in a
conspicuous place when work is delivered to Alaska.

If an open source license provides implementation guidance, the
contractor shall ensure compliance with that guidance. If implementation
guidance is not available, the contractor shall attach or include the
license within the work itself. Examples of this include code comments
at the beginning of a file or contained in a license file within a
software repository.
