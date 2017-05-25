## Technical Prototyping
In working with legacy systems, it's especially important to test technical assumptions *before* scoping any kind of procurement, because there are likely unknown hazzards that could put your procurement at risk, and these hazzards can't be known unless you start building something. 

Prototyping a small end-to-end user flow is something that we can do quickly before writing an RFP, and should help identify any hazzards in the code, the deployment process or any other technical aspect of a project. This will help us scope the procurement and build out a reasonable RFP based on this documentation. This documentation will also be extremely valuable to vendors who actually end up doing the work because they'll have some sort of guidance already. Prototyping will be done continuously as we acquire the various pieces of the future system, so this is a practice, not a one time thing. 

## The Alaska DHSS Modernization Project



## Our first prototype
For our first procurement we are dealing with updating a new legacy code base (ARIES) that is very complex and not particularly well understood, a deployment process that is even less clear, and on top of that, we want to create new connections between legacy systems ARIES and EIS. The unknowns involved with this work are risky enough that we can't be confident that vendors will be able to deliver anything without more guidance. 

We have begun the prototyping process and have been focusing on the following:

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
* [Trello board](https://trello.com/b/qiQq7T53/acq-ak-prototype-1) (Private for now)

