# AI-Ready Data Store and Integration

This document focuses on the AI-Ready Data Store within the DDS AI-powered reporting system. It provides an  overview of the data structure, data dictionary, data quality expectations, and the integration of AI models for generating actionable insights for DDS. <mark style="color:yellow;">**While the Business Logic Layer (BLL) and Raw Data Repository are pre-processing steps managed by a**</mark>** **<mark style="color:red;">**DDS internal team,**</mark>** **<mark style="color:yellow;">**understanding these elements in context ensures seamless collaboration and data understanding for effective AI model integration and reporting.**</mark>



Reporting system that involves three key components: the Raw Database, the AI Database, and the Business Logic layer.

* **Raw Database:** This database acts as the system's initial storage point for all data extracted from the dealership management system (DMS). It retains the data in its original, unaltered state, ensuring a complete and auditable record of all transactions. The Raw Database serves as the "single source of truth" \[2] for all subsequent data processing steps.
* **Business Logic:** This component functions as the intermediary between the Raw Database and the AI Database. It houses a set of rules and algorithms that govern how data is cleaned, validated, and transformed. The BL acts as a "cleaning engine," ensuring that only high-quality, consistent data is passed on to the AI Database.
* **AI Database:** Unlike the Raw Database, the AI Database stores data that has been specifically prepared for use by the AI models and reporting engine. This data undergoes cleaning, standardization, and transformation to ensure consistency and accuracy, making it **"AI-Ready"**

Here's a breakdown of the three different steps in the data cleaning workflow:



**Data Validation:** Upon retrieving data from the Raw Database, the BL performs various checks to identify potential errors.&#x20;

This might involve:

* Detecting missing values in essential data fields.
* Verifying that data conforms to expected formats (e.g., date formats).
* Identifying values that fall outside of acceptable ranges.

1. **Data Cleaning:** This stage focuses on resolving inconsistencies and standardizing data formats:

* **Date Standardization:** The BL ensures all dates adhere to a uniform format (e.g., YYYY-MM-DD) to prevent discrepancies caused by variations in regional settings or data entry practices.
* **Name Standardization:** The BL uses algorithms to standardize salesperson, customer, and manager names, addressing inconsistencies arising from nicknames, abbreviations, or inconsistent data entry across various parts of the DMS.

1. **Data Transformation:** This stage involves manipulating data to make it more meaningful and suitable for analysis:

* **Missing Value Handling:** The BL implements strategies to manage missing data points. This might involve:
* **Exclusion:** Removing records entirely if they lack crucial information (e.g., "Sales Date") \[15-17]. However, this approach requires careful consideration to avoid losing potentially valuable data.
* **Imputation:** Substituting missing values with estimated values based on statistical methods or predefined business rules \[15-17].
* **Customizable Exclusion Criteria:** Dealerships often have unique business rules that determine which sales transactions should be included or excluded from reports. The BL allows for the definition of these custom criteria, ensuring reports align with specific dealership practices \[16-18].
* **Data Aggregation:** The BL can summarize data at various levels (e.g., daily, weekly, monthly) and across different dimensions (e.g., by salesperson, department, vehicle model), making the data more manageable and insightful for reporting purposes \[16, 17].

The workflow essentially moves data from the Raw Database, through the BL's cleaning and transformation processes, and finally into the AI Database, where it's ready for use by the AI models and reporting tools.

**1. AI-Ready Data Store Structure**

The AI-Ready Data Store is a dedicated database designed to house **cleaned, standardized, and transformed data for analysis and reporting**. The schema below outlines the proposed tables and fields:

**Table: sales\_performance**

