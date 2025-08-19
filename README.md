> **Welcome!**
> This repo contains documentation describing the Alaska Department of Health (DOH) modernization project. It is intended to be a place where project participants can keep track of the overall project goals, the decision framework, progress to date and learnings as we work. It is also intended to be a project 'home page' where members can access important and up-to-date project information that exists somewhere else.

# EIS Modernization Project
### _Modernizing DPA technology and methods to achieve an integrated eligibility system_

----

_Contents:_

[Vision](#vision) | [The Challenge](#the-challenge) | [Our Hypothesis](#our-hypothesis) | [Risks](#risks) | [Project Initiation Milestones](#Project-Initiation-milestones) | [Ongoing Strategic Concerns](#ongoing-strategic-concerns) | [Important Resources](#important-resources) | [System Information](#system-information-user-account-must-be-granted-by-the-state-of-alaska) | [Technology Requirements](#technology-requirements) | [Contributing](#contributing-to-this-repo)

----

## Vision
Alaska Department of Health (DOH) is developing a modern, integrated eligibility system that enables staff to more efficiently issue correct and timely benefits to Alaskans who need help meeting their basic needs. Utilizing agile development and modular procurements, DOH has the goal of implementing an eligibility system that not only meets state and federal standards, but is user friendly for our clients, our eligibility staff, and our technical staff.

## Team
Fundamental to this project is our integrated, cross-functional team approach. By staffing a unified, durable team from the Division of Public Assistance (Division), IT Services (IT), and Grants & Contracts (Procurement), we work to break down silos that could inhibit the success of our project. We plan together, procure together, build together, and operate together. We are a single delivery team. This ensures:

- Division product ownership *and* a product team with diverse expertise from Division, Procurement, and IT.
- Division, Procurement, and IT is making capability improvements, allowing us to break vendor lock-in dependencies.
- Process and tool improvements support innovation and common approaches

We are supported in this effort by our department and division leadership. We work in partnership with CMS, FNS, and a network of vendor collaborators.

## Modernization
"Modernization" does not just refer to updating systems built long ago. It means that we are rethinking every aspect of our work and looking for opportunities to improve. This includes product management, risk mitigation, staffing, procurement, development methods, technology choices, oversight response, design, user engagement, vendor management, and more.

We have already seen many benefits from these efforts and seek to spread these lessons throughout AK DOH wherever possible.

## Methods & Strategies
- [How we work](/how-we-work.md)
- [Procurement strategy](/procurement-strategy.md)
- [Technical strategy](/tech-strategy.md)
- [Design strategy](/modular-experience.md)

----

## Product

### Value Statements

| Group  | Value |
|:---|:---|
| **Low income Alaskans** | We want to create an environment where needy Alaskans feel supported by a system that provides timely and accurate benefits along with self-service access to status of applications. |
| **DPA Field Staff** | We want to create an environment where DPA Field staff can be productive and feel fulfilled by giving them efficient tools and processes and timely access to the information that they need in order to serve low income Alaskans. |
| DPA Systems Operations Staff | We want to create an environment where Sys Ops workers feel confident about maintaining the systems and supporting DPA field staff in their work. |
| **IT Services Staff** | We want to create an environment where DOH FMS-IT workers feel confident and empowered to rapidly meet DPA field staff and Sys Ops needs while preserving and extending DPA’s return on investment. |
| **DOH Leadership** | We want to create an environment where system capability and stability free department leadership to make directional decisions based on accurate and timely data, and show value for system investments. |
| **Department of Administration (DOA) Office of Information Technology (OIT) Staff** | We want to create an environment where OIT can rely upon clearly defined and agreed upon support procedures and responsibilities to efficiently deliver service to DOH. |
| **Federal Partners** | We want to create an environment where our Federal partners can count on the State to act quickly on Federal mandates and requests, and that they can quickly and easily get accurate information from their State partner when they need it. |
| **Tribal Organizations** | We want to create an environment where tribal organizations can easily access information about their members and be able to assist them in getting the benefits they are eligible for in an automated fashion. |
| **Hospitals** | We want to create an environment where hospitals can input patient information and receive instant eligibility determination, including issuance of the benefit, without DPA intervention. |
| **State Agency Partners** | We want to create an environment where our state agencies can trade information seamlessly, timely, and effortlessly. This two way transfer of information should be immediate and automatic, using established standards based data structures. |
| **General Public** | We want to create an environment where DOH can demonstrate that public monies invested in information technology and public assistance delivery efficiently provide positive outcomes. |

### Mission Model Canvas
We have visualized the various areas of concern with respect to the overall vision into a Mission Model Canvas. Our product strategy will pay attention to these areas of concern and their relationships in order to ensure that the right thing is being delivered to the right beneficiaries. It will evolve over time as needed.

[**View the canvas**](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1576183670083/61c5a6fea3288415cd62a0aa01afa3057fa51c6a)

### The Product Roadmap
This is where we work out and communicate our delivery plan in the context of our strategy. The first column contains some background information about our beneficiaries, stakeholders, partners, teams and activities. The second column contains a set of milestones ordered from top to bottom according to the team's current priorities. Each milestone contains a set of increments designed to deliver the desired outcome. In each increment, you will see the affected user/stakeholder groups, some detail about the work, and an indication of which teams/what kind of activity is involved. The final column contains all unscheduled work as we know it.

[**View the roadmap**](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1576183680860/c1682951c77a41f29cb684cff893ff837f70b084)

## The Challenge
The challenge is rooted in the need for Alaska to migrate these programs off of their "old legacy" eligibility system, EIS, to something that costs less to operate and is more flexible to change. The EIS system does what it does well, but it is built in an old technology (COBOL on a mainframe) that is difficult to change. It is also expensive to host, and as other agencies in Alaska migrate away from the system, DOH will be responsible for more and more of this cost. Further, expertise for this type of technology is aging out, so it will be harder and harder to support it going forward. Moving away from this system is the ultimate goal.

To this end, Alaska entered into an agreement with a contractor to migrate all programs to a customized system that was supposed to be more automated, flexible and maintainable. The first phase of this migration was problematic, leaving the State with a partially implemented eligibility system, ARIES, which at this time only contains MAGI Medicaid. Work on the previous project plan ended summer 2016.  The State is now determining eligibility in two systems forcing a good deal of manual workarounds so that the State can continue to deliver services.

Delays in fully implementing ARIES have resulted in delays processing applications.  Working in two eligibility systems results in duplication of effort depending on which program an individual has requested.  This has caused a significant decrease in worker productivity.

## Our Proposition
We have moved away from a legacy "Big Bang" waterfall acquisitions process to a more modular approach, emphasizing user centered design, agile product development, and DevOps practices. We believe doing this will incrementally improve the current situation in a measurable and sustainable way, and eventually allow the continued migration of programs away from the EIS system and onto something more modern, flexible and maintainable.

We will know we are successful if we can increase worker productivity and if benefits are being provided in a timely manner to those who are eligible. An early win demonstrating to State workers and the Legislature that we are moving in the right direction occurred with the implementation of the [United Search Feature](https://github.com/AlaskaDHSS/RFP-Search-Unification)

## Risks


| Description  | Criticality (1 - 5) <sup>*</sup> | Status  |
|:---|:---:|:---:|
| The depth of the vendor pool available that understands agile delivery and can do modular procurement might be limited.  | 2  | Derisked  |
| As we integrate with multiple new systems, both internal and external, (ARIES database,CMS data hub, MCI, EIS Mainframe) complexity arises and can cause delays or complications. The amount of complexity for new integrations is not well known.     | 2  |  In progress |
| The quality/consistency of the data may be a blocker to goals we have around reporting and analysis.  | 4  | In progress  |
| The availability of appropriate platforms within the state technology environment for deploying prototypes is limited.   | 2  | Derisked  |
| The fixed and saturation-based network latency in different locations may create performance issues for web applications that load data asynchronously or via multiple requests.  |  4 |  Not started |
| There is a risk that we won't be able to deploy to production frequently enough that we can work in an agile fashion.  | 2  | Derisked  |
| There is a risk that vendors won't be able to easily work with the legacy ARIES code and existing authentication methods. | 5  | In progress  |
| There is a landscape of existing solutions that could potentially be leveraged instead of building from scratch. Evaluation into these solutions is ongoing.  |  2 |  In progress |
| There is a risk that the DOH authority to operate (ATO) process will prevent us from being able to deploy continuously to a production environment.  | 5  | In progress  |
| There is a risk that by having multiple vendors contributing to the same codebase, we increase the complexity of integration. There could be problems that arise specifically from the logistics and timing of multiple contributors.   | 3  |  In progress |

 \* 1 = low criticality; 5 = high criticality

## Project Initiation Milestones

- [x] Identify product owner and team - Done 2/28/17
- [x] Identify where to start - Done 3/2/17 (Search API and UI to support)
- [x] Foundational work
  - [x] Product vision - Done 5/8/17
  - [x] Product roadmap - Initial roadmap created 5/22/17
  - [x] Funding strategy
  - [x] Market research and vendor outreach
  - [x] Acquisition strategy
  - [x] [DevOps MVP](https://github.com/AlaskaDHSS/DevSecOpsMvp)
  - [x] [Technical prototyping](technical-prototyping.md)
- [X] [Draft solicitation documents and vendor outreach](https://github.com/AlaskaDHSS/EIS-Modernization/wiki)
- [X] First solicitation - RFP released November 3, 2017 (https://github.com/AlaskaDHSS/RFP-Search-Unification)
- [X] Award first contract
- [ ] Subsequent acquisition(s) - [In progress](https://github.com/AlaskaDHSS/EIS-Modernization/issues)
- [ ] Regular Roadmap updates - In progress

## Ongoing Strategic Concerns
* Integrating security into DevSecOps
* Data normalization
* Communication (external and internal)
* System integration (of the various modules)
* DevSecOps and continuous delivery
* Support and maintenance
* Documentation
* Alignment with CMS, FNS, and other Federal Partners

## Important Resources

Alaska team
* [Alaska organizational chart](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1681250908368/41b7502a14f34e48d7af905c343ff0746054ef11?sender=tracymack7142) (includes product team members)
* [Alaska Department of Health organizational chart](https://health.alaska.gov/media/irchaabd/orgchart.pdf) (official departmental org chart)

EIS-M project management
* This repo - This repository serves as the overarching umbrella repo for the EIS-M project. Please note that each solicitation will have its own GitHub repository
* [Search Procurement Repo](https://github.com/akhealth/RFP-Search-Unification)
* [AVS-EVS Procurement Repo](https://github.com/akhealth/RFP-AVS-EVS)
* [Microsoft Teams](https://teams.microsoft.com/l/team/19%3a3ac701697e2f4d279a28c0e33b00a092%40thread.skype/conversations?groupId=6bf46ba5-dd04-4ed8-b1c2-c9152ecddecd&tenantId=20030bf6-7ad9-42f7-9273-59ea83fcfa38) (Private)
* [Azure](https://alaskadhss.visualstudio.com) (Private)
* [Mural](https://app.mural.co/t/dhssalaska0106) (Private)

Key documents

* [2/28/17-3/2/17 Initial workshop findings](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1576183591439/09f86a74829ad590d598995285303d59e5b86f3c) (Private)
* [Modular product design strategy](modular-experience.md)
* [Usability Research](https://github.com/AlaskaDHSS/EIS-Modernization/blob/master/UsabilityResearch.md)


## System Information (User account must be granted by the State of Alaska)
* Link to the SSP User Acceptance Testing Environment: https://uat.aries.alaska.gov
* Link to the Worker Portal User Acceptance Testing Environment: https://uat.myaries.alaska.gov

## Technology requirements
We are working with the Microsoft technology stack. Please see [DevSecOps.md](DevSecOps.md) for specific requirements.

See our [How we Work document](how-we-work.md) for more about how we work with external vendors, accept code, and conduct code reviews.

## Contributing to this repo
* Read the [CONTRIBUTING](CONTRIBUTING.md) Policy
* Questions or suggestions? Open a [new issue](https://github.com/18F/alaska-dhss-modernization/issues) to ask or suggest.
* Want to send us a change? Create a [new pull request](https://help.github.com/articles/creating-a-pull-request/).

