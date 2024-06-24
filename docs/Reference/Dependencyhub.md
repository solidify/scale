# Dependency Hub User Guide

## Introduction

The Dependency Hub in @Scale improves dependency management with a comprehensive, user-friendly interface. It provides real-time visibility into dependency statuses, helping teams stay on track.

## Key Features

### Request Layer
- Send and manage dependency requests to team members.
- Accept or decline requests to clarify responsibilities.

### Dashboard Overview
- Real-time updates on dependency statuses.
- Visualize which dependencies are accepted, declined, or pending.

### Status Tracking
- Monitor dependencies through their lifecycle.
- Track statuses such as in progress, planned, delivered, or late.

## Using the Dependency Hub

### Sending a Dependency Request
1. Navigate to the Dependency Hub.
2. Click on "New Dependency Request."
3. Fill in the details and send the request.
   1. **Title** - Title of the dependency request
   2. **Requested by** - Which team is requesting this dependency?
   3. **Depends on** - Which team is solving or delivering this dependency
   4. **Requested for** - For what is this dependency needed to? (Select an item in the requested by teams backlog
   5. **Need By** - In what iteration does this need to be delivered?
   6. **Description** - Describe what this dependency request is about
      
   ![dependencyhub new dependency](https://github.com/solidify/scale/assets/83336871/187b1280-3978-4b51-ac5f-870d6d75f3bc)


### Managing Dependencies
- View and manage all requests on the dashboard.
- Track accepted dependencies through their lifecycle.
- Reassign or re-evaluate declined dependencies.

### Tracking Progress
- Dependencies are color-coded based on their status.
- Hover over a dependency for detailed information.

### Example Dashboard

<img width="1200" alt="image" src="https://github.com/solidify/scale/assets/83336871/2c637243-af78-4920-b6b0-9765824dbe49">


## Getting Started

### Enabling & configuring the Dependency Hub
1. Go to the new menu option "Depdendencies"
2. Go through the guide
3. Configure the workflow for dependencies
<img width="600" alt="image" src="https://github.com/solidify/scale/assets/83336871/c8feeaef-8b7a-496e-9ce9-599a6da2c7c3">

There are 3 different options when working with dependencies. We recommend choosing option 1 which is a predefined work item type that will get configured.
1. **Predefined Work item type** - @Scale will configure a new work item type in your process called "Dependency Request" 
2. **Custom work item type** - If you already have a similar request item in your process, you can select your own item which will act as a dependency request in @scale.
3. **No configuration** - This will just show a list of your dependencies (Predecessor & successors), this limits the functionality and removes the request capabilties of @Scale

### General Functions

| **Setting** | **Function** |
|-------------|--------------|
| Internal team dependencies | Toggle visibility of dependencies within the same team where both the predecessor & successor exist in the same team |
| Filtering | Filter on any of the columns through the filter button|


## Workflow Examples & Board Recommendations

Dependency Requests can be shown in the board, but here are some general recommendations of how you can mittigate a cluttered board!

### Workflow of requests

The Dependency request can have 3 different states
1. **Pending** - This means that the dependency request has not been accepted or declined yet.
2. **Accepted** - Once a Dependency request gets accepted, you need to link it to the real item that is solving this dependency request. This will close the request and link to the item solving this need.
![dependency hub accept](https://github.com/solidify/scale/assets/83336871/05ef577c-9de3-4387-984f-8dae37c796c0)
3. **Declined** - When a dependency request gets declined, you need to state a reason why this request is getting declined. This will put the dependency request in the state "Removed" and state the reason within the dependency hub list.
<img width="701" alt="image" src="https://github.com/solidify/scale/assets/83336871/daecc934-8a6d-420c-9aab-dfe0258bd038">

### Board Example & Recommendations

Let's say that we are in the middle of planning, and we have just put out estimates for when our features will be delivered. This will look something like this in the board:
![image](https://github.com/solidify/scale/assets/83336871/21825e6b-f126-40df-be82-f1c16a9c1f21)

Now we wan't to create dependencies, So I head to the new dependency hub and create a dependency request. My team needs new pipelines for a new features we are building. So I request them from the innovation team:
<img width="350" alt="image" src="https://github.com/solidify/scale/assets/83336871/f46799c3-ed85-4e64-9447-ebfa25b8b6fe">
<img width="1200" alt="image" src="https://github.com/solidify/scale/assets/83336871/5aa9d9fd-6851-470c-a733-988062d52a9a">

Without them accepting or declining this, I've added to show "Dependency Requests" in the board settings and this is how it looks now:
<img width="1200" alt="image" src="https://github.com/solidify/scale/assets/83336871/87c338bf-aed0-492a-9f17-755bec9f7008">

This will notify the innovation team, and if they enter the Dependency view, they can accept or decline this request. In this case, the innovation team accepts it and creates a user story to solve this need:
![Accepting dependency1](https://github.com/solidify/scale/assets/83336871/b1a644ae-22e8-48bd-87bd-5b5c84f180ca)

This is how the board will look now when they have accepted and created an item that solves this need and planned for, as you can see, two items exist, the request and the item solving it, However, the request has changed state to "Accepted" which is in the state category of closed items:
<img width="1200" alt="image" src="https://github.com/solidify/scale/assets/83336871/442436c1-544f-460e-8ec8-e3be5166c664">

And to limit the board, I can set some rules, Let's say I don't want to see accepted dependencies, becasue they will always have a new linked item to them. I can then set the rule to exclude every dependency request that has the state "Accepted"
<img width="600" alt="image" src="https://github.com/solidify/scale/assets/83336871/379af8ba-02b0-4052-8512-ee5a99636a33">

This will make sure that only the unhandeled Dependency Requests & Dependencies are shown in the board when you plan together with your teams:
<img width="1200" alt="image" src="https://github.com/solidify/scale/assets/83336871/7f5204ca-d7ac-41d6-85c8-1585869dc5af">