<table data-header-hidden data-full-width="true"><thead><tr><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>Field Name</td><td>Description</td><td>Data Type</td><td>Format</td><td>Source Table(s)</td><td>Transformations</td></tr><tr><td>salesperson_id</td><td>Unique identifier for the salesperson</td><td>INT</td><td></td><td>appointments, bdc_lead_sources</td><td>Standardized ID based on name matching</td></tr><tr><td>sales_date</td><td>Date of the vehicle sale</td><td>DATE</td><td>YYYY-MM-DD</td><td>appointments</td><td>Standardized format</td></tr><tr><td>dealership_id</td><td>Unique identifier for the dealership</td><td>INT</td><td></td><td>appointments</td><td></td></tr><tr><td>vehicle_year</td><td>Year of manufacture of the vehicle sold</td><td>INT</td><td></td><td>appointments</td><td></td></tr><tr><td>vehicle_make</td><td>Make of the vehicle sold</td><td>VARCHAR</td><td></td><td>appointments</td><td></td></tr><tr><td>vehicle_model</td><td>Model of the vehicle sold</td><td>VARCHAR</td><td></td><td>appointments</td><td></td></tr><tr><td>vehicle_trim</td><td>Trim level of the vehicle sold</td><td>VARCHAR</td><td></td><td>appointments</td><td>Model imputation if missing, based on vehicle model</td></tr><tr><td>front_gross</td><td>Profit from the vehicle sale</td><td>DECIMAL</td><td></td><td>appointments</td><td>Converted to numerical type if needed</td></tr><tr><td>back_gross</td><td>Profit from parts &#x26; service on this vehicle</td><td>DECIMAL</td><td></td><td>Calculated</td><td>Calculated from service records linked to this sale based on customer &#x26; vehicle</td></tr><tr><td>total_gross</td><td>Total gross profit (front + back)</td><td>DECIMAL</td><td></td><td>Calculated</td><td>front_gross + back_gross</td></tr><tr><td>customer_id</td><td>Unique identifier for the customer</td><td>INT</td><td></td><td>appointments, bdc_lead_sources</td><td>Standardized ID based on name &#x26; contact matching</td></tr><tr><td>lead_source</td><td>Origin of the lead that led to the sale</td><td>VARCHAR</td><td></td><td>bdc_lead_sources</td><td></td></tr><tr><td>lead_origination_date</td><td>Date the lead was generated</td><td>DATE</td><td>YYYY-MM-DD</td><td>bdc_lead_sources</td><td>Standardized format</td></tr><tr><td>days_to_sale</td><td>Number of days between lead and sale</td><td>INT</td><td></td><td>Calculated</td><td>sales_date - lead_origination_date</td></tr></tbody></table>

**Table: customer\_segments**

| Field Name          | Description                                      | Data Type | Format | Source Table(s)    | Transformations                                                                                                   |
| ------------------- | ------------------------------------------------ | --------- | ------ | ------------------ | ----------------------------------------------------------------------------------------------------------------- |
| customer\_id        | Unique identifier for the customer               | INT       |        | sales\_performance |                                                                                                                   |
| age                 | Customer's age                                   | INT       |        | appointments       | Calculated based on date of birth. Median imputation if missing.                                                  |
| gender              | Customer's gender                                | VARCHAR   |        | appointments       | Mode imputation if missing.                                                                                       |
| zip\_code           | Customer's zip code                              | VARCHAR   |        | appointments       |                                                                                                                   |
| vehicle\_segment    | Category of vehicle purchased (e.g., SUV, Sedan) | VARCHAR   |        | sales\_performance | Derived based on vehicle\_make and vehicle\_model using pre-defined rules or external vehicle classification data |
| purchase\_frequency | Number of vehicles purchased by the customer     | INT       |        | Calculated         | Count of unique sales linked to the customer in sales\_performance                                                |

**Important Schema Note:**

> Several tables within the dds\_managed\_db schema use the prefix "b\_d\_c", which stands for **Business Development Center (BDC)**. However, this abbreviation is not standard database terminology and could lead to confusion. We recommend updating these table names to use clearer, more descriptive names for improved readability and maintainability.
>
> For example:
>
> * **b\_d\_c\_efforts:** Could be renamed to bdc\_performance or business\_development\_center\_performance
> * **b\_d\_c\_lead\_sources:** Could be renamed to bdc\_lead\_sources or business\_development\_center\_lead\_sources
> * **b\_d\_c\_leads:** Could be renamed to bdc\_lead\_activity or business\_development\_center\_lead\_activity

**2. Data Dictionary**

For optimal functionality, AI must comprehensively comprehend each column name, which is why we will supply an elaborate description for every column. This approach ensures that AI can interpret and utilize the data accurately, **thereby** enhancing performance and reliability in various applications. Providing these detailed descriptions is crucial as it bridges the understanding gap and leverages the AI's capabilities to deliver precise and insightful analyses.



