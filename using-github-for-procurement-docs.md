# Using GitHub to Develop Procurement Documents


As part of the effort to modernize its existing public benefit
eligibility systems, the State of Alaska DHSS has adopted a modular
procurement strategy, and is using Github to develop and release
[procurement
documents](https://github.com/AlaskaDHSS/RFP-Search-Unification) and
solicit comments / feedback from the vendor community.

There are a number of [notable examples](https://ads.18f.gov/) where
federal, state and local governments have used Github to develop
procurement related materials, and to engage with vendors as part of the
procurement process (most notably 18F’s use of Github as the foundation
for it’s [micro-purchase platform](https://micropurchase.18f.gov/)).
Github offers governments an opportunity to develop procurement
materials in an open (and even collaborative) fashion, and many features
of the Github platform lend themselves well to interacting with vendors
during a procurements.

However, the State of Alaska’s use of Github for developing and
releasing procurement documents is new and there are undoubtedly
opportunities for improvement. This document is meant to summarize
feedback both internal staff, 18F and vendors on the use of Github for
developing procurement documents and to identify some steps that could
be taken to improve the process in the future.

## Internal and External Feedback on Github

The State of Alaska DHSS and 18F held an internal retrospective on the
initial eligibility modernization RFP, and the use of Github was raised
during these discussions.

From the perspective of the state, [Github
issues](https://guides.github.com/features/issues/) presented an
efficient way to both solicit and respond to vendor questions during the
RFP process. The ability to assign issues to individuals for response,
and use labels to organize and filter responses were all helpful. And
the ability to ensure that all questions and answers were viewable
publicly can foster trust in the process and help prevent duplicative
questions.

State of Alaska DHSS staff raised issues with regard to keeping their
[official vendor document
website](https://iris-vss.alaska.gov/webapp/PRDVSS1X1/AltSelfService)
in sync with changes to procurement documents in Github. Github is ideal
for making iterative changes to documents, and for allowing a variety of
different RFP stakeholders to comment on and offer changes to documents,
but ensuring that all changes made in Github were filtered back to the
state’s vendor website prove cumbersome.

Vendors generally reported a positive experience using Github to follow
the development of RFP documents on Github, but did raise concerns about
the the ability to be notified when changes were made. It’s not
unreasonable to assume that a technology company will have the
organizational capacity to acclimate to and use Github, but those
monitoring the RFP process at vendor companies are sometime not
technology people, but business development or communications people.
Github may not always be as intuitive to this cohort of users as
initially assumed, and it may be unclear if and when vendors are allowed
to provide comments or suggestions. And even for those more comfortable
with using Github, the signal to noise ratio for notifications from
changes may not be optimal.

## Suggested Improvements

With this feedback in hand, there are several concrete steps that the
State of Alaska DHSS can take to improve it’s use of Github to develop
and issue RFP documents, and to engage with vendors.

### Use Github as the Primary Source for RFP Documents

Instead of trying to keep documents on the state’s vendor website in sync with changes on Github, the state will simply link to the RFP documents housed in Github and use the Github version as thec "official version of the RFP and associated documents. This will remove the burden of keeping these two separate copies of RFP documents in sync, and will help eliminate confusion from vendors who might be unser where the latest copy of an RFP document is located.

### Provide Clearer Guidance Upfront on Contributing

To better ensure that vendors understand when and how to offer comments or suggestions, the state and 18F should develop a [clearer set of guidelines](https://github.com/AlaskaDHSS/RFP-Search-Unification/blob/master/CONTRIBUTING.md) on contributing that better ensures vendors understand the “rules of the road.” This is particularly important if the representatives from vendor firms are less familiar with Github and contributing to open source projects.

### Simplify the Process for Notification of Changes 

While Github provides a [number of options](https://help.github.com/articles/about-notifications/) for configuring how notifications are received, and what actions trigger notifications, the state could take steps to make this process simpler. For example, instead of assuming that vendors are following all changes to a repository, use a specific Github issue to indicate when substantive changes are made to documents. Vendors could be directed to [subscribe to a specific issue](https://help.github.com/articles/subscribing-to-and-unsubscribing-from-notifications/) and follow changes announced there, as opposed to getting notification of all changes in a repo and having to determine which changes are substantive and which are not.

In addition, a more standard listserv or mailing list for vendors might help cut out some of the noise from Github notifications, and might be attractive for users at vendor companies that are less familiar with Github.

### Rethink use of Github’s Wiki Feature

The state may want to rethink the use of Github’s Wiki feature, which was used to [post updates](https://github.com/AlaskaDHSS/EIS-Modernization/wiki) for vendors during the development of the first RFP. Github’s wiki feature offers limited ways to be notified when changes are made (though it is possible to [subscribe to an Atom feed](https://github.com/AlaskaDHSS/EIS-Modernization/wiki.atom), this feature is not well publicized and might not be practical for those participating from vendor companies).

One issue with the use of a Github wiki during the development of the first RFP is that the documents were initially developed in a project-level repository (while they were still in draft form) and then were migrated to a standalone repository. The wiki for vendor updates remained in the original, project-level repository, potentially creating a disconnect. If a github wiki is used in subsequent procurements, it should reside within the same repository as the RFP documents, and it should be clearly communicated to vendors that it will be the vehicle for communicating changes.

Some of the vendor feedback suggested the use of a more traditional blog to announce substantial changes to RFP documents. While there are obviously a number of different ways to publish and maintain a simple project blog, one way to do this might be to leverage [Github pages](https://pages.github.com/) to deploy a simple website for RFP document changes.
