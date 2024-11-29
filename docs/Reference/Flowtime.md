# Flow Time Histogram

<img width="900" alt="Flow Time Histogram" src="https://github.com/user-attachments/assets/322176ab-80b3-4b54-b443-a14169e9c06c">

The **Flow Time Histogram** graph shows how long it takes to complete work items by displaying the distribution of completion times (in days). This helps teams understand their workflow efficiency and identify areas for improvement.

---

## What Does It Show?

- **X-Axis (Flow Time):** The time (in days) it took to complete work items.
- **Y-Axis (Count):** The number of work items completed within the respective flow time.
- **Bars:** Each bar represents a group of work items with the same flow time (in days).

### Tooltip:
Hovering over a bar displays:
- The number of work items in that group.
- A breakdown by team or category (if applicable).

---

## How Is Flow Time Calculated?

Flow Time represents the total time it takes for a work item to move from start to completion. This includes:
- **Lead Time (in Days):** The number of days a work item spends in the workflow.

The histogram aggregates this data and groups work items by their flow time for visual clarity.

---

### Example

If the histogram shows:
- **1 Day:** 5 work items  
- **29 Days:** 3 work items (as shown in the tooltip above)  
This means:
- 5 work items were completed in 1 day.
- 3 work items were completed in 29 days.

The **average flow time** is also displayed at the top of the graph for a quick overview of overall efficiency.

---

## How to Use the Flow Time Histogram

1. **Identify Workflow Efficiency:**
   - Short flow times indicate a streamlined workflow.
   - Longer flow times highlight potential delays or bottlenecks.

2. **Compare Across Teams:**
   - Use the tooltip to see how different teams contribute to the flow times.

3. **Set Improvement Goals:**
   - Aim to reduce average flow time by analyzing and addressing delays.

---

## User Configuration

1. **Filters:**
   - **Teams:** Select specific teams to view their flow times.
   - **Program Increments (PIs):** Focus on work completed during a specific PI.
   - **Work Item Types:** Filter by type (e.g., Features, Stories).

2. **Adjust Date Range:**
   - Customize the date range to analyze trends over a specific period.

3. **Expand View:**
   - Use the fullscreen toggle to see the graph in more detail.

---

## FAQs

**Q: What does a longer flow time indicate?**  
A: Longer flow times may point to bottlenecks or delays in your process. Investigate these items to identify areas for improvement.

**Q: Can I see data for specific teams?**  
A: Yes, use the team filter to view flow times for selected teams only.

**Q: What does the average flow time represent?**  
A: The average flow time is the sum of all flow times divided by the total number of work items. It provides a quick overview of your workflow's overall efficiency.

---

## Tips for Improvement

- Analyze the histogram regularly to track progress and workflow changes.
- Focus on reducing the longest flow times to improve the overall average.
- Use team-specific data to identify areas where processes can be optimized.
