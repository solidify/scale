# Flow load 
<img width="900" alt="image" src="https://github.com/solidify/scale/assets/83336871/9ae96374-282e-4fd4-89e3-73f4d5351d5a">

The Flow Load graph shows the number of work items in each state at a particular day during the selected period. This graph is useful for identifying bottlenecks in your workflow.

### Getting the data 

To get the data for the Flow Load graph @Scale queries the entity type WorkItemBoardSnapshot. This returns a state snapshot of a board work items during a given timeframe/day. 

One query is made per avaialble project ID in the list of distinct projects in the selected ART. 

@Scale queries the following:

- Date value between selected ART minimum and max date. 
- Has team in list of teams included in the selected ART
- Has an iteration that starts with the selected ARTs PI iteration paths (or team iterations if applicable)
- Has a work item type in the list of selected work item types in the filter in the @Scale analytics
- Has states mapped in board columns of Azure DevOps (If a state is missing in your board columns, it will not get included in the data) 

### Mapping the data to the view

All entries with the same dates are grouped together, adding the distinct groups to a property to allow the dataset to be filtered.
