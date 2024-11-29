## **Understanding the Data**

### 1. Data Source
- **Azure DevOps Analytics**: Flow Efficiency data is fetched using Azure DevOps Analytics integrated with @Scale.
- **Work Item States**: The system queries work item states to distinguish between **Active** and **Waiting** times.

### 2. Requirements for Data Calculation
To accurately calculate Flow Efficiency, the following conditions must be met:
- **Work Items**:
  - Must belong to the **selected ART** (Agile Release Train) and **team(s)** specified in the dashboard filters.
- **Iteration Paths**:
  - Must align with the PI (Planning Interval) iteration paths for the selected ART.
- **Board Columns**:
  - Must correctly reflect **Active** and **Waiting** states in Azure DevOps. For example, columns should have "Doing" or "Done" splits to categorize states appropriately.

### 3. Data Selection
- **User-Defined Filters**: Users can apply filters such as ART, teams, PI, and work item types. These filters dynamically adjust the data set to reflect the selected criteria.
  
### 4. Data Querying
- **Fetching Configurations**: The system retrieves board configurations to map work items to their respective states.
- **State Classification**:
  - **Active States**: Columns marked as "Doing" or equivalent indicate active work periods.
  - **Waiting States**: Columns not marked as "Doing" or marked as "Done" represent idle or waiting periods.
- **Duration Calculation**: The system calculates the duration each work item spends in active and waiting states using the `daysPassed` attribute.

---

## **How Flow Efficiency is Calculated**

1. **Identify Relevant Work Items**
   - Includes work items selected based on applied filters.
   - Matches iteration paths corresponding to the PI or team iterations.

2. **Classify States**
   - **Active States**: Represent periods when work is actively being done on the work item.
   - **Waiting States**: Represent periods when the work item is idle or waiting for the next step.

3. **Aggregate Data**
   - Calculate the total number of days spent in active and waiting states across all relevant work items.

4. **Calculate Efficiency**
   - Use the aggregated data to compute the Flow Efficiency percentage:
     \[
     \text{Flow Efficiency} = \left( \frac{\text{Total Active Time}}{\text{Total Lead Time}} \right) \times 100
     \]

---

## **Visualizing Flow Efficiency**

1. **Access Flow Metrics**
   - Navigate to **@Scale Flow Metrics** in the dashboard.

2. **Apply Filters**
   - **ART**: Select the Agile Release Train you want to analyze.
   - **Teams**: Choose the specific teams within the ART.
   - **Work Item Types**: Specify the types of work items to include.
   - **Program Increments (PIs)**: Select the relevant PIs for the analysis.

3. **View the Flow Efficiency Graph**
   - The graph displays:
     - **Percentage of Active Time**: Indicates the proportion of time work items are actively being worked on.
     - **Percentage of Waiting Time**: Shows the proportion of time work items are idle.
     - **Historical Trends**: Provides insights into how Flow Efficiency has evolved over time.

---

## **Example Scenario**

**Given:**
- A work item spends **5 days** in active states and **10 days** in waiting states.

**Calculation:**
- **Total Lead Time** = Active Time + Waiting Time = 5 + 10 = 15 days.
- **Flow Efficiency** = \( \frac{5}{15} \times 100 = 33.33\% \).

**Interpretation:**
- The team is actively working on tasks only **33.33%** of the time, indicating significant opportunities to streamline processes and reduce idle periods.

---

## **Key Insights for Users**

- **Improving Efficiency**:
  - **Reduce Waiting Time**: Identify and address bottlenecks to minimize idle periods.
  - **Optimize Workflows**: Ensure tasks move smoothly between active states to enhance overall productivity.

- **Setting Up Boards Correctly**:
  - **Clear State Definitions**: Ensure all team boards in Azure DevOps have distinct "Doing" and "Done" splits for columns to provide accurate data.
  - **Consistent Configuration**: Maintain consistent board configurations across teams to ensure reliable Flow Efficiency metrics.

- **Cross-Project ARTs**:
  - **Consistent Configuration**: Teams across multiple projects must configure their boards and filters consistently for accurate data aggregation.
  - **Access Permissions**: Ensure appropriate access permissions across all involved projects to visualize complete data sets.

---

## **Technical Details for Administrators**

### **Data Query Process**

