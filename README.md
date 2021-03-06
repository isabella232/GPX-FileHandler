[ARCHIVED] GPX-FileHandler
===============

**Note:** This repo is archived and no longer actively maintained. Security vulnerabilities may exist in the project, or its dependencies. If you plan to reuse or run any code from this repo, be sure to perform appropriate security checks on the code or dependencies first. Do not use this project as the starting point of a production Office Add-in. Always start your production code by using the Office/SharePoint development workload in Visual Studio, or the [Yeoman generator for Office Add-ins](https://github.com/OfficeDev/generator-office), and follow security best practices as you develop the add-in.

This is a version of [a O365 multi-tenant webapp](https://github.com/OfficeDev/O365-WebApp-MultiTenant) modified to work as a File Handler extension for GPX files.

This application requires SharePoint Online's "Read users' files" and "Edit or delete users' files" permissions to operate properly.

To run this on your machine after cloning:

1. Open the project in Visual Studio 2013. You must have the most recent version of the update (the October VSIX) in order for the app to function properly.
2. In the web.config & manifest.json, replace the app client ID and secret placeholder values.
3. Right Click -> Publish the app to the web.
4. Call the CallO365SharePointRest.ps1 PowerShell file to install your app using the File Handler install APIs:

```
Add-Type -Path "C:\Program Files\Common Files\microsoft shared\Web Server Extensions\15\ISAPI\Microsoft.SharePoint.Client.dll" 
Add-Type -Path "C:\Program Files\Common Files\microsoft shared\Web Server Extensions\15\ISAPI\Microsoft.SharePoint.Client.Runtime.dll"
./CallO365SharePointRest.ps1 -API "https://[tenant].sharepoint.com/_api/apps/" -Username [admin email] -HTTPVerb POST -BodyFile ".\MVCO365DemoMT\install_manifest.json" 
```




This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
