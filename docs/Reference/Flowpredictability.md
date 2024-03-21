# Flow Predictability
<img width="900" alt="image" src="https://github.com/solidify/scale/assets/83336871/407c5b6f-7079-4a51-9633-2dfb1c0796ac">

Flow Predictability calculates the ratio of planned business value achieved to actual business value on PI objectives delivered in a PI.

### Getting the data 

To get the data for Flow Predictability @Scale the entity type Work item Type PI Objective or the item you configured in your setup of @Scale in the Ado analytics service. @Scale is looking for work items that: 

### Requirements - New Objecives

- The following fields needs to show in your work item form in order for Analytic Services to visualize the data.
  - Actual Value
  - Planned Value
-  Iteration & Area Path must be configured correctly in order to map objectives to teams and the correct PIs
  - Iteration needs to be in one of the team iterations during a PI
  - Area needs to be set on each teams default area path in Azure DevOps. (If the team is missing a default area path, Objectives and analytics will not show data for this team)

### Requirements - Old Objectives

- The following fields needs to show in your work item form in order for Analytic Services to visualize the data.
  - Actual Value
  - Planned Value
- "Scale_PIObjective_Team" field needs to be mapped correctly with the team name
- Area path needs to be on the root area path selected in settings
- Iteration path needs to exist on the Node, example PI2, and not on the iterations under the node.

#### Calculating Flow Predictability 

For each PI/team group: 
        
        Flow Predictability percentage = SUM of all PI Objective group (Actual Business Value/ SUM of all Commited PI Objective Group (planned values)
