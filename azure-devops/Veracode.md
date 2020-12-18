# Veracode Azure DevOps Integration

See [Instructions for the Azure DevOps Veracode plugin](https://marketplace.visualstudio.com/items?itemName=Veracode.veracode-vsts-build-extension&targetId=3a6fdb87-28e4-40c1-95d9-87028e93af8f) for information used to create the following procedure.  You will need to do the following to integrate Azure DevOps and Veracode:

## Veracode portal configuration

**Option1:** Setup using Veracode generated API Credentials and Secret key

1. Obtain a valid Veracode login with access to the State of Alaska portal and the EISR application
2. Login to [Veracode portal](https://analysiscenter.veracode.com)
3. Hover over the "State of Alaska" dropdown link - a menu drops down
4. Click on "API Credentials" menu item - the _API Credentials_ page loads
5. Click on "Generate API Credentials, this will create an API ID and Secret Key
6. Copy and store these credentials in a secure place (after creation you can revoke the credentials, but cannot access them)
7. Go to the target application in Veracode and ensure a Sandbox is setup associated with the API credentials.


**Option2:** Setup using Veracode API Account
Veracode portal using Veracode API account

1. Obtain a Veracode API Account username and password information with access to the State of Alaska portal and the EISR application. The account should have the following roles set.
  a. Mitigation API
  b. Upload API
  c. Upload API - Submit Only
  d. Results API
2. Go to the target application in Veracode and ensure a Sandbox is setup associated with the API credentials.

Note: At this time we are choosing option 2. The endpoint can be used agains multiple branches (i.e. staging and production)

## Azure DevOps Veracode plugin configuration

1. Add the "Upload and scan" Veracode plugin task to the Azure DevOps build definition
2. In the Upload and scan Veracode Azure DevOps build plugin task, select the _Endpoint_ connection source from the _Select Connection Source_ radio button options
3. If there is a Veracode endpoint defined in the _Select Endpoint_ droplist select it and skip to step (9), otherwise click the _+_ symbol to the right of the _Select Endpoint_ field
4. Choose the _Veracode Endpoint_ radio button
5. Name the endpoint
6. Paste the Veracode API ID obtained in step 4 of Veracode configuration into the _ID_ field
7. Paste the Veracode API Secret Key obtained in step 4 of Veracode configuration into the _key_ field
8. Click _OK_ and make sure the Veracode endpoint is selected in the _Select Endpoint_ droplist
9. Create a build definition variable called Veracode.AppName, e.g., "ARIES-WP" as the value (note: this ties the code scan to the licensed app in Veracode, in these instructions the example "ARIES-WP" ties to the Aries worker portal license.  Work with the DHSS Veracode administrator if setting up for scan of something besides the ARIES worker portal.)
10. In the Upload and scan Veracode Azure DevOps build plugin task, enter _$(Veracode.AppName)_ into the _Application Name_ field
11. Expand _Advanced Scan Settings_ and enter the name of the Veracode Sandbox
12. Enable the Upload and scan Veracode Azure DevOps build plugin task
13. Click the _Save & queue_ button to save the build definition and queue a build to test the task

If this is the first time you are submitting a scan for the particular app/sandbox you will need to do the following after the build started in step 13 has finished uploading binaries to Veracode.

1. Login to [Veracode portal](https://analysiscenter.veracode.com)
2. Click on Application
3. Click on the link for the build started in step 13 in the previous section.
4. Hit refresh until the status states "Select Modules to be scanned".
5. Scroll down through the list of binaries and validate the modules you want scanned are selected.
6. Click on the "Scan" button at the bottom of the page to start the scan.

## Troubleshooting

### No files found

If Azure DevOps build reports the build artifacts were not found, ensure there is a publish step that moves the build artifacts to the Build.ArtifactStagingDirectory

### Veracode upload and scan task timeout

Azure DevOps build tasks timeout by default after 60 minutes of waiting for the scan to complete.  There are three scenarios we have seen with these timeouts:

1. Scan actually took longer than 60 minutes
2. Scan got stuck and needs action on the Veracode portal
3. Something else went wrong and file upload failed in-progress

We diagnose and resolve all scenarios in the Veracode portal.

### Scan took longer than 60 minutes

Sandbox scans are appropriately used for scanning of pre-production (dev, test) code, but Veracode gives sandboxes lower priority in resource scans.  This appears to mean that sometimes a sandbox scan will pause inexplicably.  This is rare, but it does happen.  When this occurs you can see in the Veracode portal that the scan is in progress and there are no errors or prompts, or you see that the scan completed.  _Note that in this case, the scan does (eventually) finish without intervention and subsequent builds will be able to scan, i.e., no additional intervention is required to avoid breaking the build.

### Scan got stuck

Sometimes we have seen scans get stuck when they use the "Previous Selection" for the modules file selection.  This selection is found in the sandbox:

1. Click _{ScanID}_
2. Click _Review Modules_
3. Click _Simple Mode_ tab
4. Within the _Uploaded Modules_ _Scan Details_ section review the _File Selection_

When this scenario occurs, _File Selection_ will be "Previous Selection".  Change the value in _File Selection_ to "Veracode Default", then click the _Start Scan_ button (will become enabled after _File Selection_ change).  This will start the scan and it typically completes within a reasonably short time frame.

### Something else went wrong

Once or twice we have seen a scan get stuck where the file upload failed in progress.  In this case, the only option is to delete the scan and re-queue the build in Azure DevOps.

### Veracode account does not have correct privileges

The Veracode API account needs to have the appropriate privileges. For our endpoint we need ensure the account have the following user roles:

1. Mitigation API
2. Upload API
3. Upload API - Submit Only
4. Results API

### Build Failed :  Exit From Scan Inspection Process, Cannot Find New Scan Build ID

This error happens when multiple builds are queued on the same Veracode Sandbox. Azure DevOps build logs should also contain the following text, though it it not called out as an error:

```
* Action "UploadAndScan" returned the following message:
* App not in state where new builds are allowed.
* A scan is in progress or has failed to complete successfully. Wait for the current scan to complete or delete the failed scan from the Veracode Platform and try again.
```

#### Final notes about scan timeouts

Note that whenever a scan is stuck, Veracode will not allow further scans within that sandbox.  The problem must be resolved in the Veracode portal before Azure DevOps builds queued that target that Veracode sandbox will succeed.  Until then the stuck scan results in breaking the build.
