Working together at scale requires increased visibility into what others are doing. @Scale adds an interactive program board to make documenting and sharing that information easier. 

# Managing the program board

The program board shows the planned work for your team grouped by team and iteration. Use the [mapping pane]() (1) to drag planned items to the board. You can also add new items directly on the board using the "+ New item" context menu (2). 

Dependencies between items are show as read strings (3) or you can add explicit work items to represent the dependency (4). Another nice charm on the card is the objective icon (6) that is shown when a board item is associated with an objective.

If you select to show the child item status rollup it will be shown as a progress bar on the card (5). 

To help manage large ARTs, or when you want to focus on a specific team, you can collapse teams to make more room on the board (7). The divider line (8) separates the ART and dependent teams.

![image.png](/docs/.attachments/image-dc891003-1929-4005-86fb-d6c796bd8c22.png)

## Mapping items to board

The mapping pane gives you a tool that connects @Scale with your backlog. Drag items from the list (1) to the sprint you plan to complete the item and @Scale will update the card with the target iteration and the default area for the team. 

![image.png](/docs/.attachments/image-e80eaafb-a2de-48c6-87eb-a541146aeb96.png)

Use the filter (2) to narrow down the items in the list, by default we filter on the active program increment.

| **Filter** | **Function** |
|---|---|
| Title | Filter on part of the title |
| Increment | Filter on program increment iteration paths or the root iteration level |
| Team | Filter on the areas the selected teams own |
| State | Filter on state |

## Create a dependency

The easiest way to create a dependency between two cards is to drag the card that represents a dependency onto the other card. This will create a predecessor/successor link between the two cards.

If you create a predecessor/successor link from the work item form or any other tool it will of course also show on the @Scale board.

## Delete a dependency

If you want to remove a dependency between two cards either open one of the work items and remove the successor/predecessor link or click on the dependency line and press the delete key.

# Board view controls

| **Control** | **Function** |
|---|---|
| ![image.png](/docs/.attachments/image-4e95335d-c334-4344-a917-3250b39f98fb.png) | Select active program increment |
| ![image.png](/docs/.attachments/image-58e02360-f706-4d54-b513-c95394e04ee9.png) | Refresh content on page |
| ![image.png](/docs/.attachments/image-4d4aeaa2-efb7-4e21-9cfc-854e997d03ce.png) | Settings: [Board](), [Exclusions](), [Fields](), [Styles]() |
| ![image.png](/docs/.attachments/image-00d419df-cc66-42a6-b982-52171260bf8a.png) | Filter |
| ![image.png](/docs/.attachments/image-d2b2e0d4-a38b-4635-af19-b7578759ef1c.png) | [Options]() |
| ![image.png](/docs/.attachments/image-9e9e362c-248f-49d9-a2b2-03962629a97c.png) | Enter or exit full screen mode |

## Board settings

Board settings controls general behaviors for the boards. The configuration is stored at project level.

| **Setting** | **Function** |
|---|---|
| Highlight dependencies | If enabled show dependencies in red, else gray |
| Show completed items | If enabled also show items in status done on the board |
| Show all teams in mapping filter | If enabled show all teams in the project in the mapping panel |
| Show dependency on board | If enabled you can also show work items for dependencies. Select the work item type that represents the dependency |

![image.png](/docs/.attachments/image-39100247-354e-418b-a9d3-e3f70f5f3ebd.png)

## Card settings

### Exclusions

Sometimes you don't want to include all items on the board matching the teams area paths and the iterations for the PI. Use exclusions to add rules which will filter out the matching items from the board.

![image.png](/docs/.attachments/image-986451ac-a4bf-48c3-820a-b872e893d23f.png)

### Fields

Add fields and charms to your board cards to make important information stand out.

The settings dialog lets you configure

1. **Core fields**. These are the essential fields you typically want to show on the card.
2. **Additional fields**. Add up to 10 custom fields to show on the board. The Parent field has the extra feature of showing the field with a link that opens the work item form.
3. **Show empty fields**. Enable if you want to show the field even if it does not have a value.
4. **Charms**. Check Show subitem rollup if you want a small rollup indicator to be shown on cards with child items. The rollup will show number of planned/in progress/completed child items for the card.

![image.png](/docs/.attachments/image-f709cec4-4652-4b56-9de7-117ad1c06fdf.png)

Also check out the Azure Boards [Choose fields to appear on cards](https://docs.microsoft.com/en-us/azure/devops/boards/boards/customize-cards?view=azure-devops#fields).

### Styles

Styles let you define rules to make cards change color when the rule criteria match.

To add a style you click on the + Styling rule, next add a field rule and card style for the card.

![image.png](/docs/.attachments/image-5714c592-0e2d-4d97-a090-01e52a0ed23a.png)

See Azure Boards [Define style rules to highlight cards](https://docs.microsoft.com/en-us/azure/devops/boards/boards/customize-cards?view=azure-devops#define-style-rules-to-highlight-cards) for additional information on how cards styles can be used.

## Options

The options menu lets you quickly access frequently used features.

![image.png](/docs/.attachments/image-a51ac158-ad7f-4221-9b50-f3e3c911de20.png)

| **Option** | **Function** |
|---|---|
| Show compact cards | Show card in full or compact layout. The compact mode is great if you want to get an overview of a large board |
| Show dependencies | Show or hide the dependency lines between cards |
| Side panel | Open side panel tool: [Mapping]() |
