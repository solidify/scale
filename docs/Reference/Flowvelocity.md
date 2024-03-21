# Flow Velocity
<img width="900" alt="image" src="https://github.com/solidify/scale/assets/83336871/0d4ac4d3-a539-4deb-a9ce-e1691ba6faed">

The Flow Velocity graph visually represents the volume of work in story points or effort accomplished within a specific timeframe. It serves as a valuable tool for detecting and addressing slowdowns in your workflow.


### Getting the data 

To get the data for Flow Velocity we query the entity type "WorkItems" in the Ado analytics service. @Scale is looking for work items that: 

- Has a work item type in the list of selected work item types in the filter in the @Scale analytics   
- Has an area path that is subscribed to the team ids in the list of teams selected by the user   
- Has an iteration that starts with the selected ARTs PI iteration paths (or team iterations if applicable) 
- Has a state category of 'Completed'
- Has the fields Effort or Story Points on the work item form

One query is made per avaialble project ID in the list of distinct projects in the selected ART. 

The query returns a list of objects with the following structure. 

```
{
    "WorkItemId": 34549,
    "Title": "allo",
    "WorkItemType": "Feature",
    "State": "Closed",
    "Effort": null,
    "StoryPoints": null,
    "Iteration": {
        "IterationPath": "Champions league\\PI 1"
    },
    "Area": {
        "AreaPath": "Champions league\\Test 1"
    },
    "Project": {
        "ProjectName": "Champions league"
    },
    "Teams": [
        {
            "TeamId": "9650e20c-6086-4f74-ae9b-c4b5504d04d5",
            "TeamName": "Test 1"
        }
    ]
}
```

### Mapping the data to the view

Only sprints with dates that are before todays date are displayed in the graph. 

The data is mapped into a structure where per pi, all effort/storypoint values are summarized per iteration  

### Cross project

As of writing this document, Flow Velocity does not have support for cross project ARTs. This means that the graph will show the wrong data for ARTs that have teams in other projects than the project that @Scale runs in. 

