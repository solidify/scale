This article goes through the general usage of @Scale Flow metrics, if you'd like to get more informaion about each graph, click one of the following articles:

| **Topic** |
|---|
| [Flow Distribution](Flowdistribution.md) | 
| [Flow Load](Flowload.md) | 
| [Flow Predictability](Flowpredictability.md) | 
| [Flow Velocity](Flowvelocity.md) | 
| [Flow Time](Flowtime.md) | 


# Flow Metrics
@Scale Flow Metrics introduces the six SAFe flow metrics, enabling you to work with measuring and analyzing flow:

<img width="900" alt="image" src="https://github.com/solidify/scale/assets/83336871/5b34312a-693e-4adc-8f1d-d6b9366aab84">


| **Metric** | **Description** |
|---|---|
|Flow Distribution|The Flow Distribution function provides a clear picture of how work items are dispersed across various workflow stages. It assists in uncovering potential bottlenecks, a critical aspect of effective planning. Utilizing this tool can help enhance overall productivity and process efficiency.|
|Flow Velocity|The Flow Velocity graph visually represents the volume of work in story points or effort accomplished within a specific timeframe. It serves as a valuable tool for detecting and addressing slowdowns in your workflow.|
|Flow Time|The Flow Time Histogram graph displays the number of work items and their respective completion times. It's a vital tool for understanding time efficiencies and potential areas for process improvement.|
|Flow Load|The Flow Load graph shows the number of work items in each state. This graph is useful for identifying bottlenecks in your workflow.|
|Flow Efficiency|Flow Efficiency is the percentage of time that work is actively being worked on. It is calculated by dividing the total active time by the total lead time.|
|Flow Predictability|Flow Predictability calculates the ratio of planned business value achieved to actual business value on PI objectives delivered in a PI.|

To access the new analytics view, go to analytics settings and turn on the preview toggle.

<img width="759" alt="image" src="https://github.com/solidify/scale/assets/83336871/c2d4f668-8eeb-4e61-8cc3-95ba3c05c41c">

From the @Scale dashboards dropdown, select Flow Metrics to start configuring the charts.

<img width="543" alt="image" src="https://github.com/solidify/scale/assets/83336871/8fd3b96d-f9d1-4344-b4f0-e93e55bd315e">

Using the filters, select the ART, work item types, teams, and program increments you want to include in the flow metric charts.

<img width="897" alt="image" src="https://github.com/solidify/scale/assets/83336871/0edc7273-0abe-42c1-acc3-7384143cffc8">

You can choose to look at one metric in isolation by toggling it into full-screen mode.

<img width="806" alt="image" src="https://github.com/solidify/scale/assets/83336871/f88a8337-b12c-47e8-8e30-6cdb5f73b05e">

To dive into these insights, navigate to the analytics settings and enable the preview toggle.

## Access and Permissions

**Data Access:**
Our analytics are powered by Azure DevOps Analytics, ensuring up-to-date and accurate information. For access, users must have Basic access or higher within their Azure DevOps projects.

**Cross-Project ARTs:**
For insights spanning multiple projects, ensure you have the necessary access across all involved projects to visualize the complete data set.

## Understanding the Data Behind Your Analytics

While the intricate details of data queries and processing are managed by @Scale, it’s essential to understand the basics of how your analytics are generated:

- **Data Sources:** We extract data from multiple project IDs associated with your selected ART, using Azure DevOps Analytics services.
- **Data Selection:** Our system intelligently filters data based on date ranges, team IDs, and work item types that you specify in the analytics interface.
- **Data Presentation:** Aggregated and processed data is translated into user-friendly graphs and charts, offering actionable insights at a glance.
- **User Interactions:** Filters and selections you make dynamically alter the displayed data without the need for new queries, ensuring a responsive and fluid experience.

## References

- Deepen your understanding of SAFe metrics through the [Scaled Agile Framework's official metrics guide](https://www.scaledagileframework.com/metrics).
- Learn about the necessary [permissions and prerequisites for accessing Analytics in Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/report/analytics/analytics-permissions-prerequisites?view=azure-devops).


# Original Metrics

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
