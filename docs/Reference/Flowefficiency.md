# Flow Efficiency

<img width="900" alt="Flow Efficiency graph" src="https://github.com/user-attachments/assets/3a2f94cc-6a69-4401-a222-0ec04ed0fd60">

Flow Efficiency is the percentage of time that work items are actively being worked on versus the total time they are in progress. This metric helps identify delays caused by waiting times and enables teams to streamline workflows and improve productivity.

## How Flow Efficiency is Calculated

Flow Efficiency is calculated using the following formula:

**Flow Efficiency (%) = (Active Time ÷ Total Time) × 100**

- **Active Time**: The total time work items are actively being worked on.
- **Total Time**: The sum of Active Time and Waiting Time.

### Example

If a work item has:
- **Active Time**: 10 days
- **Waiting Time**: 5 days

Then the **Total Time** = Active Time + Waiting Time = **10 + 5 = 15 days**

Using the formula:

**Flow Efficiency (%) = (Active Time ÷ Total Time) × 100**  
**Flow Efficiency (%) = (10 ÷ 15) × 100**  
**Flow Efficiency (%) = 66.67%**

In this scenario, 66.67% of the time was spent actively working on the item, while the remaining 33.33% was spent in waiting.



## Fetching the Data

To generate the Flow Efficiency graph, @Scale uses Azure DevOps Analytics and processes data as follows:

1. **Querying the Data**:
   - The entity type `WorkItemBoardSnapshot` is queried to get snapshots of work items across specified states.
   - Queries are made for:
     - Selected ARTs (Agile Release Trains)
     - Teams associated with the ARTs
     - Program Increment (PI) Iteration Paths
     - Work item types selected in the filter settings
   - States are categorized as either "Active" (doing) or "Waiting" (queued) based on board column configurations in Azure DevOps.
     <img width="250" alt="image" src="https://github.com/user-attachments/assets/3d8bba6b-dd65-4730-9f7f-730ee083254f">


2. **Configuration Requirements**:
   - Ensure that all board columns in Azure DevOps are configured and mapped correctly.
   - Missing columns will result in incomplete data in the Flow Efficiency calculation.

3. **Data Selection**:
   - Filters applied in the @Scale analytics interface determine:
     - Work item types
     - Teams
     - ARTs and PIs
   - Only relevant iterations and states are included in the calculation.

4. **Cross-Project Support**:
   - Flow Efficiency supports cross-project ARTs. Ensure all involved projects and teams are configured and accessible in Azure DevOps.

## Displaying the Data

The Flow Efficiency graph displays:
- Percentage breakdown of Active Time and Waiting Time.
- Trends over the selected time range to highlight process inefficiencies.

### Example Scenarios
- **Balanced Workflow**: 50% Active Time and 50% Waiting Time indicate a balanced yet improvable process.
- **High Waiting Time**: 20% Active Time and 80% Waiting Time suggest bottlenecks or delays in the workflow.

## User Configuration

### Filters
- Use the filter options in the @Scale analytics settings to customize the data displayed:
  - Select ARTs, PIs, teams, and work item types.
  - Adjust date ranges to focus on specific periods.

### Board Configuration
- Ensure board columns in Azure DevOps are correctly set as "Doing" or "Queued."
- Split columns (e.g., "In Progress - Doing" and "In Progress - Done") are supported and automatically categorized.


## Example Use Cases

1. **Identifying Bottlenecks**:
   - A high percentage of Waiting Time indicates potential areas where work is delayed.
   - Drill down into specific states or work item types causing delays.

2. **Optimizing Workflow**:
   - Increase Active Time by minimizing time spent in Waiting states.
   - Adjust team processes or priorities to address inefficiencies.

---

## FAQs

**Q: What if no data is displayed in the graph?**  
A: Ensure board columns are configured in Azure DevOps and mapped to "Doing" or "Queued." Missing configurations can result in incomplete data.

**Q: Can I analyze data across multiple projects?**  
A: Yes, Flow Efficiency supports cross-project ARTs. Ensure all necessary permissions and configurations are in place.

**Q: How often is data updated?**  
A: Data is fetched in real-time from Azure DevOps Analytics and updated dynamically based on filter selections.

---

## References

- [Azure DevOps Analytics Permissions and Prerequisites](https://learn.microsoft.com/en-us/azure/devops/report/analytics/analytics-permissions-prerequisites?view=azure-devops)
- [SAFe Metrics Guide](https://www.scaledagileframework.com/metrics)
