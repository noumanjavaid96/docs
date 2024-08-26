# Store Usage and Billing Dashboard

This document explains the Usage and Billing dashboard for individual stores within the DDS AI-powered reporting system. This dashboard allows dealership personnel to track their store's API usage and associated costs, manage credit grants, and view invoice details specific to their dealership.

#### 1. Dashboard Sections

The dashboard is organized into five key sections:

* **A. Usage: Cost:** A stacked bar chart visualizing the store's monthly spending, broken down by AI service type.
* **B. Spend by Project:** A stacked bar chart illustrating spending trends for individual projects associated with the store.
* **C. Monthly Bill:** Provides a summary of the current month's bill for the store, including the current usage limit and the option to increase it.
* **D. Credit Grants:** Tracks available credit balances specifically assigned to the store, along with their expiration dates.
* **E. Invoices:** Presents a simplified view of the store's monthly invoices and their payment status.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

2\. Section Details

**A. Usage: Cost**

* **Visualization:** A stacked bar chart displays the monthly spending for August, with each bar representing a specific date range (e.g., 01 Aug, 08 Aug, 15 Aug).
* **Data:** The chart breaks down the store's spending into three categories:
  * **AI:** Indicates the cost associated with using AI models for generating reports. This likely reflects the token usage costs.
  * **Chat:** Shows the expenses related to chatbot interactions or conversational AI features used in the reporting system for the store.
  * **Image:** Reflects costs tied to image generation or processing for the store, if such functionalities are available.
* **Insights:**
  * The chart reveals the store's peak spending periods within the month.
  * It highlights which service category (AI, Chat, Image) drives the most significant costs for the store.

**B. Spend by Project/ Spent by branch if any**

* **Visualization:** A stacked bar chart illustrates spending patterns for individual projects assigned to the store. There are two projects shown in the example: "branch1" and "branch2".
* **Data:** This chart provides a date range-based breakdown of spending, similar to "Monthly Spend," but it separates costs by individual projects for greater granularity.
* **Insights:**
  * The chart helps identify projects contributing the most to the store's spending.
  * It allows users to track spending trends for specific projects over time.

**C. Monthly Bill**

* **Data:** This section displays the store's current monthly bill, along with its current usage limit (set at $120,000 in the example).
* **Actions:** The "Increase limit" button enables users to request a higher usage limit for their store, potentially leading to a modified pricing plan.

**D. Credit Grants**

* **Data:** This section shows details about credit grants applied to the store's account:
  * **$1,165.88 / $2,505.00:** Indicates a credit grant applied to the store. $1,165.88 is the remaining balance from an initial $2,505.00 grant.
  * **Two Additional Grants:** Details for two other credit grants, including received dates, status ("Available"), current balances, and expiration dates, are also provided.
* **Insights:** Users can monitor available credit, anticipate expiration dates, and plan their AI reporting usage to maximize available resources.

**E. Invoices**

* **Data:** This table presents a simplified invoice for June 2024, indicating the month, payment status ("Paid"), and invoice balance ($5.65).
* **Insights:** Dealership personnel can review their past invoices and payment history specific to their store.

#### 3. Dashboard Filters & Actions

* **Filters:** The top-right corner of the dashboard houses filter options:
  * **Cost:** Allows filtering usage data based on cost ranges.
  * **Activity:** Enables filtering by specific user activities related to the reporting system.
  * **August:** Filters data for the month of August.
* **Export:** A download button enables exporting the dashboard data for the store, likely as a CSV or spreadsheet file.

#### 4. Data Insights and Potential Uses

This store-specific dashboard enables dealerships to:

* **Manage AI Reporting Costs:** Monitor monthly spending trends and analyze how usage is distributed across different AI services (AI, Chat, Image) and projects.
* **Optimize Resource Allocation:** Make data-driven decisions about AI service usage and allocate resources effectively based on spending patterns and project needs.
* **Understand Credit Usage:** Track available credit and plan reporting activities based on grant balances and expiration dates.
* **Monitor Invoices and Payments:** Review invoice history and payment status for their store.
