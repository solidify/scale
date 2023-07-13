The Analytics hub gives you insights into how your teams perform. The reports in @Scale complements the built-in reports for metrics like the cumulative flow diagram.

# Solution Train Predictability 
This report shows how the ART delivers on the objectives compared to what was planned. Only committed objectives are included in the diagram. The diagram shows the percentage of actual business value compared to estimated business value for each ART and program increment. The average for all ARTs is also shown as a metric for the predictability of the group.

# Program Predictability
The Program Predictability report works in the same way as the Solution Train Predictability report but instead of ARTs the performance of each Team in the selected ART is shown.

![image](https://user-images.githubusercontent.com/7904771/124176582-5aa7a400-daaf-11eb-8e05-058e93e08b1a.png)

# Analytics view controls

| **Control** | **Function** |
|---|---|
| ![image.png](/docs/.attachments/image-4e95335d-c334-4344-a917-3250b39f98fb.png) | Select active program increment |
| ![image.png](/docs/.attachments/image-9e9e362c-248f-49d9-a2b2-03962629a97c.png) | Enter or exit full screen mode |

# New Analytics & Flow Metrics
We have introduced a new feature that allows users to toggle analytics visibility in the preview mode. 
<img width="900" alt="image" src="https://github.com/solidify/scale/assets/83336871/f887ba3d-9cb3-4ce1-b30f-e030a8189515">



@Scale Flow Metrics introduces the six SAFe flow metrics, enabling you to work with measuring and analyzing flow:

| **Metric** | **Description** |
|---|---|
|Flow Distribution|The Flow Distribution function provides a clear picture of how work items are dispersed across various workflow stages. It assists in uncovering potential bottlenecks, a critical aspect of effective planning. Utilizing this tool can help enhance overall productivity and process efficiency.|
|Flow Velocity|The Flow Velocity graph visually represents the volume of work in story points or effort accomplished within a specific timeframe. It serves as a valuable tool for detecting and addressing slowdowns in your workflow.|
|Flow Time|The Flow Time Histogram graph displays the number of work items and their respective completion times. It's a vital tool for understanding time efficiencies and potential areas for process improvement.|
|Flow Load|The Flow Load graph shows the number of work items in each state. This graph is useful for identifying bottlenecks in your workflow.|
|Flow Efficiency (Coming soon)|Flow Efficiency is the percentage of time that work is actively being worked on. It is calculated by dividing the total active time by the total lead time.|
|Flow Predictability|Flow Predictability calculates the ratio of planned business value achieved to actual business value on PI objectives delivered in a PI.|

To access the new analytics view, go to analytics settings and turn on the preview toggle.

<img width="759" alt="image" src="https://github.com/solidify/scale/assets/83336871/c2d4f668-8eeb-4e61-8cc3-95ba3c05c41c">

From the @Scale dashboards dropdown, select Flow Metrics to start configuring the charts.

<img width="543" alt="image" src="https://github.com/solidify/scale/assets/83336871/8fd3b96d-f9d1-4344-b4f0-e93e55bd315e">

Using the filters, select the ART, work item types, teams, and program increments you want to include in the flow metric charts.

<img width="897" alt="image" src="https://github.com/solidify/scale/assets/83336871/0edc7273-0abe-42c1-acc3-7384143cffc8">

You can choose to look at one metric in isolation by toggling it into full-screen mode.

<img width="806" alt="image" src="https://github.com/solidify/scale/assets/83336871/f88a8337-b12c-47e8-8e30-6cdb5f73b05e">

We utilize Azure DevOps Analytics to get the data for the different metrics. To view analytics data and query the service, the user needs to be a member of a project with Basic access or greater. In order to visualize the data for cross-project ARTs, the user has to be granted access to all projects included.

# References
* [SAFe metrics](https://www.scaledagileframework.com/metrics)
* [Permissions and prerequisites to access Analytics in Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/report/analytics/analytics-permissions-prerequisites?view=azure-devops)


# References
* [SAFe metrics](https://www.scaledagileframework.com/metrics)
