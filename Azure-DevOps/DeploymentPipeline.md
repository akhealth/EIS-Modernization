# Create an Azure DevOps CI Pipepline

## Sign into Azure DevOps
1. Obtain a valid Azure DevOps login with access to the Alaska DHSS portal 
2. Navigate to the [DHSS Azure DevOps Portal](https://alaskadhss.visualstudio.com/Dpa)
3. Enter credentials to sign-in

## Create ASP .Net Application
1. Navigate to Build/release
2. Click +New
3. Search for ASP.NET Core and click "Apply" <br>
	Name: (e.g. Dpa-Eisr-UnifiedSearch Production) <br>
	Agent Queue: (e.g. "Hosted VS2017")
4. Click "Get sources" in the task pane
5. Select "This Project" for "From" section.
6. Select (e.g. "Dpa-Eisr-UnifiedSearch") for "Repository"
7. Select "Master" for "Branch"
8. Select "False" for "Clean" 
9. Click on "Restore" and change version to "2.* (preview)"
10. Click on "Build" and change version to "2.* (preview)"
11. Click on Test and change version to "2.* (preview)"
12. Click on Publish and change version to "2.* (preview)"
13. Click on "Triggers"
14. Click on "Enable Continuous integration" to enable
15. Click "Save"
15. Leave "Select Folder" to "\" which is the root
16. Click "Save"

### Add specific build steps

Add these  build steps before the "Publish" steps

1. Add "Node Tool Installer" step and match the version specified by the code,
2. Add "PowerShell" step to execute client-side build script included in the codebase

>Note: At this point you can click "Queue" to kick off a build to test to see if things have been setup correctly.

### Create Release Definition with CI enabled

1. Click on "Releases"
2. Click "+" and Select "Create release definition"
3. Select "Azure App Service Deployment" template and click Apply
4. Click "+ Add" in the Artifact box
5. Select "Build" for "Source Type"
6. Select (e.g. "Dpa-Eisr-UnifiedSearch Staging")
7. Click "Add"
8. Click on Lighting Bolt icon in "Artifacts"
9. Click toggle to "Enabled" to enable Continuous deployment trigger
10. Add a "Build branch filter", either "staging" or "master". This prevents CI builds on PRs from triggering Releases

### Point CI pipeline to publish to Azure Gov
1. Click "1 phase, 1 task" under "Environments"
2. Type in “Web” for "Environment name"
3. Select "DHSS Azure Government" for "Azure subscription"
4. Select (e.g. "DPAEisrUnifiedSearch") for "App service name"
5. Click “Deploy Azure AppService” release step
6. Check “Deploy to Slot”
7. Select “ResourceGroup” (e.g. “DPAEisrUnifiedSearch”)
8. Select “Slot” “Staging”
9. Under “Package or folder” click … and select Web.zip as the package to deploy.
10. Add an Environment and repeat the previous block of steps for the “Api” project/environment.
11. Click "Pipeline" to view Artifacts and Environments settings
12. Click "Save" button on the top right hand side of the screen
13. Click "Pipeline" to view Artifacts and Environments settings
14. Click "Save" button on the top right hand side of the screen

***Add Veracode***
- Click [HERE](Veracode.md) to view Veracode setup documentation
