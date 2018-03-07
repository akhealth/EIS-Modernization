
## FFM Automated Registration (FAR) prototyping 

The next procurement in this effort will deal with inbound FFM referrals for individuals who apply for benefits directly through [healthcare.gov](https://www.healthcare.gov/), and whose Medicaid eligibility has already been determined by the FFM. Currently, all inbound FFM referrals require manual intervention by an agent (even for referrals which have a status of `determined eligible` from the federal marketplace).

This procurement will automate the registration of applications in the ARIES system received through the FFM, eliminating the need for manual registration (though some manual processing may still be needed for FFM referrals not already designated as `determined eligible`). This effort will:

* Reduce the burden on field agents, who currently register FFM applications manually.
* Help to reduce the backlog of applications
* Result in speedier issuance of benefits for applicants through the federal marketplace that have been assessed as eligible by the FFM.

## Risks

| Description  | Criticality (1 - 5)* | Status  |
|---|---|---|
| Accessing and modifying existing batch jobs that move applications received from the FFM through the ARIES system  | 5  | Not yet started  |
| Successfully matching applicants that come in through the FFM with existing demogrphic data (in the [MCI](https://github.com/AlaskaDHSS/RFP-Search-Unification/blob/master/4-Prototype-Findings.md#components)) and associating them with existing applications (if they exist)  | 5  | Not yet started  |
| Establishing a development environment to support the testing of modifications to the batch jobs and other components that might need to be modified to support this work.  | 4  | In progress  |
| Understanding more fully the process of how FFM appications populate the staging table and, more broadly the boundaries between different system components (Quartz scheduler, Mule ESB, etc.)  |  3 | Not yet started  |

* 1 = low criticality; 5 = high criticality

## Additional resources

* Prototyping [strategy session results](https://app.mural.ly/t/gsa6/m/gsa6/1518556396089/5d06a55c138f4ebf7e18dc0a3ac812e888a3f6a7). (Note - access might not be public)
