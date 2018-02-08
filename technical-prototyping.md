**Note:** The [information about the first technical prototype](technical-prototyping-unified-search.md) originally on this page has been moved.

---

# Technical Prototyping
Especially when working with legacy systems, **it's important to test technical assumptions *before* scoping any kind of procurement** because there are almost certainly unknown hazards that can put your procurement at risk. These hazards can't be known unless you start building something.

Unlike most kinds of prototypes, technical prototypes are not focused on user experience, but rather on the mechanics behind the user's experience. They test things like "Can we really access the data we think we need?", or "How does this external API actually work?"—so they’re pretty bare-bones. They show *just enough* of the user-facing functionality to verify some kind of technical implementation. Practically, the prototype follows some user on a "happy path" user flow through that implementation.

**Prototyping a small end-to-end user flow is something that teams can do quickly before writing an RFP**, and should help identify any hazards in the code, the deployment process or any other technical aspect of a project. This will help teams properly scope the procurement and build out a reasonable RFP with some useful documentation for buyers and for vendors.

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


## Prototyping infrastructure

Through the process of standing up an initial technical prototype for the first product increment, we worked through a variety of initial challenges. Having done so, we are now positioned to more easily and quickly prove out technical questions. We can now take advantage of...

- **Security plans** - Agreement with state security teams about the applicable security requirements (should connect to documentation of that agreement)
- **Tailored IT standards** - (Is this similar to the security plans above; should connect to documentation)
- **[Agile and HCD practice](https://github.com/AlaskaDHSS/EIS-Modernization/blob/master/how-we-work.md)** - DHSS has embraced agile and human-centered design practices, works in product increments and sprints, and continuously seeks improvement.
- **Test data** - Test data has been aligned across MCI, EIS, ARIES for UAT and dev environments. A process for adding new test data has been established (links to documentation)
- **VSTS** - DHSS uses VSTS for version control, teams, git, security scans, etc. More information can be found [in the DevSecOps repo](https://github.com/AlaskaDHSS/DevSecOpsMvp/tree/master/vsts).
- **GitHub** - While we work in VSTS, we sync our code with GitHub as part of our deployment cycle to ensure our open source software is visible and accessible.
- **Service Proxy** - BizTalk ESB can be used to manage access to MCI, AREIS, EIS (Link to swagger docs)
- **Cloud/PaaS/Azure** - DHSS has adopted Azure and will be using this PaaS moving forward. More information on access can be found [in the DevSecOps repo](https://github.com/AlaskaDHSS/DevSecOpsMvp/blob/master/Azure.md).
- **CI/CD pipeline** - Continuous Integration / Continuous Deployment mechanism are now in place and documented [in the DevSecOps repo](https://github.com/AlaskaDHSS/DevSecOpsMvp/blob/master/vsts/GitBranchingStrategy.md).

## [IN PROGRESS] People & skills

Producing technical prototypes requires DHSS developers and product managers to devote time and energy working in the systems and building. To do this, we need...

- C# & .NET Core
- Front-end development
- Azure expertise
- On-prem service/data expert
- An experimental culture - The team needs to be committed to trying things out, experimenting, and learning from either successes of failures.
- Just do it attitude - working rough/imperfect, just getting started
- CI/CD understanding
- Staffing commitments
- Product management - High level vision, roadmap, modular/incremental thinking, prototype scoping
- Ability to identify risks
- Security office involvement
- Technical architecture vision/mediator (Risk)
- Approach to working with ARIES (Risk)

## [IN PROGRESS] Getting Started

- Identify the people invovled with prototyping efforts
- Identify required approvals from security office
- Identify the risks (facilitated session ?)
- Assign criticality level to risks
- Synthesize risks into actionable items
- Identify boundaries of concern for prototypeing effort (scoped around technical matters)

Create a template for this? 
