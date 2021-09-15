# Summary
The purpose of our prototyping was to get a deeper understanding of how the parts of the existing ARIES system function to be updated as a part of Automated Renewals work. Given the complexity of the system a full scale prototype was not possible given certain constraints. Instead we chose to present a handful of illustrative prototypes on the parts of ARIES we think will need to be updated as a part of developing Automated renewals. These include the WebSphere Application Server, WebSphere Operational Decision Manager, Mule Community Edition, HP Exstream (a.k.a OpenText) and Quartz Scheduler.

## Components
- DHSS controlled systems
- 
- **ARIES Worker Portal** -We created a page in JAVA

- **MULE** - We created a sample service using Mulesoft's Anypoint Studio IDE and the Mule 3.9 CE runtime. The service mimics the ARIES Mule services as much as possible, which were created using Mule 3.3.1 CE (which is not available through Mulesoft any longer). The flow of data through the service is as follows: 
SOAP Request -> HTTP Listener -> Proxy Service (CXF) -> Proxy Client (CXF) -> HTTP Requester -> CMS Hub Endpoint.
The proxy service is configured with the CMS Hub Endpoint's WSDL and the HTTP Request is configured to use both a Trust Store and Key Store, TLSv1.2 protocol, and TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 Cipher Suite for authentication with CMS. Additionally, the original SOAP request to the service must include a Username/Password in Digest Format along with a Timestamp.

- **Opentext/HP Extreme** - We shadowed our M&O team who made updates to existing notices to address defects. The process required updates

- **IBM WebSphere Operational Decision Manager (WODM)** - We created a rule flow based on a simple Java Class to create a BOM/XOM that was deployed to a test Rules Execution Server. We were able to call the rule to validate results was done using SOAP UI using the WSDL generated when BOM/XOM was created.

- **Batch** - 

- DevOps pipeline info and work management

- External Services

- CMS HUB – For the prototype we connected to two different CMS Hub services - the Hub Connectivity Service and the Verify Current Income Service. The Hub Connectivity Service returns a 'Success' message if a connection is created and authentication is validated. The Verify Current Income Service...

- IEVS – 

## Key findings

**Notices** - Updating existing, or creation, of new notice templates requires using HP Exstream (supported by OpenText) tools for creation or updates of notices. If new data is needed to be presented to the forms this may require doing complementary updates to code for the WebSphere applications, Quartz batch jobs and WebSphere Rules server. The biggest limitation we have hit so far are the fact we are running older versions of software which makes getting support challenging. In addition, for formal development, the processes for developing and deploying these components are still being put into place.

## Remaining risks

## Relevant resources
- How we work
- Code review
- Pipeline
- Container info
- SOAP Projects for CMS Hub Connectivity and VerifyCurrentIncome testing

## Remaining questions/considerations
Batch

## Don’t forget about
- Security
- Federal requirements
- 508

## Appendix items 

- CMS data hub def – what we can
- Container stuff that might be useful
- Diagrams for data flow and process
   - [Renewal Process Diagram](/Automated-Renewals/Prototype-Findings/Renewal-Process-Diagram)
     