- **Board Configuration Retrieval**:
  - Utilizes the `getBoardColumnsConfiguration` function to fetch board column settings.
  - Maps columns into **Active** (e.g., "Doing") and **Waiting** (e.g., "Done") categories based on configuration.

- **Flow Efficiency Calculation**:
  - Employs the `calculateFlowEfficiency` function to compute percentages from the active and waiting durations.
  - Aggregates data using work item states and `daysPassed` to determine total active and waiting times.

### **Configuration Requirements**

- **Backlog Levels**:
  - Ensure backlog levels are correctly mapped and visible in the work item forms.
  - Configure backlog levels to include necessary fields such as **Actual Value** and **Planned Value**.

- **Flow Efficiency Configuration**:
  - Use the `useFlowEfficiencyConfiguration` hook to manage Flow Efficiency settings.
  - Ensure teams are correctly mapped and backlog levels are appropriately filtered.

- **Iteration Path Mapping**:
  - Confirm that iteration paths are correctly associated with PIs and teams.
  - Use the `usePiIterationPaths` hook to manage PI iteration paths.

### **Code Overview**

- **Data Fetching**:
  - Uses `useQuery` from `@tanstack/react-query` to asynchronously fetch data based on selected filters.
  - Filters data based on ART, teams, work item types, and PIs to ensure relevant data is processed.

- **State Management**:
  - Implements hooks like `useFlowEfficiencyConfiguration` and `useFlowEfficiencyData` to manage configurations and data fetching.
  - Utilizes mutations (`useMutation`) to handle configuration updates, ensuring data consistency.

- **Error Handling & Optimization**:
  - Incorporates query invalidation and caching strategies to optimize data fetching and reduce load times.
  - Ensures that data queries are enabled only when necessary conditions are met, improving performance.

---

## **Access and Permissions**

### **Data Access**
- **Azure DevOps Analytics**: Flow Efficiency analytics are powered by Azure DevOps Analytics, ensuring data is up-to-date and accurate.
- **User Permissions**: Users must have **Basic access** or higher within their Azure DevOps projects to access Flow Efficiency metrics.

### **Cross-Project ARTs**
- **Multiple Projects**: For insights spanning multiple projects, users must have the necessary access permissions across all involved projects.
- **Data Visualization**: Proper access ensures that data from all relevant projects is aggregated and visualized correctly in the Flow Efficiency graphs.

---

## **Getting Started with Flow Efficiency**

1. **Enable Analytics Preview**
   - Navigate to **Analytics Settings** in your dashboard.
   - Turn on the **Preview Toggle** to access the new analytics view.

   ![Enable Preview Toggle](https://github.com/solidify/scale/assets/83336871/c2d4f668-8eeb-4e61-8cc3-95ba3c05c41c)

2. **Access Flow Metrics Dashboard**
   - From the **@Scale Dashboards** dropdown, select **Flow Metrics**.

   ![Select Flow Metrics](https://github.com/solidify/scale/assets/83336871/8fd3b96d-f9d1-4344-b4f0-e93e55bd315e)

3. **Configure Filters**
   - Use the filters to select the **ART**, **work item types**, **teams**, and **program increments** you want to include in the Flow Efficiency charts.

   ![Configure Filters](https://github.com/solidify/scale/assets/83336871/0edc7273-0abe-42c1-acc3-7384143cffc8)

4. **View and Analyze Flow Efficiency**
   - The Flow Efficiency graph will display the percentage of active and waiting times.
   - Toggle metrics into full-screen mode for a detailed view.

   ![Flow Efficiency Graph](https://github.com/solidify/scale/assets/83336871/f88a8337-b12c-47e8-8e30-6cdb5f73b05e)

---

## **References**

- **Scaled Agile Framework Metrics Guide**: Deepen your understanding of SAFe metrics through the [Scaled Agile Framework's official metrics guide](https://www.scaledagileframework.com/metrics).
- **Azure DevOps Analytics Permissions**: Learn about the necessary [permissions and prerequisites for accessing Analytics in Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/report/analytics/analytics-permissions-prerequisites?view=azure-devops).

---

## **Support and Feedback**

If you encounter any issues or have suggestions for improving the Flow Efficiency metrics, please reach out to our support team or submit feedback through the @Scale platform.

---

*© 2024 @Scale Analytics Documentation. All rights reserved.*
