# DDS AI-Powered Reporting System: Dashboard Overview

This document provides an overview of the DDS AI-powered reporting system dashboard. The dashboard provides a visual representation of key system metrics, allowing DDS administrators and dealership personnel to monitor AI usage, performance, and individual store details.

#### 1. Dashboard Components

The dashboard is divided into four main sections:

* **A. System Overview:** Provides a high-level summary of the system's usage across all dealerships.
* **B. Token Usage by Store:** A bar chart visualizing token consumption by individual store.
* **C. AI Performance Metrics:** A line chart illustrating the average AI accuracy across stores.
* **D. Store Details:** A tabular view displaying detailed information for each store in the system.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### 2. Section Details

**A. System Overview**

This section displays four key metrics:

* **Total Stores:** The total number of dealerships registered and integrated with the AI-powered reporting system (currently 5).
* **Stores with Active AI:** The number of dealerships currently utilizing the AI-powered reporting features (currently 4).
* **Total Token Usage:** The aggregate token consumption across all dealerships (currently 27,500).
* **Avg. AI Accuracy:** The average accuracy of the AI models across all reports generated (currently 69.05%). This metric is calculated based on user feedback collected through "Thumbs Up" and "Thumbs Down" buttons associated with each generated report.

**B. Token Usage by Store**

* **Visualization:** A bar chart visually represents the token usage for each store.
* **Data:** The chart displays the token usage for each of the five stores. Store 3 has the highest usage (15,000 tokens), followed by Store 4 (7,500 tokens). Stores 1, 2, and 5 have either minimal or no token usage.

**C. AI Performance Metrics**

* **Visualization:** A line chart shows the trend of average AI accuracy across the five stores.
* **Data:** The chart suggests that AI accuracy is generally high, fluctuating between approximately 60% and 100%. The accuracy dips for Store 2, which aligns with its inactive AI status (as shown in the "Store Details" section).

**D. Store Details**

* **Visualization:** A table provides a detailed view of individual store information.
* **Columns:**
  * **Store Name:** The name of each dealership.
  * **AI Status:** Indicates whether the AI features are active or inactive for the store.
  * **Token Usage:** Displays the token consumption for the store.
  * **AI Accuracy:** Shows the average accuracy of AI-generated reports for the store, based on user feedback collected through the "Thumbs Up" and "Thumbs Down" buttons.
  * **AI Latency (ms):** Indicates the average time (in milliseconds) taken for the AI models to generate results for the store.
  * **Token:** A unique, alphanumeric token used to authenticate API requests for the store.
  * **Actions:**
    * **View Details:** Provides a link to view more detailed information about the store's AI usage and settings.
    * **Regenerate Token:** Allows administrators to generate a new API token for the store, typically used for security purposes or if the existing token is compromised.

#### 3. AI Accuracy Measurement

The AI accuracy displayed on the dashboard is a direct reflection of user satisfaction with the generated reports.

* **Feedback Mechanism:** Each AI-generated report will include a simple feedback mechanism, likely in the form of "Thumbs Up" and "Thumbs Down" buttons.
* **Accuracy Calculation:** The system will calculate the AI accuracy for each store by:
  1. **Tracking User Feedback:** Recording each "Thumbs Up" (positive feedback) and "Thumbs Down" (negative feedback).
  2. **Calculating the Percentage:** Dividing the number of "Thumbs Up" responses by the total number of responses (Thumbs Up + Thumbs Down) for reports generated for that store.

**Example:**

If a store has received 80 "Thumbs Up" and 20 "Thumbs Down" responses for its AI-generated reports, the calculated AI accuracy would be:

(80 / (80 + 20)) \* 100 = 80%

#### 4. Data Insights and Potential Uses

The dashboard provides valuable insights into:

* **AI System Adoption:** Quickly gauge the overall adoption of the AI-powered reporting features across dealerships (based on "Stores with Active AI").
* **Token Consumption Patterns:** Identify dealerships with high or low token usage, indicating potential areas for optimization or support.
* **AI Performance:** Track the average AI accuracy across stores and identify potential performance issues that may need investigation. Low accuracy for a specific store could indicate that the AI models are not adequately meeting the reporting needs of that dealership.
* **Store-Specific Details:** Get a granular view of individual dealership AI usage, including token consumption, accuracy, latency, and API token management.

#### 5. Dashboard Actions and Management

The dashboard allows for the following actions:

* **Viewing Detailed Store Information:** Clicking "View Details" provides access to more granular information about the selected dealership's AI usage.
* **Regenerating API Tokens:** Administrators can generate new API tokens for individual dealerships to enhance security or manage access.
