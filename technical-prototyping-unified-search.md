**Update:** The prototyping work for the first procurement is complete and the associated procurement [has been awarded](https://github.com/AlaskaDHSS/EIS-Modernization/tree/master/vendor-info#whats-happened-so-far). The [prototyping findings](https://github.com/AlaskaDHSS/RFP-Search-Unification/blob/master/4-Prototype-Findings.md) are available for review.

---

## Search unification prototyping

For our first procurement we are dealing with updating a new legacy code base (ARIES) that is very complex and difficult to understand, a deployment process that is opaque — and on top of that, we want to create new connections between legacy systems ARIES and EIS. The unknowns involved with this work are risky enough that we can't be confident that vendors will be able to deliver anything without more guidance.

As this is our first prototype, we will be testing out some of the more foundational things, like a vendor development environment and deploy process, that will apply to all buys, as well as setting up the lines of communication with internal technical staff that will be necessary throughout the project.

## Risks
Before we write this first RFP, we want to spend time prototyping so we can mitigate the following identified risks:

| Description  |  Criticality (1 - 5)<sup>*</sup> | Status  |
|---|:---:|:---:|
| Creating a development and deployment pipeline that will allow vendors to deliver code that can be automatically evaluated and pushed to a staging environment  | 2  |  In progress. See [DevSecOps Strategy](https://github.com/AlaskaDHSS/DevSecOpsMvp). |
| Creating a process to get the delivered code into a production environment on a continuous basis  | 5  | In progress. See [DevSecOps Strategy](https://github.com/AlaskaDHSS/DevSecOpsMvp).  |
| Verifying that the existing identity service can be used for user authentication/authorization  |  3 | In progress. |
| Accessing data from the legacy EIS system to show in search results  | 3  |  In progress. |
| Accessing data from the ARIES system and staging table to show in search results  | 2  | In progress.  |
| Validating that the data coming from multiple systems is potentially reconcilable  | 4   | Not started.  |
| Deploying existing ARIES code to production  | 5  |  Not started. |

 \* 1 = low criticality; 5 = high criticality

Prototype documentation:
* [Prototype findings](https://github.com/AlaskaDHSS/RFP-Search-Unification/blob/master/4-Prototype-Findings.md)
* **[Prototype]** <-- **ADD THIS**
* [Prototype code](https://github.com/AlaskaDHSS/ProtoWebApi)
* [High-level technical overview](https://github.com/18F/acq-alaska-dhss-modernization/blob/master/assets/search-prototype-high-level-technical-overview.pdf)
* [Conceptual Diagram](https://app.mural.ly/t/gsa6/m/gsa6/1489619780239/view/4116522087)
* [Interactive mock](http://gsa.invisionapp.com/share/QDAZYEJPZ)
