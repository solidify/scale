# Creating "Dependency Request" Work Item Type in Azure DevOps (XML Process Model)

This process can be technical, so please ask your Azure DevOps Administrators to configure this for you if you are unfamiliar with it.

To create a "Dependency Request" work item type in Azure DevOps using the XML process model, follow these steps:

## Step 1: Define the Work Item Type

Create a new XML file for the "Dependency Request" work item type. Name it `DependencyRequest.xml`.

Here is a simple example, but you might need to adjust it for organization-specific fields. Consult with your Azure DevOps administrator.

```xml
<?xml version="1.0" encoding="utf-8"?>
<witd:WITD application="Work item type editor" version="1.0"
  xmlns:witd="http://schemas.microsoft.com/VisualStudio/2008/workitemtracking/typedef">
  <WORKITEMTYPE name="Dependency Request">
    <DESCRIPTION>scale-dependency-request</DESCRIPTION>
    <FIELDS>
      <FIELD name="Iteration Path" refname="System.IterationPath" type="TreePath"
        reportable="dimension">
        <HELPTEXT>The iteration within which this task will be completed</HELPTEXT>
      </FIELD>
      <FIELD name="Iteration ID" refname="System.IterationId" type="Integer" />
      <FIELD name="External Link Count" refname="System.ExternalLinkCount" type="Integer" />
      <FIELD name="Team Project" refname="System.TeamProject" type="String" reportable="dimension" />
      <FIELD name="Remote Link Count" refname="System.RemoteLinkCount" type="Integer" />
      <FIELD name="Comment Count" refname="System.CommentCount" type="Integer" />
      <FIELD name="Hyperlink Count" refname="System.HyperLinkCount" type="Integer" />
      <FIELD name="Attached File Count" refname="System.AttachedFileCount" type="Integer" />
      <FIELD name="Node Name" refname="System.NodeName" type="String" />
      <FIELD name="Area Path" refname="System.AreaPath" type="TreePath" reportable="dimension">
        <HELPTEXT>The area of the product to which this task contributes</HELPTEXT>
      </FIELD>
      <FIELD name="Revised Date" refname="System.RevisedDate" type="DateTime" reportable="detail" />
      <FIELD name="Changed Date" refname="System.ChangedDate" type="DateTime" reportable="dimension" />
      <FIELD name="ID" refname="System.Id" type="Integer" reportable="dimension" />
      <FIELD name="Area ID" refname="System.AreaId" type="Integer" />
      <FIELD name="Authorized As" refname="System.AuthorizedAs" type="String" syncnamechanges="true" />
      <FIELD name="Title" refname="System.Title" type="String" reportable="dimension">
        <HELPTEXT>Work required and how this will implement a User Story</HELPTEXT>
        <REQUIRED />
      </FIELD>
      <FIELD name="State" refname="System.State" type="String" reportable="dimension">
        <HELPTEXT>New = New work not yet activated; Active = work remains to be done; Closed =
          tested and checked in.</HELPTEXT>
      </FIELD>
      <FIELD name="Authorized Date" refname="System.AuthorizedDate" type="DateTime" />
      <FIELD name="Watermark" refname="System.Watermark" type="Integer" />
      <FIELD name="Rev" refname="System.Rev" type="Integer" reportable="dimension" />
      <FIELD name="Changed By" refname="System.ChangedBy" type="String" syncnamechanges="true"
        reportable="dimension">
        <ALLOWEXISTINGVALUE />
        <VALIDUSER />
      </FIELD>
      <FIELD name="Reason" refname="System.Reason" type="String" reportable="dimension">
        <HELPTEXT>The reason why the task is in its current state</HELPTEXT>
      </FIELD>
      <FIELD name="Assigned To" refname="System.AssignedTo" type="String" syncnamechanges="true"
        reportable="dimension">
        <HELPTEXT>The person currently working on this task</HELPTEXT>
        <ALLOWEXISTINGVALUE />
        <VALIDUSER />
      </FIELD>
      <FIELD name="Work Item Type" refname="System.WorkItemType" type="String"
        reportable="dimension" />
      <FIELD name="Created Date" refname="System.CreatedDate" type="DateTime" reportable="dimension" />
      <FIELD name="Created By" refname="System.CreatedBy" type="String" syncnamechanges="true"
        reportable="dimension" />
      <FIELD name="Description" refname="System.Description" type="HTML">
        <HELPTEXT>What to do, pointers to resources and inputs, design notes, exit criteria</HELPTEXT>
      </FIELD>
      <FIELD name="History" refname="System.History" type="History">
        <HELPTEXT>Discussion thread plus automatic record of changes</HELPTEXT>
      </FIELD>
      <FIELD name="Related Link Count" refname="System.RelatedLinkCount" type="Integer" />
      <FIELD name="Tags" refname="System.Tags" type="PlainText" />
      <FIELD name="Board Column" refname="System.BoardColumn" type="String" reportable="dimension" />
      <FIELD name="Board Column Done" refname="System.BoardColumnDone" type="Boolean"
        reportable="dimension" />
      <FIELD name="Board Lane" refname="System.BoardLane" type="String" reportable="dimension" />
      <FIELD name="Remaining Work" refname="Microsoft.VSTS.Scheduling.RemainingWork" type="Double"
        reportable="measure" formula="sum">
        <HELPTEXT>An estimate of the number of units of work remaining to complete this task</HELPTEXT>
      </FIELD>
      <FIELD name="Original Estimate" refname="Microsoft.VSTS.Scheduling.OriginalEstimate"
        type="Double" reportable="measure" formula="sum">
        <HELPTEXT>Initial value for Remaining Work - set once, when work begins</HELPTEXT>
      </FIELD>
      <FIELD name="Completed Work" refname="Microsoft.VSTS.Scheduling.CompletedWork" type="Double"
        reportable="measure" formula="sum">
        <HELPTEXT>The number of units of work that have been spent on this task</HELPTEXT>
      </FIELD>
      <FIELD name="Activity" refname="Microsoft.VSTS.Common.Activity" type="String"
        reportable="dimension">
        <HELPTEXT>Type of work involved</HELPTEXT>
        <SUGGESTEDVALUES expanditems="true">
          <LISTITEM value="Deployment" />
          <LISTITEM value="Design" />
          <LISTITEM value="Development" />
          <LISTITEM value="Documentation" />
          <LISTITEM value="Requirements" />
          <LISTITEM value="Testing" />
        </SUGGESTEDVALUES>
      </FIELD>
      <FIELD name="State Change Date" refname="Microsoft.VSTS.Common.StateChangeDate"
        type="DateTime">
        <WHENNOTCHANGED field="System.State">
          <READONLY />
        </WHENNOTCHANGED>
        <WHENCHANGED field="System.State">
          <SERVERDEFAULT from="clock" />
        </WHENCHANGED>
      </FIELD>
      <FIELD name="Activated Date" refname="Microsoft.VSTS.Common.ActivatedDate" type="DateTime"
        reportable="dimension">
        <WHENNOTCHANGED field="System.State">
          <READONLY />
        </WHENNOTCHANGED>
      </FIELD>
      <FIELD name="Activated By" refname="Microsoft.VSTS.Common.ActivatedBy" type="String"
        syncnamechanges="true" reportable="dimension">
        <WHENNOTCHANGED field="System.State">
          <ALLOWEXISTINGVALUE />
          <READONLY />
        </WHENNOTCHANGED>
      </FIELD>
      <FIELD name="Closed Date" refname="Microsoft.VSTS.Common.ClosedDate" type="DateTime"
        reportable="dimension">
        <WHENNOTCHANGED field="System.State">
          <READONLY />
        </WHENNOTCHANGED>
      </FIELD>
      <FIELD name="Closed By" refname="Microsoft.VSTS.Common.ClosedBy" type="String"
        syncnamechanges="true" reportable="dimension">
        <WHENNOTCHANGED field="System.State">
          <ALLOWEXISTINGVALUE />
          <READONLY />
        </WHENNOTCHANGED>
      </FIELD>
      <FIELD name="Priority" refname="Microsoft.VSTS.Common.Priority" type="Integer"
        reportable="dimension">
        <HELPTEXT>Importance to business</HELPTEXT>
        <ALLOWEDVALUES expanditems="true">
          <LISTITEM value="1" />
          <LISTITEM value="2" />
          <LISTITEM value="3" />
          <LISTITEM value="4" />
        </ALLOWEDVALUES>
        <DEFAULT from="value" value="2" />
      </FIELD>
      <FIELD name="Stack Rank" refname="Microsoft.VSTS.Common.StackRank" type="Double"
        reportable="dimension">
        <HELPTEXT>Work first on items with lower-valued stack rank. Set in triage.</HELPTEXT>
      </FIELD>
      <FIELD name="Integration Build" refname="Microsoft.VSTS.Build.IntegrationBuild" type="String"
        reportable="dimension">
        <HELPTEXT>The build in which the bug was fixed</HELPTEXT>
        <SUGGESTEDVALUES expanditems="true">
          <LISTITEM value="&lt;None&gt;" />
        </SUGGESTEDVALUES>
      </FIELD>
      <FIELD name="Start Date" refname="Microsoft.VSTS.Scheduling.StartDate" type="DateTime"
        reportable="dimension">
        <HELPTEXT>The date to start the task</HELPTEXT>
      </FIELD>
      <FIELD name="Finish Date" refname="Microsoft.VSTS.Scheduling.FinishDate" type="DateTime"
        reportable="dimension">
        <HELPTEXT>The date to finish the task</HELPTEXT>
      </FIELD>
    </FIELDS>
    <WORKFLOW>
      <STATES>
        <STATE value="New">
          <FIELDS>
            <FIELD refname="Microsoft.VSTS.Common.ActivatedDate">
              <EMPTY />
            </FIELD>
            <FIELD refname="Microsoft.VSTS.Common.ActivatedBy">
              <ALLOWEXISTINGVALUE />
              <EMPTY />
            </FIELD>
            <FIELD refname="Microsoft.VSTS.Common.ClosedDate">
              <EMPTY />
            </FIELD>
            <FIELD refname="Microsoft.VSTS.Common.ClosedBy">
              <ALLOWEXISTINGVALUE />
              <EMPTY />
            </FIELD>
          </FIELDS>
        </STATE>

        <STATE value="Done">
          <FIELDS>
            <FIELD refname="Microsoft.VSTS.Scheduling.RemainingWork">
              <EMPTY />
            </FIELD>
            <FIELD refname="Microsoft.VSTS.Common.ClosedDate">
              <SERVERDEFAULT from="clock" />
              <REQUIRED />
            </FIELD>
          </FIELDS>
        </STATE>


        <STATE value="Removed">
          <FIELDS>
            <FIELD refname="Microsoft.VSTS.Scheduling.RemainingWork">
              <EMPTY />
            </FIELD>
            <FIELD refname="Microsoft.VSTS.Common.ClosedDate">
              <SERVERDEFAULT from="clock" />
              <REQUIRED />
            </FIELD>
          </FIELDS>
        </STATE>

      </STATES>
      <TRANSITIONS>
        <TRANSITION from="" to="New">
          <REASONS>
            <DEFAULTREASON value="New" />
          </REASONS>
        </TRANSITION>
        <TRANSITION from="New" to="Done">
          <REASONS>
            <DEFAULTREASON value="Done" />
          </REASONS>
        </TRANSITION>
        <TRANSITION from="New" to="Removed">
          <REASONS>
            <DEFAULTREASON value="Removed dependency" />
          </REASONS>
        </TRANSITION>
        <TRANSITION from="Done" to="New">
          <REASONS>
            <DEFAULTREASON value="New" />
          </REASONS>
        </TRANSITION>
        <TRANSITION from="Done" to="Removed">
          <REASONS>
            <DEFAULTREASON value="Removed dependency" />
          </REASONS>
        </TRANSITION>
        <TRANSITION from="Removed" to="Done">
          <REASONS>
            <DEFAULTREASON value="Done" />
          </REASONS>
        </TRANSITION>
        <TRANSITION from="Removed" to="New">
          <REASONS>
            <DEFAULTREASON value="New" />
          </REASONS>
        </TRANSITION>
      </TRANSITIONS>

    </WORKFLOW>
    <FORM>
      <Layout HideReadOnlyEmptyFields="true" HideControlBorders="true">
        <Group Margin="(4,0,0,0)">
          <Column PercentWidth="90">
            <Control FieldName="System.Title" Type="FieldControl" ControlFontSize="large"
              EmptyText="&lt;Enter title here&gt;" />
          </Column>
          <Column PercentWidth="10">
            <Control FieldName="System.ID" Type="FieldControl" ControlFontSize="large" />
          </Column>
        </Group>
        <Group Margin="(10,0,0,0)">
          <Column PercentWidth="30">
            <Group Label="Status">
              <Column PercentWidth="100">
                <Control FieldName="System.AssignedTo" EmptyText="&lt;No one&gt;"
                  Type="FieldControl" Label="Assi&amp;gned To" LabelPosition="Left" />
                <Control FieldName="System.State" Type="FieldControl" Label="Stat&amp;e"
                  LabelPosition="Left" />
                <Control FieldName="System.Reason" Type="FieldControl" Label="Reason"
                  LabelPosition="Left" />
              </Column>
            </Group>
          </Column>
          <Column PercentWidth="30">
            <Group Label="Classification">
              <Column PercentWidth="100">
                <Control FieldName="System.AreaPath" Type="WorkItemClassificationControl"
                  Label="&amp;Area" LabelPosition="Left" />
                <Control FieldName="System.IterationPath" Type="WorkItemClassificationControl"
                  Label="Ite&amp;ration" LabelPosition="Left" />
              </Column>
            </Group>
          </Column>
          <Column PercentWidth="20">
            <Group Label="Planning">
              <Column PercentWidth="100">
                <Control FieldName="Microsoft.VSTS.Common.Priority" Type="FieldControl"
                  Label="Priority" LabelPosition="Left" />
                <Control FieldName="Microsoft.VSTS.Common.Activity" Type="FieldControl"
                  Label="Activity" LabelPosition="Left" EmptyText="&lt;None&gt;" />
              </Column>
            </Group>
          </Column>
          <Column PercentWidth="20">
            <Group Label="Effort (Hours)">
              <Column PercentWidth="100">
                <Control FieldName="Microsoft.VSTS.Scheduling.OriginalEstimate" Type="FieldControl"
                  Label="Original Estimate" LabelPosition="Left" />
                <Control FieldName="Microsoft.VSTS.Scheduling.RemainingWork" Type="FieldControl"
                  Label="Remaining" LabelPosition="Left" />
                <Control FieldName="Microsoft.VSTS.Scheduling.CompletedWork" Type="FieldControl"
                  Label="Completed" LabelPosition="Left" />
              </Column>
            </Group>
          </Column>
        </Group>
        <Group>
          <Column PercentWidth="50">
            <TabGroup>
              <Tab Label="Description">
                <Control FieldName="System.Description" Type="HtmlFieldControl" Dock="Fill" />
              </Tab>
              <Tab Label="Implementation">
                <Group>
                  <Column PercentWidth="50">
                    <Control FieldName="Microsoft.VSTS.Build.IntegrationBuild" Type="FieldControl"
                      Label="Integrated in Build" LabelPosition="Left" />
                  </Column>
                  <Column PercentWidth="50" />
                </Group>
                <Control Type="LinksControl" Name="Hierarchy">
                  <LinksControlOptions>
                    <WorkItemLinkFilters FilterType="include">
                      <Filter LinkType="System.LinkTypes.Hierarchy" />
                    </WorkItemLinkFilters>
                    <WorkItemTypeFilters FilterType="include">
                      <Filter WorkItemType="Task" />
                      <Filter WorkItemType="User Story" />
                    </WorkItemTypeFilters>
                    <ExternalLinkFilters FilterType="excludeAll" />
                    <LinkColumns>
                      <LinkColumn RefName="System.ID" />
                      <LinkColumn RefName="System.WorkItemType" />
                      <LinkColumn RefName="System.Title" />
                      <LinkColumn RefName="System.AssignedTo" />
                      <LinkColumn RefName="System.State" />
                      <LinkColumn LinkAttribute="System.Links.Comment" />
                    </LinkColumns>
                  </LinksControlOptions>
                </Control>
              </Tab>
            </TabGroup>
          </Column>
          <Column PercentWidth="50">
            <TabGroup Margin="(5,0,0,0)">
              <Tab Label="History">
                <Control FieldName="System.History" Type="WorkItemLogControl" Dock="Fill" />
              </Tab>
              <Tab Label="All Links">
                <Control Type="LinksControl" Name="GeneralLinks">
                  <LinksControlOptions>
                    <LinkColumns>
                      <LinkColumn RefName="System.ID" />
                      <LinkColumn RefName="System.WorkItemType" />
                      <LinkColumn RefName="System.Title" />
                      <LinkColumn RefName="System.AssignedTo" />
                      <LinkColumn RefName="System.State" />
                      <LinkColumn LinkAttribute="System.Links.Comment" />
                    </LinkColumns>
                  </LinksControlOptions>
                </Control>
              </Tab>
              <Tab Label="Attachments">
                <Control Type="AttachmentsControl" LabelPosition="Top" />
              </Tab>
            </TabGroup>
          </Column>
        </Group>
      </Layout>
      <WebLayout>
        <SystemControls>
          <Control Type="FieldControl" FieldName="System.Title" EmptyText="Enter title" />
          <Control Label="Assi&amp;gned To" Type="FieldControl" FieldName="System.AssignedTo" />
          <Control Label="Stat&amp;e" Type="FieldControl" FieldName="System.State" />
          <Control Label="Reason" Type="FieldControl" FieldName="System.Reason" />
          <Control Label="&amp;Area" Type="WorkItemClassificationControl"
            FieldName="System.AreaPath" />
          <Control Label="Ite&amp;ration" Type="WorkItemClassificationControl"
            FieldName="System.IterationPath" />
          <Control Label="History" Type="WorkItemLogControl" FieldName="System.History" />
          <Control Label="Links" Type="LinksControl" Name="Links" />
          <Control Label="Attachments" Type="AttachmentsControl" Name="Attachments" />
        </SystemControls>
        <Page Label="Details" LayoutMode="FirstColumnWide">
          <Section>
            <Group Label="Description">
              <Control Label="Description" Type="HtmlFieldControl" FieldName="System.Description" />
            </Group>
          </Section>
          <Section>
            <Group Label="Development">
              <Control Type="LinksControl" Name="Development">
                <LinksControlOptions ViewMode="List" ZeroDataExperience="Development"
                  ShowCallToAction="true">
                  <ListViewOptions GroupLinks="false"></ListViewOptions>
                  <LinkFilters>
                    <ExternalLinkFilter Type="Build" />
                    <ExternalLinkFilter Type="Integrated in build" />
                    <ExternalLinkFilter Type="Pull Request" />
                    <ExternalLinkFilter Type="Branch" />
                    <ExternalLinkFilter Type="Fixed in Commit" />
                    <ExternalLinkFilter Type="Fixed in Changeset" />
                    <ExternalLinkFilter Type="Source Code File" />
                    <ExternalLinkFilter Type="Found in build" />
                    <ExternalLinkFilter Type="GitHub Pull Request" />
                    <ExternalLinkFilter Type="GitHub Commit" />
                  </LinkFilters>
                </LinksControlOptions>
              </Control>
            </Group>
            <Group Label="Related Work">
              <Control Type="LinksControl" Name="Related Work">
                <LinksControlOptions ViewMode="List">
                  <LinkFilters>
                    <WorkItemLinkFilter Type="System.LinkTypes.Duplicate-Reverse" />
                    <WorkItemLinkFilter Type="System.LinkTypes.Hierarchy-Reverse" />
                    <WorkItemLinkFilter Type="Microsoft.VSTS.Common.TestedBy-Reverse" />
                    <WorkItemLinkFilter Type="Microsoft.VSTS.Common.TestedBy-Forward" />
                    <WorkItemLinkFilter Type="System.LinkTypes.Hierarchy-Forward" />
                    <WorkItemLinkFilter Type="System.LinkTypes.Duplicate-Forward" />
                    <WorkItemLinkFilter Type="System.LinkTypes.Dependency" />
                    <WorkItemLinkFilter Type="System.LinkTypes.Related" />
                    <ExternalLinkFilter Type="GitHub Issue" />
                  </LinkFilters>
                  <Columns>
                    <Column Name="System.State" />
                    <Column Name="System.ChangedDate" />
                    <Column Name="System.Links.Comment" />
                  </Columns>
                </LinksControlOptions>
              </Control>
            </Group>
          </Section>
        </Page>
      </WebLayout>
    </FORM>
  </WORKITEMTYPE>
</witd:WITD>
```


