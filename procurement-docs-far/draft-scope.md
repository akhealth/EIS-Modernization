# Description

Federally Facilitated Marketplace Automatic Application Registration
(FAR)

## Purpose of the RFP

The Department of Health and Social Services, Division of Public
Assistance (DPA), is soliciting proposals for a Contractor to
continuously deliver iterations of software that enables the automated
registration of applications received from the Federally Facilitated
Marketplace (FFM).

### Background Information

**BACKGROUND**

The background for this project as a whole is
detailed in the project README in DHSS primary [GitHub
Repo](https://github.com/AlaskaDHSS/acq-alaska-dhss-modernization/blob/master/README.md).
For this solicitation we plan to take the lessons we have learned in our
first procurement and apply them to our processes. The ARIES system
connects to the Federally Facilitated Marketplace (Healthcare.gov) to
accept public assistance applications for Medicaid. Alaska is what is
known as a determination state, which means that the federal marketplace
is authorized to make Medicaid eligibility determinations where
possible. At this time roughly half of all applications received are
received with a status of “determined eligible”. The remainder of
applications are received in a variety of statuses that require some
input from eligibility workers. For applications received by DPA from
the FFM, there is an intermediate step inserted into the process to
“register” the application. This registration process is a manual lookup
to ensure that the application is associated with any existing records
for the same client that may exist. This manual step is largely
unnecessary and can be automated.

**OBJECTIVES**

* Alaska Department of Health and Social Services (DHSS) goals for the FFM
Automated Registration (FAR) procurement are as follows:

* Reduce the amount of manual intervention by Division of Public
Assistance (DPA) in processing incoming FFM applications.

* Decreased burden on DPA field staff as they process incoming
applications for program benefits.

* Allow DPA application intake staff to focus on registering
applications for other application submission methods.

* Increase the number of applications processed per worker, per day, so
that potential beneficiaries can get their benefits sooner.

* Decrease time for FFM applicants to receive their benefits.

### Scope of Work

The scope of this contract is for the Contractor to continuously deliver
iterations of updated ARIES software that automates the FFM application
registration process. Currently this process requires a step where a
clerical office worker reviews the application, and prepares it for
eligibility determination. The changes to this process will move the
applications either directly to benefit issuance, or to a queue to be
worked by eligibility workers. This work will necessitate updates to the
business logic used to route applications within the current ARIES
system, as well as visual UI updates to let workers know how to process
incoming work.

The State of Alaska will provide documentation on how to access data
sources, describe existing authentication systems, and discuss how to
continuously deploy work to a staging environment.

### Requirements

The Contractor shall provide the following services:

* Contractor shall update the application workflow to route applications
received from the FFM to either the batch job to automatically process
eligibility or to a work queue to have eligibility determined by an
eligibility technician.

* Contractor shall update the relevant batch processes that currently
exist within the ARIES system.

* Contractor shall update the necessary tasks to suppress tasks that no
longer apply and create any new needed tasks

* Contractor shall review existing research artifacts and conduct
additional user research in order to determine user needs so that the
contractor can design and deliver interfaces/data views that are most
useful.

* Contractor shall conduct usability testing and gather feedback from
DPA workers on an ongoing basis as solutions are explored and software
is delivered, and incorporate feedback.

* Contractor shall ensure that automated task generation is updated to
reflect the new workflow.

* Contractor shall ensure that solution integrates with existing
technology choices and technical stack.

* Contractor shall continuously deliver working software for use in the
Alaska production environment.