**3. Data Quality Expectations**

The **AI-Ready** Data Store will adhere to the following data quality standards:

* **Completeness:** All fields in the AI-Ready Data Store are expected to be complete, with no missing values except where explicitly stated in the schema.
  * **"Sales Date"**: Any record without a "Sales Date" will be excluded from the sales\_performance table.
  * **Imputed Fields:** Fields that have undergone imputation will be clearly identified in the data dictionary, and the imputation method will be documented.
* **Accuracy:** The BLL's validation and transformation processes will ensure that the data is as accurate as possible based on the source data from the DMS.
  * **Regular Data Audits:** Periodic data audits will be performed to identify and address any data discrepancies or anomalies.
* **Consistency:** The data schema and transformation rules enforced by the BLL guarantee consistency across different tables and fields.
  * **Standardized Formats:** Consistent date and name formats will be maintained.
  * **Data Type Enforcement:** Data types will be strictly validated and enforced.

**4. AI Model Integration**

* **Data Access:** AI models will interact with the data in the AI-Ready Data Store through dedicated APIs. This approach balances security and performance.
  * **API Authentication and Authorization:** Robust authentication and authorization mechanisms will be implemented to control access to the data and protect it from unauthorized use.
  * **Data Extracts (Optional):** Depending on the specific requirements of the AI models and the model provider's recommendations, data extracts may be provided in a secure format for model training and evaluation.
* **Data Security:** The AI-Ready Data Store will be hosted in a secure environment with appropriate access controls and encryption measures.
  * **Data Masking:** Sensitive customer information may be masked or de-identified to protect privacy during analysis, depending on the specific AI model use cases and data requirements.

#### Reporting and Visualization Use Cases

The AI-Ready Data Store will be used to generate interactive reports and visualizations, providing DDS dealerships with actionable insights. Here are some examples:

* **Sales Performance Dashboards:** Visualize key sales metrics, track individual salesperson performance, and compare performance across teams and dealerships.
* **Customer Segmentation Reports:** Identify key customer segments based on demographics, purchase behavior, and service history to enable targeted marketing campaigns.
* **Inventory Optimization Reports:** Analyze inventory turnover rates, identify slow-moving stock, and forecast future demand to optimize inventory levels.
* **Service Department Efficiency Dashboards:** Monitor service advisor performance, technician efficiency, and key service metrics to streamline service operations.
* **Marketing ROI Reports:** Track the effectiveness of marketing campaigns by analyzing lead generation, conversion rates, and the cost of customer acquisition.

***

### Flow

<figure><img src="../.gitbook/assets/mermaid-diagram (19).png" alt=""><figcaption></figcaption></figure>

> <mark style="color:yellow;">**Explanation of the Diagram**</mark>\
>
>
> * **Raw Data Repository:** Contains the raw data tables extracted from the DDS Dealership Management System (DMS).
>   * **appointments:** Provides detailed records of customer appointments.
>   * **bdc\_performance:** Contains metrics on the activities and performance of the Business Development Center (BDC).
>   * **bdc\_lead\_sources:** Tracks the origins of leads managed by the BDC.
>   * **bdc\_lead\_activity:** Logs daily lead engagement activities performed by the BDC.
> * **Business Logic (BL):** The core data processing engine responsible for:
>   * **Data Extraction:** Retrieving raw data from the Raw Data Repository.
>   * **Data Validation:** Performing validation checks on the extracted data.
>   * **Data Cleaning:** Standardizing and cleaning the data.
>   * **Data Transformation:** Applying customizable exclusion criteria and transforming data types.
>   * **Data Aggregation:** Aggregating data at various levels.
>   * **Data Loading:** Loading the processed data into the AI-Ready Data Store.
> * **AI-Ready Data Store:** Houses cleaned and transformed data, optimized for AI model consumption and report generation.
> * **AI Model Integration & Reporting:**
>   * **AI Models:** Analyze the cleaned data to generate insights.
>   * **Reporting Dashboard:** Visualizes the generated insights in a user-friendly manner.



