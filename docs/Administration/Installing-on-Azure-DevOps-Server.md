Unlike if you are using Azure DevOps Service (cloud), running Azure DevOps Services on-premise currently requires us to do some manual configuration. Should the APIs to automate the way we configure @Scale in the service also come to Azure DevOps Server we will of course leverage that option and this guide will be obsolete.

# Create process config for reference or customization
We define the process configuration for Scale in a json file containing the types and fields we use. Use it as is or customize the mappings for work item types and fields. The id field is what keeps the config together so that's the one thing you should not change. The Name field is most likely what you want to change if you prefer the work item types to be named differently. The config file will be used in the final step of the configuration process.

Here's a snippet of the configuration file:
    
```json
{
  "name": "SAFe",
  "version": "1.1.0",
  "author": "Solidify",
  "process": {
    "types": [
      {
        "id": "scale-art",
        "name": "Agile Release Train",
        "description": "Agile Release Train",
        "color": "f6546a",
        "icon": "icon_government",
        "fields": [
          {
            "id": "art-teams",
            "name": "Scale_ART_Teams",
            "description": "Teams working on this ART.",
            "type": "PlainText"
          },
          {
            "id": "art-dependent-teams",
            "name": "Scale_ART_Dependent_Teams",
            "description": "Teams this ART is dependent on.",
            "type": "PlainText"
          }
        ]
      },
...
```

References:
* [Icons](https://docs.microsoft.com/en-us/azure/devops/reference/xml/process-configuration-xml-element?view=azure-devops#specify-wit-icons)
* [HTML colors](https://www.w3schools.com/colors/colors_picker.asp)
* [Latest config](https://github.com/solidify/scale/tree/master/config)

# Add custom work item types
Next we need to add the required work item types to your project.

The below PowerShell script will add all wit* definitions to the specified project:

```powershell
$witadmin = "C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\witadmin.exe"
$project = "m-200601-1"
$files = Get-ChildItem wit*.xml
foreach ($file in $files) {
    Write-Host "Importing WIT '$file'..."
    & $witadmin importwitd /collection:$UriOrg /p:"$project" /f:$file
}
```

# Make custom work item types hidden (optional)
By default all work item types are visible and can be created by the end user. If you want to hide some (or all) of the custom work item types Scale depends on you can do so by modifying the categories mapping.

## Export the current categories mapping.

`witadmin exportcategories /collection:https://your-tfs/collection /p:"some project" /f:categories.xml`

## Add the Scale work item types to the Hidden Types Category.
```xml
<CATEGORY refname="Microsoft.HiddenCategory" name="Hidden Types Category">
    <DEFAULTWORKITEMTYPE name="Code Review Request" />
    <WORKITEMTYPE name="Code Review Response" />
    <WORKITEMTYPE name="Feedback Request" />
    <WORKITEMTYPE name="Feedback Response" />
    <WORKITEMTYPE name="Shared Steps" />
    <WORKITEMTYPE name="Shared Parameter" />
    <WORKITEMTYPE name="Test Plan" />
    <WORKITEMTYPE name="Test Suite" />
    <WORKITEMTYPE name="Agile Release Train" />
    <WORKITEMTYPE name="Program Increment" />
  </CATEGORY>
</cat:CATEGORIES>
```

## Import the current categories mapping.

`witadmin importcategories /collection:https://your-tfs/collection /p:"some project" /f:categories.xml`

# Upload configuration metadata 
The final step is to make Scale aware of the configuration we've made. In order to understand which work item types and fields your specific configuration have we store that metadata in the extension's internal storage in your Azure DevOps organization. In Azure DevOps Service this is set for you in the configuration process, for Server we need to do this manually.

## Prepare the configuration
To manually set the extension configuration, we need to create a json string containing the metadata in the following format:

```json
{
"setting": "add-your-settings-here",
"id": "PROCESS-CONFIG",
"__etag": 1
}
```

where the setting string is a serialized string of your configuration process json. You can use a tool like https://tools.knowledgewalls.com/jsontostring to generate an escaped string to be stored in the extension data settings.

Note: if you stick to the configuration in the default SAFe json document then the stringified version in the provided can be used as-is.

## Post the configuration to Azure DevOps
With the configuration defined we can now post it to the extension storage service in Azure DevOps. To do so you can use the PowerShell script we share with you, providing the following:
* Organization URL.
* Personal Access Token. A user PAT with permission to read and write extension data.
* Project name.

```powershell
$AzureDevOpsPAT = "YOUR-PERSONAL-ACCESS-TOKEN"
$AzureDevOpsAuthenicationHeader = @{Authorization = 'Basic ' + [Convert]::ToBase64String([Text.Encoding]::ASCII.GetBytes(":$($AzureDevOpsPAT)")) }

$collectionName = "COLLECTION-NAME"
$documentId = "DOCUMENT-ID"
$extensionData = "SETTING-JSON" # Use Get to fetch a starting value that you want to modify
$uriApi = "https://extmgmt.dev.azure.com/YOUR-PROJECT/_apis/ExtensionManagement/InstalledExtensions/solidify/solidify-scale/Data/Scopes/Default/Current/Collections/$collectionName/Documents/$documentId?api-version=3.2-preview.1"
Invoke-RestMethod -Uri $uriApi -Method Post -Headers $AzureDevOpsAuthenicationHeader -Body $extensionData -ContentType "application/json"

```

# Purchase @Scale
After you have completed the trial, the license needs to be updated with the correct license details. For an online license we will update this for you, for offline the license key needs to be uploaded again.
