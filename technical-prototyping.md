# Technical Prototyping
Especially when working with legacy systems, **it's important to test technical assumptions *before* scoping any kind of procurement** because there are almost certainly unknown hazards that can put your procurement at risk. These hazards can't be known unless you start building something.

Unlike most kinds of prototypes, technical prototypes are not focused on user experience, but rather on the mechanics behind the user's experience. They test things like "Can we really access the data we think we need?", or "How does this external API actually work?"—so they’re pretty bare-bones. They show *just enough* of the user-facing functionality to verify some kind of technical implementation. Practically, the prototype follows some user on a "happy path" user flow through that implementation.

**Prototyping a small end-to-end user flow is something that teams can do quickly before writing an RFP**, and should help identify any hazards in the code, the deployment process or any other technical aspect of a project. This will help teams properly scope the procurement and build out a reasonable RFP with some useful documentation for buyers and for vendors.

**Our prototypes:**

- [Unified search](technical-prototyping-unified-search.md)
- [FFM automation](technical-prototyping-ffm-automated-registration.md)
- [Automated Renewals](https://github.com/AlaskaDHSS/RFP-ARIES-AutomatedRenewals/blob/main/Attachment%2007%20Automated%20Renewals%20Technical%20Prototype%20Findings.md)

## When we prototype

Throughout this project **we will be using technical prototyping** whenever we are faced with some question about integration with existing systems, the nature of existing data sources, or any other existing technical process that we plan to leverage as part of our planned acquisition. We may change direction at times, based on what we learn through prototyping. We may decide to pursue a completely different implementation, or even a different set of features entirely. Best case is that we can proceed with the original plan, only now with much more information that will help ensure the success of the acquisition.

## Why we prototype

Prototyping is learning. For us, it allows us to learn firsthand about the challenge before us so that we can take on the work from a more empowered position. Technical prototyping helps us:

- **Reduce risk** | Prototypes help us identify problems fast when the risk is far lower than when time is ticking with a vendor on board so that we can remove barriers to success early.
- **Validate direction** | By testing out our intended vendor _ask_, we can validate if the planned work is viable. If it is, we can proceed. If the planned path proves unviable, we can more easily adjust course.
- **Understand business needs** | By exploring a small end-to-end user flow, our product team surfaces and learns about business and policy needs, developing greater subject matter expertise.
- **Write a good RFP** | The lessons learned through prototyping help inform the content of our requests for proposals, making the project focus sharper and less speculative.
- **Prepare vendors** | Vendors benefit from the investigation by having more detailed and accurate information upon which to build their proposals. After award, they understand the landscape better and can jump right into the work.
- **Develop expertise** | By actively working in system code to prove out hypotheses, we retain and grow in-house technical expertise with our systems and understanding of what vendor developers need to succeed.
- **Refine infrastructure** | Technical prototyping creates opportunities to improve and refine our infrastructure.
- **Be transparent** | By working in the open on our prototypes, we increase visibility for all our stakeholders and the larger Alaska community.

## What we prototype

Technical prototypes should address risks identified by the product team. The approach to using technical prototypes borrows heavily from the idea of a [code spike](http://agiledictionary.com/209/spike/) in agile software development. Code spikes are not meant to produce production ready code, and should be designed to leverage the simplest possible solution to identify solutions to an outstanding question or potential risk. Technical prototypes. like code spikes, should help give the product team clarity on the level of efforts required to address risks that have been identified in the planning process.

## Prototyping infrastructure

Through our initial prototypes efforts, we worked through a variety of initial challenges. Having done so, we are now positioned to more easily and quickly prove out technical questions. We can now take advantage of...

- **Security plans** - Agreement with state security teams about the applicable security requirements 
- **Tailored IT standards** - (Is this similar to the security plans above; should connect to documentation)
- **[Agile and HCD practice](https://github.com/akhealth/EIS-Modernization/blob/master/how-we-work.md)** - DOH has embraced agile and human-centered design practices, works in product increments and sprints, and continuously seeks improvement.
- **Test data** - Test data has been aligned across MCI, EIS, ARIES for UAT and dev environments. A process for adding new test data has been established 
- **Azure DevOps** - DOH uses Azure DevOps for version control, teams, git, security scans, etc. More information can be found [in the DevSecOps repo](https://github.com/akhealth/DevSecOpsMvp).
- **GitHub** - While we work in Azure DevOps, we intend to sync our code with GitHub as part of our deployment cycle to ensure our open source software is visible and accessible.
- **Service Proxy** - BizTalk ESB can be used to manage access to MCI, ARIES, EIS 
- **Cloud/PaaS/Azure** - DOH has adopted Azure and will be using this PaaS moving forward. More information on access can be found [in the DevSecOps repo](https://github.com/akhealth/DevSecOpsMvp/blob/master/Azure.md).
- **CI/CD pipeline** - Continuous Integration / Continuous Deployment mechanism are now in place and documented [in the DevSecOps repo](https://github.com/akhealth/DevSecOpsMvp/blob/master/vsts/GitBranchingStrategy.md).

## People & skills

Producing technical prototypes requires DOH developers and product managers to devote time and energy working in the systems and building. To do this, we leverage some or all of the following:

- Familiarity with C# & .NET Core
- Front-end development 
- Experience with Azure
- Familiarity with Git, Azure DevOps and an understanding of CI/CD 
- Ability to identify risks
- On-prem service/data expert
- An experimental mindset - The team needs to be committed to trying things out, experimenting, and learning from both successes or failures
- A bias toward action - working in a deliberately rough & imperfect way in order to make progress mitigating risk
- Product management - High level vision, roadmap, modular/incremental thinking, prototype scoping

## Getting Started

- Identify the people involved for prototyping efforts to be successful
- Identify required approvals from security office
- Identify the risks (this may be a facilitated session, where a team collectively identifies potential risks)
- Assign criticality level to risks
- Synthesize risks into actionable items, and identify risks outside scope of prototyping activity
- Identify boundaries of concern for prototyping effort (scoped around technical matters)
