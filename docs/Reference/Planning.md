The planning hub is where we define how teams work together to deliver value. We also associate the ART with the program increments (PI) they work on. Program increments are defined using Azure DevOps iterations and ARTs can share PIs to align or have their on if they are on different cadences.

# Setting up an Agile Release Train (ART)

The Planning view shows all ARTs and PIs. The PIs assigned to an ART (2) is listed with details of the increment period and associated teams. You can navigate to the program board for a PI by clicking on the PI title (1). You can also navigate to the settings for a team by clicking on the team icon (2). Use the context menus on the ARTs and PIs (4) to show the available commands.

![image.png](/docs/.attachments/image-94b41067-9fd8-4fad-ba95-5813d50dcd33.png)

To setup a new ART you use the New ART button (3). In the Create ART dialog you name the ART, assign the teams belonging to the ART and you can also associate the teams this ART depends on. The ART is stored as a work item in Azure DevOps which can be used to query for SAFe related information outside of @Scale.

![image.png](/docs/.attachments/image-72aad0b9-894e-4575-92e3-47c64c217902.png)

## ART commands

Clicking the action menu (...) for an ART shows the available commands for the item.

![image.png](/docs/.attachments/image-3ad8e99e-3354-40e1-983c-3365da786671.png)

| **Command** | **Function** |
|---|---|
| Add new PI to ART | [Create a new PI and associate to the ART](#create-a-new-pi-and-associate-to-an-art) |
| Add existing PI to ART | [Associate an existing PI to the ART](#associate-an-existing-pi-to-an-art) |
| Edit ART | Edit the ART definition if you want to change the name or associated teams |
| Set ART team order | [Configure the order of the teams for an ART](#configure-the-order-of-the-teams-for-an-art) |
| Delete ART | Delete the selected ART. The ART work item is deleted but can be restored like other work items from the [Recycle bin](https://docs.microsoft.com/en-us/azure/devops/boards/backlogs/remove-delete-work-items?view=azure-devops#restore-or-destroy-work-items) |

### Create a new PI and associate to an ART

In the New Program Increment dialog you define a program increment for the ART. The PI is implemented as a work item that has the iteration path set to the created PI iteration tree. 

![image.png](/docs/.attachments/image-044edb7b-cc35-4fcf-9a16-a3e1ae3a4038.png)

First select the iteration you want the new PI to have as its root. Then give it a name and description, the start date for the increment, sprint length (working days) and number of sprints.

**Note:** if a PI already exists for the selected parent iteration you will see a validation error. Choose a different name or use the Add existing program increment command if you intended to align to an existing PI. 

@Scale creates an iteration tree for you with the dates set based on the values in the ART creation dialog. You can later change dates or name of the iterations (like for Sprint 5 in the illustration), @Scale will show the values from the Azure DevOps definition.

![image.png](/docs/.attachments/image-d7bc3027-cfe4-4de7-8e08-ebd0b5fb2956.png)

### Associate an existing PI to an ART

If you already have PIs created or create a new ART and want to align it to existing PIs then you use the Add existing program increment dialog. It works similar as the add new PI dialog with the difference that you can only set the description for the PI to be unique for the ART, the rest is controlled by the Azure DevOps iteration definition.

![image.png](/docs/.attachments/image-48195cbf-0ccd-480e-bf6a-f28a439340ed.png)

### Configure the order of the teams for an ART

The Set ART team order lets you set the display order to list teams in the program board. Drag and drop to move the order in the dialog to what makes sense for you.

![image.png](/docs/.attachments/image-ca5b612b-0dec-4c8a-a664-11ebfde7bcc3.png)

## PI commands

Clicking the action menu (...) for a PI shows the available commands for the item.

![image.png](/docs/.attachments/image-dd7d8bd9-652b-44ea-ab40-a682e3ff0a90.png)

| **Command** | **Function** |
|---|---|
| Delete PI | Delete the selected program increment. The PI work item is deleted but can be restored like other work items from the [Recycle bin](https://docs.microsoft.com/en-us/azure/devops/boards/backlogs/remove-delete-work-items?view=azure-devops#restore-or-destroy-work-items) |

# Planning view controls

| **Control** | **Function** |
|---|---|
| ![image.png](/docs/.attachments/image-58e02360-f706-4d54-b513-c95394e04ee9.png) | Refresh content on page |
| ![image.png](/docs/.attachments/image-4d4aeaa2-efb7-4e21-9cfc-854e997d03ce.png) | Settings: [Sprints](#sprints-configuration) |
| ![image.png](/docs/.attachments/image-9e9e362c-248f-49d9-a2b2-03962629a97c.png) | Enter or exit full screen mode |

## Sprints configuration

The Sprints configuration allows you to set the default values for your project.

* Sprint length: number of work days per sprint.
* Number of sprints: number of sprints per program increment.

![image.png](/docs/.attachments/image-01e1ba4f-9fda-41db-8512-ed3af22ce27a.png)

