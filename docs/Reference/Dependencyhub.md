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


### General Settings

| **Setting** | **Function** |
|-------------|--------------|
| Work items on the board | Select types of work items to display |
| Show completed items | Toggle visibility of completed items |
| Show capacity & load indicators | Toggle visibility of load and capacity indicators |
| Show child items on cards | Toggle visibility of child work items on cards |

## Load & Capacity Indicators

- Visualize team sprint load and set capacity.
- Capacity adjustments are made by clicking on capacity and entering the number.
- Load notifications indicate if the sprint's workload exceeds capacity:
  - **Green**: Load is below capacity
  - **Yellow**: Load is at capacity
  - **Red**: Load exceeds capacity

## Card Settings

### Exclusions

Exclude specific items from the board using custom rules.

### Fields

Configure essential and additional fields on the board cards:
1. **Core fields**: Essential fields to display.
2. **Additional fields**: Up to 10 custom fields.
3. **Show empty fields**: Display fields without values.
4. **Charms**: Indicators for child item rollups.

### Styles

Define rules to change card colors based on specific criteria.

## Options

Quickly access frequently used features through the options menu.

| **Option** | **Function** |
|------------|--------------|
| Show compact cards | Toggle between full and compact card layout |
| Show dependencies | Show or hide dependency lines between cards |
| Side panel | Open side panel tool |

For more detailed instructions and visual aids, please refer to the complete guide.
