## Technical Prototyping
In working with legacy systems, it's especially important to test technical assumptions *before* scoping any kind of procurement, because there are likely unknown hazzards that could put your procurement at risk, and these hazzards can't be known unless you start building something. 

Unlike most kinds of prototypes, technical prototypes are not focused on user experience, but rather on the mechanics behind the user's experience. They test things like "Can we really access the data we think we need?", or "How does this external API actually work?", so, they are pretty bare bones. They show *just enough* of the user facing functionality to verify some kind of technical implementation. Practically, the prototype follows some user on a 'happy path' user flow through that implementation.

Prototyping a small end-to-end user flow is something that teams can do quickly before writing an RFP, and should help identify any hazzards in the code, the deployment process or any other technical aspect of a project. This will help teams properly scope the procurement and build out a reasonable RFP with some useful documentation for buyers and for vendors. 

## The Alaska DHSS Modernization Project
Throughout this project we will be using technical prototyping whenever we are faced some question about integration with existing systems, the nature of existin data sources, or any other existing technical process that we plan to leverage as part of our planned acquisition. We may change direction at times, based on what we learn through prototyping. We may decide to pursue a completely different implementation, or even a different set of features entirely. Best case is that we can proceed with the original plan, only now with much more information that will help ensure the success of the acquisition.

## Our first prototype
For our first procurement we are dealing with updating a new legacy code base (ARIES) that is very complex and not particularly well understood, a deployment process that is even less clear, and on top of that, we want to create new connections between legacy systems ARIES and EIS. The unknowns involved with this work are risky enough that we can't be confident that vendors will be able to deliver anything without more guidance. 

Before we write this first RFP, we want to spend time prototyping so we can mitigate the following identified risks:

1. Creating a development and deployment pipeline that will allow vendors to deliver code that can be automatically evaluated and pushed to a staging environment - in progress
2. Creating a process to get the delivered code into a production environment on a continuous basis - in progress
3. Verifying that the existing identity service can be used for user authentication/authorization - in progress
4. Accessing data from the legacy EIS system to show in search results - blocked
5. Accessing data from the ARIES system and staging table to show in search results - not yet started
6. Validating that the data coming from multiple systems is potentially reconcileable - not yet started
7. Deploying existing ARIES code to production - not yet started

Here are some documents:
* [High level technical overview](https://github.com/18F/acq-alaska-dhss-modernization/blob/master/assets/search-prototype-high-level-technical-overview.pdf) 
* [Conceptual Diagram](https://app.mural.ly/t/gsa6/m/gsa6/1489619780239/view/4116522087)
* [Interactive mock](http://gsa.invisionapp.com/share/QDAZYEJPZ)
* [Trello board](https://trello.com/b/qiQq7T53/acq-ak-prototype-1) (Private for now

