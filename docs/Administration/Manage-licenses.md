The @Scale extension is a licensed product and not sold. The license format is a subscription license where the Licensee can add and remove users based on needs. When a user gets added into the license pool a deduction will be made from the available number of licenses in the subscription.

@Scale licenses are separate from Azure DevOps licenses, where the purpose of the @Scale license is to control who gets access to the extension and in what role. See [Permissions](/docs/Administration/Permissions.md) for details on how the model works.

# Request license

When Scale is loaded and has a valid subscription it checks if the user has a license. If the user does not have a license a screen is presented where the user can request a license. The request is then approved and a role assigned by the subscription owner or an Azure DevOps administrator.


![image](https://user-images.githubusercontent.com/83336871/196707947-33b8e504-d355-486e-b235-eb96c615dd70.png)

![image](https://user-images.githubusercontent.com/83336871/196708201-79b0a3bc-2af7-4a31-afc1-a2362d2be8a6.png)

# Manage licenses

The subscription owner or an Azure DevOps administrator can manage users and assign roles. You manage the licenses from the @Scale admin application.

Direct URL: https://dev.azure.com/<your-organization>/_settings/solidify.solidify-scale.subscription-admin

1. Go to the Azure DevOps organization settings
2. Click @Scale in the Extensions section (very bottom of the list)
  
## Add License Administrator
If you don't want a user to have the Azure DevOps administrator but still be able to control licenses you can add a user as a license administrator. This role does not grant access to @Scale but lets that user manage access to @Scale.
  
To assign a license administrator. Click on the Administrator tab and assign and click on add users.
![image](https://user-images.githubusercontent.com/83336871/196709684-2304a785-ce14-48d3-9d5b-8fe6deef0bd4.png)


## Add license

To assign a license and role just click on the Add users button. 

  ![image.png](/docs/.attachments/image-691e51c4-facb-4211-bd85-a3d8222eae0c.png)

Next add users by searching the users directory and select the user should ne assigned to.

  ![image.png](/docs/.attachments/image-df01a0ba-ac88-4cee-8025-c175e4e3adeb.png)

## Assign license request

If users have requested a license the number of requests shows as a tile on the add users button.

  ![image.png](/docs/.attachments/image-bdc6f3dc-15aa-4e24-9f18-c0ce641fd15f.png)

In the add users dialog there is now a pending requests section where the requesting users are shown. Select each user and assign a role from the context menu.

  ![image.png](/docs/.attachments/image-f9b145c5-b48e-412d-8068-101d4d6a96fc.png)

## Remove license

From the list of users you can select a user and from the context menu choose to remove the user.

  ![image.png](/docs/.attachments/image-8ec1ff7c-1d98-45a3-b2fb-8cc3f478f4b9.png)

