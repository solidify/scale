# Creating "Dependency Request" Work Item Type in Azure DevOps (XML Process Model)

This process can be technical, so please ask your Azure DevOps Administrators to configure this for you if you are unfamiliar with it.

To create a "Dependency Request" work item type in Azure DevOps using the XML process model, follow these steps:

## Step 1: Define the Work Item Type

Create a new XML file for the "Dependency Request" work item type. Name it `DependencyRequest.xml`.

Here is a simple example, but you might need to adjust it for organization-specific fields. Consult with your Azure DevOps administrator.

```xml
<?xml version="1.0" encoding="utf-8"?>
<WORKITEMTYPE name="Dependency Request">
  <DESCRIPTION>Tracks dependency requests between teams.</DESCRIPTION>
  <FIELDS>
    <FIELD name="Title" refname="System.Title" type="String" />
    <FIELD name="State" refname="System.State" type="String" />
    <FIELD name="Reason" refname="System.Reason" type="String" />
    <FIELD name="Assigned To" refname="System.AssignedTo" type="String" />
    <FIELD name="Description" refname="System.Description" type="HTML" />
  </FIELDS>
  <STATES>
    <STATE value="Pending">
      <CATEGORY value="Proposed" />
      <COLOR value="b2b2b2" />
    </STATE>
    <STATE value="Accepted">
      <CATEGORY value="Completed" />
      <COLOR value="339933" />
    </STATE>
    <STATE value="Declined">
      <CATEGORY value="Removed" />
      <COLOR value="e60017" />
    </STATE>
  </STATES>
  <TRANSITIONS>
    <TRANSITION from="Pending" to="Accepted">
      <REASONS>
        <DEFAULTREASON value="Accepted" />
      </REASONS>
    </TRANSITION>
    <TRANSITION from="Pending" to="Declined">
      <REASONS>
        <DEFAULTREASON value="Declined" />
      </REASONS>
    </TRANSITION>
  </TRANSITIONS>
  <FORM>
    <Layout>
      <Page Label="Details">
        <Section>
          <Control FieldName="System.Title" Type="FieldControl" />
          <Control FieldName="System.State" Type="FieldControl" />
          <Control FieldName="System.AssignedTo" Type="FieldControl" />
          <Control FieldName="System.Description" Type="HtmlFieldControl" />
        </Section>
      </Page>
    </Layout>
  </FORM>
</WORKITEMTYPE>
```


## Step 2: Update Your Current Process Template

Modify your current process template XML to include the "Dependency Request" work item type.

## Step 3: Configure the Dependency Hub in @Scale

1. Go to the new menu option **Dependencies**.
2. Click on **Choose work item type**.
3. Select the newly created **Dependency Request** item.

## Step 4: Verify the Work Item Type

1. Go to the **Dependency Hub** in @Scale.
2. Create a new **Dependency Request** in the view.
3. Ensure the states (Pending, Accepted, Declined) and transitions work as expected.

That's it! You've successfully created a "Dependency Request" work item type in Azure DevOps using the XML process model and configured it in the Dependency Hub in @Scale.
