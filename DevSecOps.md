# DevSecOps

We [spiked](https://en.wikipedia.org/wiki/Spike_(software_development)) on a number of approaches to Cloud and DevOps, our learnings are in the [DevSecOpsMVP](https://github.com/AlaskaDHSS/DevSecOpsMvp) repository. 
Here are a couple documents from that repo that provide a good overview of our approach and our work so far.

- [README.md](https://github.com/AlaskaDHSS/DevSecOpsMvp/blob/master/README.md)
- [DevSecOps.md](https://github.com/AlaskaDHSS/DevSecOpsMvp/blob/master/DevSecOps.md)

## Environment

We are targeting

- [Microsoft C#](https://docs.microsoft.com/en-us/dotnet/csharp/) for application language
- [Microsoft Dotnet Core](https://www.microsoft.com/net/core) for application framework
- [Microsoft Azure App Service](https://azure.microsoft.com/en-us/services/app-service/) Platform-as-a-Service for application environments
- Utilizing the State of Alaska's existing Enterprise Service Bus (ESB) for accessing on-premises data sources.

We prefer development environments to be virtualized using something like [Docker](https://www.docker.com/). See the [running-locally section of our prototype README](https://github.com/AlaskaDHSS/ProtoWebApi#running-locally) for more information.

## CI/CD Pipeline

We use
- [Visual Studio Team Services(VSTS)](https://alaskadhssba.visualstudio.com) for Source Code Management, Continuous Integration, and Continuous Deployment
- [Git](https://git-scm.com/) for source control

More info about our current VSTS setup is in the [DevSecOpsMVP repo vsts folder](https://github.com/AlaskaDHSS/DevSecOpsMvp/tree/master/vsts).  

## Culture 

We are
- Continuously learning
- Committed to an automated DevSecOps approach to this work
