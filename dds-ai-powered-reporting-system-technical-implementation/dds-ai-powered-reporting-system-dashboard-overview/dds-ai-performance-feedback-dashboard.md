---
icon: message-bot
coverY: 0
---

# DDS AI Performance Feedback Dashboard

This document outlines the key components and functionalities of the DDS AI Performance Feedback Dashboard. This dashboard empowers DDS administrators to track the accuracy and effectiveness of the AI-powered reporting system, analyze user feedback, and identify areas for improvement.

#### 1. Dashboard Sections

The AI Performance Feedback Dashboard is divided into two main views:

* **A. Overview & Feedback Breakdown:** Provides a high-level summary of AI performance and user feedback, along with breakdowns by dealership and report type.
* **B. Performance Trends & Feedback Distribution:** Visualizes AI accuracy trends over time and the distribution of user feedback across different report types.

#### 2. Overview & Feedback Breakdown (View 1)

* **AI Performance Metrics:** This section displays four key metrics:
  * **Average Accuracy:** The overall average accuracy of AI-generated reports across all dealerships (currently 85%).
  * **Total Feedback:** The total number of feedback responses received from users (currently 1000).
  * **Positive Feedback:** The percentage of positive feedback (Thumbs Up) received (currently 75%).
  * **Negative Feedback:** The percentage of negative feedback (Thumbs Down) received (currently 25%).

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* **Filters:** Allows users to filter the displayed data by:
  * **Dealership:** Select specific dealerships to view their individual feedback and performance.
  * **Salesperson:** Filter feedback based on the salesperson associated with the report.
  * **Report Type:** Analyze feedback for specific report categories.
  * **AI Feedback:** Filter data based on positive or negative feedback.
* **Average AI Accuracy over Time:** (Placeholder for a line chart visualizing accuracy trends, as seen in View 2)
* **Feedback Distribution by Report Type:** (Placeholder for a chart showing feedback breakdown by report type, as seen in View 2)
* **Report Feedback:** A tabular view displaying individual feedback entries:
  * **Columns:**
    * **Report Name:** The name of the AI-generated report.
    * **Dealership:** The dealership associated with the report.
    * **Date Generated:** The date the report was generated.
    * **Salesperson:** The salesperson associated with the report (if applicable).
    * **User:** The user who provided the feedback.
    * **Feedback:** Indicates whether the feedback was positive (Thumbs Up) or negative (Thumbs Down).
    * **Comments:** Additional comments provided by the user.

#### 3. Performance Trends & Feedback Distribution (View 2)

* **Average AI Accuracy over Time:** A line chart visualizes the trend of average AI accuracy over time (currently January to June).
  * **Data Insights:** The chart shows a general upward trend in AI accuracy over the six months, with a dip in April.
  * **Annotation:** An annotation on the chart highlights the accuracy in January (82%).
* **Feedback Breakdown by Dealership:** A stacked bar chart displays the breakdown of positive and negative feedback for each dealership.
  * **Data Insights:** All dealerships have a higher proportion of positive feedback than negative feedback. Store 2 has the highest percentage of positive feedback, while Store 4 has the lowest.
  * **Legend:**
    * **Green:** Positive Feedback
    * **Red:** Negative Feedback
* **Feedback Distribution by Report Type:** A pie chart shows the distribution of user feedback across different report types.
  * **Data Insights:** Sales Trend Analysis reports receive the highest volume of feedback (35%), followed by Inventory (25%) and Lead Conversion (20%).
  * **Legend:**
    * **Blue:** Sales Trend
    * **Orange:** Inventory
    * **Yellow:** Lead Conversion
    * **Green:** Service Efficiency
    * **Purple:** Customer Satisfaction

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

#### 4. Data Insights and Potential Uses

This dashboard provides valuable insights into:

* **Overall AI Performance:** Monitor the average AI accuracy and track how it changes over time.
* **User Satisfaction:** Understand user satisfaction levels with the system based on positive and negative feedback.
* **Dealership-Specific Performance:** Identify dealerships with lower AI accuracy or higher rates of negative feedback, indicating potential areas for improvement or further training.
* **Report Effectiveness:** Analyze the distribution of feedback across different report types. Reports with higher proportions of negative feedback may require adjustments or improvements to better meet user needs.
* **Individual Feedback Analysis:** Review user comments to understand specific issues and gather valuable suggestions for enhancing the system.
