In @Scale permissions are controlled by application roles in combination with the Azure DevOps license and permissions assignments. This means that a user can get limited functionality in @Scale if they have the correct role but lacks the underlying access rights, for example a stakeholder user will typically not be able to create areas or iterations.

# @Scale roles

The application roles in @Scale are defined in the table below.

|Role|Purpose|
|---|---|
|Subscription owner | Responsible for the extension subscription, manages licenses. This role is assigned to the person creating the subscription and cannot be assigned to more than one person. |
|Extension admin | Responsible for configuring the Azure DevOps project for the extension. |
|Project admin | Responsible for managing Scale settings. |
|Contributor | General user of the extension. |

# Permission matrix

The table below shows the relationship between the Scale role assignments and Azure DevOps license and access rights.

|@Scale permission | @Scale role | Azure DevOps license | Azure DevOps permission|
|---|---|---|---|
| Create subscription| N/A | Stakeholder | Contributor |
| Manage subscription| Subscription owner | Stakeholder | Organization admin |
| Manage licenses| Subscription owner/Administrator role | Stakeholder | Organization admin |
| Configure projects| Extension admin | Basic | Project admin with permission to customize the projects' process definition |
| Create ART | Project admin | Basic | Contributor |
| Create PI | Project admin | Basic | Project admin or user with permission to manage areas and iterations |
| Configure settings | Project admin | Stakeholder | Contributor |
| Use extension | Contributor | Stakeholder | Contributor |

# Permissions

## Create subscription
When creating a subscription is created (trial or paid) we present the name and email of the current user. The user can then change this information to someone else. This user will be the owner of the subscription. 

Only the subscription owner and an organization admin can change the subscription owner (or us on the backend in Stripe).

## Manage subscription
A subscription owner can from the admin view change the subscription owner to someone else. The subscription owner can also change or cancel the subscription.

## Manage licenses
The permission to manage licenses included adding and removing users and assigning access request from users.

## Configure projects
This permission gives the user the ability to customize the work item process for an Azure DevOps project.

## Create ART
The permission to create, edit and delete the release trains.

## Create Program Increment
The permission to creating, edit and delete program increments.

## Configure settings
With this permission the user can change settings for at the project level.

## Use extension
General use of the features in the extension such as creating objectives and working with the board and reports.
