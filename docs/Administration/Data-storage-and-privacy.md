# Azure DevOps Data

All data created by the @Scale extension is stored in the form of work items, meaning that the extension does not store any data outside of the installation of the Azure DevOps except for telemetry. 

All data created by the extension that could be considered additional or data created by the extension is also stored in the scope of the organization. 

Apart from helping you manage data in backlog we also add additional work item types (such as objectives and risks) to your process as described in [Customization]() secton.

See the [@Scale - Privacy Policy](https://marketplace.visualstudio.com/items/solidify.solidify-scale/privacy) for more details.

Data generated by the extension is therefore protected under data protection in Azure DevOps. See Microsoft's Documentation on Data Protection in [Azure DevOps](https://docs.microsoft.com/en-us/azure/devops/organizations/security/data-protection?view=azure-devops) for information on how data is secured in Azure DevOps.

# Settings

@Scale uses Azure DevOps extension storage to store its configuration. 

The table below describes the different settings stored in the extension. The scope can be per organization, per project or per user. 

| Document | Collection name | Document id | Scope | Description |
|--|--|--|--|--|
|Process config| PROCESS-CONFIG-<project id> |PROCESS-CONFIG| Project| Project process configuration |
|Selected PI| SELECTED-PI-<project name> |SELECTED_PI| User| User's last selected PI |
|Settings| SETTINGS-<project name> |BOARD_SETTINGS| Project | Board settings for project |
|Settings| SETTINGS-<project name> |PLANNING_SETTINGS| Project | Planning settings for project |
|Subscription| subscription | subInfo| Project | Account subscription and license info |

All Settings are stored within the organization and are therefore covered under general Data Protection policies from Microsoft. 

# Personal Identifiable Information (PII)

Information about users are only stored in the Azure DevOps tenant the extension is installed. 

# Subscription

We store the following information related to a subscription:

* Organization name
* Subscription owner name and email

Apart from the above our payment provider Stripe also saves credit card information for recurring payments.
