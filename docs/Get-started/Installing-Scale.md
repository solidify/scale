@Scale is designed to be simple to add to your existing project. We require a subscription to manage access to the extension and we also customize your Azure DevOps process to improve the support for agile at scale. It may sounds like a lot but as you will see we take care of most of the work for you.

# Installing @Scale 

Follow the steps below to get @Scale up and running in your project:

1. Install [@Scale from the Azure DevOps marketplace](https://marketplace.visualstudio.com/items?itemName=solidify.solidify-scale). Installing @Scale requires project collection administrator or organization owner permissions. If you don't have permissions you can request the extension to be installed, and your administrator will be notified of your request.

   @Scale uses the following permissions:

   1. Graph (read). Read user and team metadata, read group membership.
   1. Project and team (read and write). Read project and team info.
   1. Work items (read and write). Read and update work items, manage iterations.

1. [Create a subscription](/docs/Administration/Subscription-management.md). Any user can create a subscription and will then become the owner of it.
1. [Assign licenses](/docs/Administration/Manage-licenses.md) to users of @Scale. 
1. [Configure](/docs/Administration/Configuration-and-customization.md) your project. @Scale requires certain elements in your planning process in order to function. As part of the setup we will add missing configuration to your project, where needed. **Note:** If you are using an on-premises Azure DevOps Server you need to contact us at scale@solidify.dev to get instructions how to configure the project manually.

# Related articles
* [Install Azure DevOps extensions](https://docs.microsoft.com/en-us/azure/devops/marketplace/install-extension)
* [Azure DevOps extension scopes](https://docs.microsoft.com/en-us/azure/devops/extend/develop/manifest?view=azure-devops#scopes)
* [@Scale permissions](/docs/Administration/Permissions.md)
