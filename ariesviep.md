**ARIES vs. IEP**

Background:

[47.05.010](https://www.akleg.gov/basis/statutes.asp#47.05.010)
designates Department of Health (DOH), Division of Public Assistance
(DPA) as having responsibility for determining eligibility and
administration of Alaska’s public assistance programs. As a part of this
designation, DPA is charged with determining eligibility for each of the
programs based on state and federal regulation, governed by Alaska
Administrative Code, [Title
7](https://www.akleg.gov/basis/aac.asp#1.05). Our mission is to “promote
self-sufficiency and provide basic living expenses to Alaskans in need.”

This includes the following programs:

- Adult Public Assistance (APA)
- Alaska Temporary Assistance Program (ATAP)
- ATAP Work Services
- Childcare
- Family Nutrition
- General Relief Assistance
- Heating Assistance
- Interim Assistance
- Medicaid
	- Modified Adjusted Gross Income (MAGI)
	- Denali KidCare (SCHIP)
	- Aged, Disabled, Blind, and Long-Term Care
- Permanent Fund Dividend Hold-Harmless
- Senior Benefits
- Supplement Nutrition Assistance Program (SNAP) (aka food stamps)
- SNAP Employment and Training
- Tribal Assistance for Needy Families (TANF)
- Women, Infants, and Children Program (WIC)

DPA has federal partners, including the Centers for Medicare & Medicaid Services (CMS), Food and Nutrition Services (FNS), and Administration of Children and Families (ACF), who we work with to implement regulations and program rules.
To perform this work, DPA uses several technical systems. The core eligibility processing and benefit administration is managed by two systems. A legacy mainframe system, the Eligibility Information System (EIS), as well as a modern Modified Adjusted Gross Income (MAGI) Medicaid system.
Integrated Eligibility Platform (IEP)
DPA is developing a modern, Integrated Eligibility Platform (IEP) that enables staff to more efficiently issue correct and timely benefits to Alaskans who need help meeting their basic needs. While the IEP encompasses several systems, each with a specific purpose, the ARIES system is the cornerstone. DPA intends to leverage and extend the ARIES system to develop a fully Integrated Eligibility Platform (IEP), that supports eligibility determination and benefit administration for all public assistance programs, as well as integration/interoperability across the systems within the integrated eligibility platform.

![IEP Architecture](media/iep_architecture.png)

![IEP System](media/iep_system.png)

Utilizing agile development methods and modular procurements, DPA has the goal of implementing an eligibility system that not only meets state and federal standards, but is user friendly for clients, eligibility staff, and technical staff.
The State has been working with its federal partners and stakeholders to implement a continuously updated roadmap with the end- goal of a fully IEP that supports a variety of administrative services, including eligibility determination and benefit administration for all DPA public assistance programs. The roadmap is a holistic and hierarchical view of the Eligibility & Enrollment (E&E) Modernization projects.

**Alaska Product Roadmap**

The [Alaska Product Roadmap](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1576183680860/c1682951c77a41f29cb684cff893ff837f70b084) outlines key milestones to implementing the IEP, achieved through a modular strategy that prioritizes agile product development and DevSecOps practices, enabling continuous measurable and sustainable improvements as programs transition from the legacy system.
The following complimentary systems/components are included in the IEP..

**EIS**

While EIS has effectively supported program administration and benefit delivery for over 40 years, the technology on which it is based (IBM mainframe platform, COBOL software development language and ADABAS database management system) is becoming increasingly difficult and costly to maintain. Many significant changes in public assistance programs and program administration have occurred since the system was placed into production in 1984. Mandatory federal Medicaid provisions of the ACA, Welfare Reform, new program demands, and the continued growth and complexity in public assistance programs are creating a shift in business needs. The system is currently functioning well beyond the capacity for which it was designed and does not provide the flexibility needed to implement mandatory federal provisions. 
A key objective for the State of Alaska is to de-commission the EIS system as soon as possible; DPA has developed the [Alaska Product Roadmap](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1576183680860/c1682951c77a41f29cb684cff893ff837f70b084)  to plan for and support this objective. The actual decommissioning will be an Alaska DOH initiative/project; this is not specifically included in the [Alaska Product Roadmap](https://app.mural.co/t/dhssalaska0106/m/dhssalaska0106/1576183680860/c1682951c77a41f29cb684cff893ff837f70b084)  or the scope of the related projects.

**Alaska’s Resource for Integrated Eligibility Services (ARIES)**

ARIES is hosted in the Azure Commercial Cloud and built on a modern, scalable framework. Originally implemented to support eligibility determination and benefit administration for MAGI Medicaid, ARIES now serves as the cornerstone of Alaska’s Integrated Eligibility Platform (IEP).
The system is actively used by more than 400 Division of Public Assistance (DPA) staff, including eligibility technicians, administrative personnel, and management. In addition, ARIES supports access for multiple contractors and community partners who assist with public assistance program administration. Altogether, the system supports over 700 users and manages eligibility and benefits for more than 200,000 recipients.
DPA is currently working to de-couple and extend ARIES through the use of microservices, enabling the platform to support eligibility determination and benefit administration for additional public assistance programs, including the Supplemental Nutrition Assistance Program (SNAP).

**Mobius:** A document repository for IES related reports; this will ultimately be replaced by ILINX prior to decommissioning the EIS system.

**ILINX:** Image Source ILINX is a modular enterprise content services and process automation platform that leverages AI, hyper automation, low-code/no-code tools, intelligent capture from any source or device, mobile access, electronic forms, workflows, records management, multimedia processing, intelligent security, and seamless on-premises-to-cloud migration to modernize operations, streamline information management, and drive business process innovation. 
The state of Alaska has implemented ILINX to route and store client/application related documents using smart routing. 

**Alaska Connect:** Is the online self-service portal powered by ImageSource's ILINX Engage platform for the Alaska Department of Health's Division of Public Assistance (DPA). It allows eligible Alaskans to apply for public assistance benefits (such as SNAP, Medicaid via ARIES, and others), report changes, renew benefits, upload required documents, and manage their cases securely through a myAlaska-integrated login portal.  

**Current:** Current™ is a comprehensive operations management tool that integrates on-site and virtual workflows, translates agency data into real-time dashboards and reports, optimizes staff capacity, ensures compliance with state/federal requirements, and helps safety-net programs (like Medicaid, SNAP, child welfare, and unemployment insurance) serve more clients faster by addressing underlying system inefficiencies.

**Genesys Cloud:** Genesys Cloud (now branded as Genesys Cloud CX) is a leading cloud-based customer experience (CX) platform that includes a fully virtual contact center (often referred to as a virtual call center) solution, enabling organizations to manage customer interactions across voice, chat, email, SMS, social media, and digital channels without requiring on-premises hardware.

**IEVS:** PCG's Instant Eligibility Verification System (often abbreviated as IEVS or Instant Eligibility Verification System & API Gateway) is a fully configurable, cloud-based SaaS solution developed by Public Consulting Group (PCG) that serves as an eligibility data hub and API gateway. It automates the verification of applicant and beneficiary information by electronically querying dozens of federal, state, commercial, and third-party data sources (including income, assets via financial institutions, and other factors) to support faster, more accurate eligibility determinations, renewals, and ex parte processing for programs like Medicaid, SNAP, and other human services.

**ECOS:** The JAI Software’s Heating Assistance Program ECOS system refers to the  Energy Community Online System developed as customized or configured for administering Heating Assistance Programs, such as the federal Low Income Home Energy Assistance Program (LIHEAP) or state-specific heating/fuel assistance initiatives in jurisdictions that use JAI's platform.
This specialized instance of ECOS handles applicant eligibility screening, application processing, benefit determination, case tracking, payment issuance, and compliance reporting for heating-related public assistance, integrating data verification, workflow automation, and program rules specific to energy aid to help agencies efficiently deliver timely support to low-income households facing heating costs.

**AKCCIS:** AKCCIS stands for the Alaska Child Care Information System, a modern online database and portal launched by the State of Alaska's Child Care Program Office (CCPO) around 2025, used for child care provider licensing, facility searches, public access to provider information (via akccis.com), online applications for Child Care Assistance Program (PASS eligibility categories), document submissions, compliance reporting, and streamlining administrative processes for families, providers, and state staff to improve efficiency in Alaska's child care ecosystem.

**Spirit Web:** It serves as the primary software platform for Alaska WIC clinics to handle participant certification, eligibility determination, benefit issuance (via electronic benefits or food instruments), nutrition education tracking, vendor management, data reporting, and compliance with federal WIC regulations.

**Qualtrics:** Qualtrics is a leading cloud-based experience management (XM) platform developed by Qualtrics, LLC (an SAP subsidiary that went public and later taken private), enabling organizations to collect, analyze, and act on feedback through surveys, forms, and data from multiple channels to improve customer, employee, product, and brand experiences.

**iSight:** DPA's iSight case management platform is  an online fraud allegation reporting and case management tool used by the Alaska Department of Health's Division of Public Assistance (DPA) Fraud Control Unit to handle investigations into suspected fraud, waste, or abuse in public assistance programs such as SNAP (Food Stamps), Medicaid, ATAP, and others.

**Random Moment Study (RMS):** Tracks random moments survey for cost allocation which is needed for federal funding claims and reimbursements.

**Quality Assurance:** DPA's Case Review System refers to the internal case review and quality control process (and associated tools or modules) used by the Alaska Department of Health's Division of Public Assistance (DPA) to evaluate the accuracy, completeness, and compliance of public assistance case determinations, eligibility decisions, benefit calculations, and documentation for programs such as SNAP, Medicaid (via ARIES), ATAP, and others.

![IEP Current State](media/iep_currentstate.png)




