# Flow distribution 
<img width="900" alt="image" src="https://github.com/solidify/scale/assets/83336871/d7c3a2d3-1722-4e0b-8788-8e91c64211d4">

The Flow Distribution function provides a clear picture of how work items are dispersed across various workflow stages. It assists in uncovering potential bottlenecks, a critical aspect of effective planning. Utilizing this tool can help enhance overall productivity and process efficiency.

### Configuration
Flow distrubtion can be configured to separate data by Work items or Work items & Value Area. This means that if your organization uses example the work item Feature, but you separate these by Value Area, Example Architecture & Business, these can be separated to visually show this separation of work in the graph.

<img width="250" alt="image" src="https://github.com/solidify/scale/assets/83336871/b4908deb-0ad6-40bf-b57c-67e46f3c012f">


### Getting the data 

To get the data for the Flow Distribution we query the entity type WorkItemBoardSnapshot. This returns a state snapshot of a board work item during a given timeframe. 

One query is made per avaialble project ID in the list of distinct projects in the selected ART. 

We query the following entries: 

- Date value between selected ARTs PI Start and End Date
- Has team id in list of teams included in the selected ART
- Has an iteration that starts with the selected ARTs PI iteration paths (or team iterations if applicable)
- Has a work item type in the list of selected work item types in the filter in the @Scale analytics   

### Mapping the data to the view

All entries with the same dates are grouped together, adding the distinct groups to a property to allow the dataset to be filtered.

