# Alaska’s Eligibility Information System Modernization Project Post-Mortem

## Reflecting on the good and the bad from Alaska and 18F’s first contract

July 25, 2018


## Background

In December 2017, Alaska’s Department of Public Assistance [announced the award](https://github.com/AlaskaDHSS/EIS-Modernization/blob/ffe20eeb7f7ca2b3b5606ddc5ee26838ee05f80f/vendor-info/RFP-Search-Unification-Award.md) of their first agile software development contract to Resource Data, Inc., an Alaskan company based out of Anchorage, AK. Work began in January, and concluded at the beginning of June. This was the first of many smaller contracts that Alaska is going to award as part of implementing their modular approach to modernizing their Eligibility Information System (EIS). See Alaska’s GitHub repositories for additional background information on the [modernization strategy](https://github.com/AlaskaDHSS/EIS-Modernization/blob/master/README.md) and the first RFP that will update the [Search](https://github.com/AlaskaDHSS/RFP-Search-Unification/blob/master/README.md) functionality of the existing systems. An [initial post-mortem about the RFP process](https://github.com/AlaskaDHSS/RFP-Search-Unification/blob/master/post-award-vendor-info/Post-Mortem_on_the_first_Alaska_buy.v2.pdf) was held after the contract was awarded, but before work had started; this post-mortem was held in June, after the vendor’s work had been completed.

## Purpose

On June 14, 2018, the EIS-R (Replacement) Product Team from Alaska and 18F held a "Post-Mortem" session as part of our commitment to continuous improvement. In thinking about the first buy in our modular procurement strategy, we considered what things worked well, and what things did not work well. The context for this exercise was the post-award period, during which [Resource Data, Inc.](https://www.resourcedata.com/) (RDI) was working.

## What worked well?

The team was asked to identify a number of items that worked well during the procurement, whether it was under our team’s control or not.

### The vendor’s work was very good

The team agreed that the work of RDI was high-quality, and that they proved to be a good partner.

- "Selected vendor did a solid job on delivery."
- "Procurement resulted in very clear top candidates."
- "Good trust with vendor."
- "What they said, they did."
- "This vendor was real from the get-go, and delivered what we asked for."

### DPA’s capacity for "owning product" and product management *grew significantly* over the course of the engagement

The team noted that DPA staff on the team had improved in their own work during the five-month process.

- "There was a great escalation in DHSS’ work over the course of the project."
- "Got to try out new things and experiment with new ways of working."
- "After some initial process hiccups, State tech staff got into delivery pattern for our responsibilities."
- "State staff paired well into new processes like code reviews."
- "Alaska started taking on more and more of the code reviews from 18F."
- "We hit a rhythm with regard to our process about halfway through."

### The vendor and DPA collaborated well

RDI worked in the style that DPA is transitioning to working in, and proved a good partner for this first procurement because of that.

- "The tone of the engagement was really trusting, open, and collaborative."
- "RDI led in the ways that we needed them to lead (crucially for this first procurement), and followed in the ways that we needed them to follow."
- "There were several occasions when we needed RDI to be flexible, and they did so well."
- "RDI called out issues when the State wasn’t doing what they committed — the contract document actually provided useful guidelines."

## What didn’t work well?

### DPA is yet to deploy software to users

While the product was built incrementally each sprint, the DPA team failed to successfully facilitate deploying that code to end-users at the end of each sprint, or even by the end of the engagement, failing to employ agile correctly and gain the associated benefits. This was primarily the result of security policies and practices, crafted for monolithic software procurements that are not compatible with the rapid delivery of user-tested software increments, that resulted in extensive Authority to Operate (ATO) work which is ongoing. Although the software produced during this buy was informed by user research, and iteratively built, users were not able to interact with functional code and reliable data and provide direct feedback on the built product, missing the benefits of the agile feedback loop.

- "We got stuck when it came time to actually access data and put it in front of users."
- "The failure to actually employ agile — delivering value to end-users — was far and away the biggest problem."
- "Delivering iteratively to actual users, and getting their feedback into the process, was a persistent challenge."

#### Action Items

- Do not begin agile projects without a clear path to deploy to staging at the end of the first sprint, and to production early and frequently.
- Ensure that projects under development have access to test data that is a realistic, complete simulation of the live data.
- Unblock the organizational obstacles to a path to deployment (which are specified as other issues, below).

### DPA and DHSS aren’t yet set up to support agile fully

It is not enough to hire an agile development team and have a DPA product team work with them in an agile fashion, because the entire process is dependent on people within DPA and DHSS who are not a part of that process, and may not have benefited from the resources and freedoms afforded to the product team. This disconnect, between those who were part of the process and those who weren’t, prevented the development team and the product team from completing their work.

- "Tension between a new approach and old one."
- "Now we’ve had to deal with a whole bunch of security issues we’ve never had to deal with before. Trying this in a new way uncovers those issue."
- "We’re not across the chasm of DevOps."
- "We focused on ’security plan,’ but we missed prioritizing and prototyping make-or-break technical security controls."
- "The state wasn’t able to keep pace with the vendor because of infrastructure/security issues."

#### Action Items

- Before beginning any new projects, research and document the security requirements, and engage with the security team as early as possible.
- Do a better job of helping the security team to perceive the time- and resource-saving value of DevSecOps.
- DHSS needs to adequately staff the security office. All indications are that three people is an insufficient number.
- Ensure that there is buy-in at all levels to help remove unnecessary friction when working with security, network, and ops teams.

### Critical design work fell to 18F

The initial design work was not what we believed that the project needed, necessitating a significant correction. That happened at a crucial point early in the development process, and required that we lean heavily on 18F to perform design work, to ensure a smooth transition and to keep the team from losing velocity. This was handled quickly and smoothly by all involved, and little time was lost as a result.

- "Initial design approach and subsequent need for 18F to establish the initial design direction to keep things moving."
- "Vendor pivoted agreeably"

#### Action Items

- When design is a critical part of an increment, be  thoughtful about design expertise representation on future vendor-assessment panels.
- Reconsider the point weighting that goes towards design expertise.
- Personnel changes are difficult to anticipate, and must be dealt with _in situ_, but should not be avoided if a course correction is necessary. This case was handled directly, and should serve as a guide for handling similar problems in the future.

### Unsustainable levels of involvement were needed from some staff

Some DPA staff on the project found it challenging to maintain the necessary level of work for their role, due to unrelated obligations on other projects. This sometimes blocked the work of others, preventing progress on the project.

- "People were spread across too many projects, not as focused as they should be."
- "Lack of availability for product owner in the engagement."
- "There were AK tech staff resource constraints."

#### Action Items

- When staffing a project, set expectations for how much time that it is going to require over what duration, and ensure that the necessary supervisors are prepared to support that commitment. This is especially true if the supervisors are in different organizations than most of the product team.
- Get adequate time from a project’s assigned staff, rather than adding additional staff to an inadequately-resourced project, in order to minimize complexity.
- If there is a need for staff that cannot be met with the current team, hire the right kind of talent to fill that staffing need.