## Step 2: Update Your Current Process Template

Modify your current process template XML to include the "Dependency Request" work item type.

Add the icon for the work item type. 

```diff
<Properties>
    ...
    <Property 
        name="WorkItemTypeIcons" 
        value="
        Bug=icon_insect,
        Code Review Request=icon_code_review,
        Code Review Response=icon_code_response,
        Epic=icon_crown,    
        Feature=icon_trophy,
        Feedback Request=icon_review,   
        Feedback Response=icon_response,   
        Impediment=icon_traffic_cone,
        Product Backlog Item=icon_list,
        Shared Parameter=icon_test_parameter,   
        Shared Steps=icon_test_step,
        Task=icon_clipboard,
        Test Case=icon_test_case,
        Test Plan=icon_test_plan,Test   
        Suite=icon_test_suite, 
+       Dependency Request=icon_review
        " 
    />
</Properties>
```

Add the work item color for the work item type. 

```diff
<WorkItemColors>
    ...
+   <WorkItemColor 
+       primary="FFFF0000" 
+       secondary="FFFFEAEA" 
+       name="Dependency Request" 
+   />
</WorkItemColors>
```

## Step 3: Configure the Dependency Hub in @Scale

1. Go to the new menu option **Dependencies**.
2. Click on **Choose work item type** in the settings or config.
3. Select the newly created **Dependency Request** item.

## Step 4: Verify the Work Item Type

1. Go to the **Dependency Hub** in @Scale.
2. Create a new **Dependency Request** in the view.
3. Ensure the states (New, Done, Removed) and transitions work as expected.

That's it! You've successfully created a "Dependency Request" work item type in Azure DevOps using the XML process model and configured it in the Dependency Hub in @Scale.
