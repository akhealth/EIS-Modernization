# DevOps

This document is living, it will change as we learn things and sharpen our focus.

## Environment

We are working in the Microsoft universe.  We prefer:

- C# and Powershell
- WindowsServer2016 or NanoServer
- Windows10 for dev

We are using [VSTS](https://alaskadhssba.visualstudio.com) for SCM(git), CI, and CD.

## Pipeline MVP Plan

We want to create a MVP that demonstrates basic DevOps concepts and practice

1. Use an exemplar .NET core web app written in C#
2. Use VSTS/git to store the code, and change it via PullRequests
3. Use VSTS/build to build the project when code gets checked in (Continuous Integration)
    a. Run project tests
    b. Compute code coverage
    c. Run a simple TBD security scan
4. Use ARM and DSC to automate infrastructure in Azure
5. Use VSTS/build to deploy changes to Azure on successful builds (Continous Delivery)

## People Support

We must help all sorts of people feel the benefits of, and _believe_ in our DevOps mission.

1. Create short, high-level briefing/overview containing AK opportunities and distribute
2. Generate initial list of challenges/risks.  Brainstorm antidotes
3. Initive ITS stakeholders to join our sprints as team members so they can contribute to and refine risks, requirements, barriers.
4. **Road Show**: Bring our DevOps MVP to groups of stakeholders and gather feedback from shows
5. Find an effective, easy way to send out continuous status briefings to people. 
