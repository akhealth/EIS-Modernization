# Prototype Findings

A summary of findings, lessons learned and additional questions from our work on the initial technical prototype. 

## Summary

The purpose of the initial technical prototype was to develop and test
different approaches to accessing data in Alaska DPA’s existing legacy
systems (the Master Client Index \[MCI\], ARIES and EIS) from a cloud
environment. A secondary benefit of this prototyping work was that it
provided an opportunity to validate some technology choices, and to
build out and refine our
[DevSecOps](https://github.com/AlaskaDHSS/DevSecOpsMvp) strategy.

A fuller description of our rationale to prototyping can be found in our
[project GitHub
repo](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/technical-prototyping.md),
and a [high-level
overview](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/assets/search-prototype-high-level-technical-overview.pdf)
of our technical design can be found here.

This document and the associated [prototype
code](https://github.com/AlaskaDHSS/ProtoWebApi) are not meant to be
prescriptive in nature - we expect vendors to use their best judgement,
experience and technical expertise to design and deliver great software.
Vendors should use this report and associated materials (contained
within public Github repos) as a supplement to the
[RFP](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/procurement-docs-search/Request-for-Proposals.md).

## Description

### Components

 The prototype lives in the
 [ProtoWebApi](https://github.com/AlaskaDHSS/ProtoWebApi) solution.
 This is an ASP.NET Web API application targeting the .NET Core 2.0
 platform and is deployed in the [Azure App
 Service](https://azure.microsoft.com/en-us/services/app-service/).
 The proxy API for interacting with legacy on-premise data sources is
 in the **AKRestAPI** directory, and the UI components are in the
 **wwwroot** directory. Tests are in **AKRestAPI**.Tests (just some
 sample controller tests for now).

 **MCI**: The Master Client Index (MCI) is an on-premise SOAP-based web
 service that supports searching for DPA clients by name and other
 other search criteria. The MCI contains high-level client information
 about individuals participating in state of Alaska programs. (e.g.
 Client IDs, demographic information, etc.)

 **ARIES**: Alaska’s Resource for Integrated Eligibility Services
 (ARIES) is a solution implemented by a previous vendor to support
 eligibility determination for MAGI Medicaid. This is a Java-based
 solution with a Postgres backend running in a managed hosting
 environment in the State of Alaska.

 **Staging Table**: Staging tables reside within the ARIES environment
 and are used to temporarily store transmitted application information
 received from the ARIES Self Service Portal (SSP) and the Federally
 Facilitated Marketplace (FFM). Note - we did not access staging tables
 data as part of the prototype, but the same method for accessing ARIES
 data should also work for these tables if necessary.

 **EIS**: The Eligibility Information System (EIS) is a legacy system
 that was implemented prior to the development of ARIES and contains
 applicant information for public assistance programs and services.
 This is a Natural/ADABAS system running on the state mainframe.
 Because of some limitations with the ARIES system, eligibility
 technicians occasionally “fall back” to EIS to process applications.
 As such, MAGI Medicaid applications are contained in both ARIES and
 EIS systems.

### Key Findings

 We used [Azure Hybrid
 Connection](https://github.com/AlaskaDHSS/DevSecOpsMvp/tree/master/hybrid-connection)
 to facilitate access to on-premise legacy systems from the [Azure App
 Service](https://github.com/AlaskaDHSS/DevSecOpsMvp/tree/master/appservice).
 Both links in the previous sentence point to our DevSecOpsMVP
 repository in Github. There you will find much more information about
 The AppService PaaS and the associated HybridConnection: gotchas,
 limitations, code, and other documentation. In general the AppService
 and HybridConnection are simple to create, configure, and operate.
 Limitations we’ve found so far (i.e. SQL Server only supports SQL
 Server Authentication over the Hybrid Connection) have not turned into
 blockers.

 Access to the EIS system can be achieved in several different ways,
 and we spent time exploring the use of SQL Server’s [Linked
 Server](https://docs.microsoft.com/en-us/sql/relational-databases/linked-servers/linked-servers-database-engine)
 functionality with an [ODBC connector for
 ADABAS](http://www.connx.com/databases/adabas-db.php) from Software
 AG. The most efficient method of accessing this data seems to be a
 simple RESTful service layer that runs on top of [EntireX
 Broker](http://www.softwareag.com/corporate/products/adabas_natural/appl_mod/products/entirex/how_it_works/default.asp)
 and small, custom Natural programs to access ADABAS. This latter approach was succesfully tested as part of our prototype work.

 Our prototype work ended up involving a number of representatives from
 the department and state security offices, and both groups have become
 more familiar with the approach to legacy data access we’ve developed
 during our work. However, interacting with these groups and ensuring
 that all required security checks and documentation are completed will
 be essential to successful product delivery.

## Relevant Repositories / Resources

* [Main prototype repo](https://github.com/AlaskaDHSS/ProtoWebApi)
(note, this repo is populated by our VSTS-based continuous
integration pipeline. Access to git repos in VSTS, which may
contain additional prototype code, will be provided to the
selected vendor.)

* A list of [general project
risks](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization#risks)
identified early in the project by the product team.

* A summary of our [prototyping
philosophy](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/technical-prototyping.md).

* A high-level overview of the [technical
design](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/assets/search-prototype-high-level-technical-overview.pdf)
of our initial prototype.

* A repo containing our [DevSecOps tools and
practices](https://github.com/AlaskaDHSS/DevSecOpsMvp).

* A list of [Trello
cards](https://trello.com/b/siAFtoWJ/alaska-medicaid-eligibility-information-system-replacement-eis-r-project)
relating to our prototype work (access will be provided to the
selected vendor).

## Other Questions / Considerations

One of the [risks we identified early in this
project](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization#risks)
was around network latency in DPA field offices in different locations
around the State of Alaska. This risk was not thoroughly explored
during the prototype phase because of limited time. High latency might
require a different technical design than the one used for our
prototype, which isolates access to various backend systems in separate
calls to a proxy service.

Legacy data schemas are complex and may be inconsistent across different
systems. We obtained a better understanding of the legacy data sources
through our prototyping process.  However, completely mapping these schemas and
reconciling them was beyond the scope of this work. Identifying which
data elements to return in a search solution and linking data in
different systems will be an important aspect of the search application
and will be closely tied to user research activities.

A requirement of the project is that new modules and features be
integrated into the state’s existing authentication and authorization
framework. This was [identified early in the prototyping
process](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/technical-prototyping.md#risks)
as an area of potential risk. And while our prototype does not leverage
this [existing
framework](https://www.ibm.com/support/knowledgecenter/SSPREK_7.0.0/com.ibm.isam.doc_70/ameb_webseal_guide/concept/con_ws_intro.html),
we did some early research to get a better understanding of the steps
required to do so.

Integrating new modules into the existing ARIES production environment
was identified as an area of risk, but the work and LOE required to do
this were not completed as part of our prototyping efforts.
