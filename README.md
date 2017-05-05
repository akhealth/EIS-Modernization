# Welcome!
This repo contains documentation describing the Alaska Department of Health and Social Services (DHSS) modernization project. It is intended to be a place where project participants can keep track of the overall project goals, the decision framework, progress to date and learnings as we work. It is also intended to be a project 'home page' where members can access important and up-to-date project information that exists somewhere else.

## Our Big Vision
Alaska Department of Health & Social Services (DHSS) is developing a modern, integrated eligibility system that enables staff to more efficiently issue correct and timely benefits to Alaskan’s who need help meeting their basic needs.  Utilizing agile development and modular procurements, DHSS has the goal of implementing an eligibility system that not only meets state and federal standards, but is user friendly for our clients, our eligibility staff, and our technical staff.

## The Challenge
The challenge is rooted in the need for Alaska to migrate these programs off of their "old legacy" eligibility system, EIS, to something that costs less to operate and is more flexible to change. The EIS system does what it does well, but it is built in a old technology (COBOL on a mainframe) that is difficult to change. It is also expensive to host, and as other agencies in Alaska migrate away from the system, DHSS will be responsible for more and more of this cost. Further, expertise for this type of technology is aging out, so it will be harder and harder to support it going forward. Moving away from this system is the ultimate goal.

To this end, Alaska entered into an agreement with a contractor to migrate all programs to a bespoke system that was supposed to be more automated, flexible and maintainable. The first phase of this migration was problematic, leaving the State with a "new legacy" Medicaid eligibility system, ARIES, that is difficult for users to work with. And, the contractor walked away from the agreement in December of 2016, leaving the State with a partially implemented migration, virtually no ability to iterate on the new system and barely any ability to maintain or fix it. The State is now straddling the old system and new one, forcing a good deal of manual workarounds so that the State can continue to deliver services.

ARIES has arguably caused a _significant decrease in worker productivity_ as evidenced by a backlog of between 16,000 and 24,000 applications for Medicaid and other public assistance programs (the exact number is unknown due to bad data and duplication), and a documented decrease in application processing per worker per day from 12 to 4. Beneficiaries can wait months to receive benefits and workers are frustrated. Clients get frustrated with delays, and this causes them to submit duplicate applications thereby adding to the backlog and pressure.

## Our Hypothesis
We want to move away from a legacy "Big Bang" waterfall acquisitions process to a more modular approach, emphasizing user centered design, agile product development, and DevOps practices. We believe doing this will incrementally improve the current situation in a measurable and sustainable way, and eventually allow the continued migration of programs away from the EIS system and onto something more modern, flexible and maintainable.

We will know we are successful, if we can increase worker productivity and morale, among other things, and if benefits are being provided in a timely manner to those who are eligible. We are currently focused on getting a win here fairly soon so that we can show State workers and the Legislature that we are moving in the right direction.

## Risks
* The depth of the vendor pool available that understands agile delivery and can do modular procurement might be limited, at least in the early phases of the project. We continue to investigate the existence of these vendors.
* The level of effort required to read or write data across multiple environments (ARIES database, staging table, MCI, Mainframe) is not well known yet. We will de-risk this via prototyping
* The quality/consistency of the data may be a blocker to goals we have around reporting and analysis. We will de-risk via prototyping and product work to normalize the data.
* The ability to guide the end-user through large search result scenarios in a responsive way may create blockers to the value of improved search.  We will de-risk this via prototyping.
* The availability of appropriate platforms within the state technology environment for deploying prototypes is not well understood yet. We will de-risk this via prototyping.
* The fixed and saturation-based network latency in different locations may create performance issues for web applications that load data asynchronously or via multiple requests.  We will de-risk this via prototyping.
* There is a risk that we won't be able to deploy to production frequently enough that we can work in an agile fashion. We will de-risk this via prototyping and through developing a DevOps strategy with the State of Alaska.
* There is a risk that vendors won't be able to easily work with the legacy ARIES code and existing authentication methods. We will de-risk this via prototyping.
* There is a landscape of existing solutions that could potentially be leveraged instead of building from scratch. We need to constantly keep an eye out for this and advise vendors accordingly.

## Near-term Milestones
- [x] Identify product owner and team - Done 2/28/17
- [x] Identify where to start - Done 3/2/17 (Search API and UI to support)
- [ ] Validate starting point - In Progress
- [ ] Acquire a vendor - To Do
- [ ] First acquisition - To Do

## Product Vision & Strategy

**Product vision**

- [ ] Define product vision

**Strategy**

- [ ] Data considerations
   - Ontology - [definition](https://en.wikipedia.org/wiki/Ontology_(information_science))
- [ ] DevOp
   - Infrastructure, process
- [ ] Communications
   - Internal
   - External
- [ ] High-level navigation/IA scheme
   - Generalize it so that vendors can concentrate on the specific thing they were asked to do, and not step all over each other
- [ ] Alignment with CMS, FNS, and other Federal Partners
   - APD
   - Interoperability
- [ ] Procurement approach
- [x] [Modular product design strategy](modular-experience.md)

## Important Resources

Alaska team
* [Alaska organizational chart](http://mur.al/vzV3BEBJ)

EIS-R project management
* This repo - This repository serves as the overarching umbrella repo for the EIS-R project
* [Slack channel](https://gsa-tts.slack.com/messages/C3SM6SLGM/convo/C3M933336-1488211534.000271/) (Private)
* [Project Trello board](https://trello.com/b/siAFtoWJ/alaska-medicaid-eligibility-information-system-replacement-eis-r-project) (Private for now)
* [18F Project Folder](https://drive.google.com/drive/u/0/folders/0B4B0xeCMEaFyYmE0VFhTR3lTSms) (Private)

Key documents

* [2/28/17-3/2/17 Initial workshop findings](https://app.mural.ly/t/gsa6/m/gsa6/1488927409455/view/3842912505) (Private)
* [Research Synthesis]

Search module - API & UI 
* Technical prototype
    * [Diagrams for first prototype](https://app.mural.ly/invitation/mural/gsa6/1489619780239?sender=michaeltorres&key=1026750817)
    * [Trello board](https://trello.com/b/qiQq7T53/acq-ak-prototype-1) (Private for now)
    * [Design prototype](http://gsa.invisionapp.com/share/QDAZYEJPZ)
    * Prototype repo (TBD)
* Vendor solicitation (Coming)


## System Information (User account must be granted by the State of Alaska)
* Link to the SSP User Acceptance Testing Environment: https://uat.aries.alaska.gov 
* Link to the Worker Portal User Acceptance Testing Environment: https://uat.myaries.alaska.gov 

## Related projects
* [CMS project]
* [MO MMIS Modernization]
* [Multi-benefit application and enrollment prototype](https://usds.github.io/benefits-enrollment-prototype/) by [CMS](https://github.com/CMSgov)/[USDS](https://github.com/usds)/[18F](https://github.com/18F) | [repo](https://github.com/usds/benefits-enrollment-prototype)

## Contributing to this repo
* Read the [CONTRIBUTING](CONTRIBUTING.md) Policy
* Questions or suggestions? Open a [new issue](https://github.com/18F/alaska-dhss-modernization/issues) to ask or suggest.
* Want to send us a change? Create a [new pull request](https://help.github.com/articles/creating-a-pull-request/).
