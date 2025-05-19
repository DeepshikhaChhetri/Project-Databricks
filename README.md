# Customer Retention Analytics Using the Modern Data Stack

## Objective

The objective of this project was to develop a modern marketing analytics solution focused on understanding customer retention in an e-commerce context. The key business question addressed:
***"How long does it take for customers to make their second purchase, and how does this vary across different customer cohorts?"***

This initiative provided hands-on experience using the modern data stack, spanning from data ingestion and transformation to cohort-based visualization — ultimately delivering actionable insights into customer behavior.

## High-Level Workflow
### 1. Data Ingestion
Source: Simulated e-commerce transaction data from a BigQuery table named ecom_orders.

Planned Tool: Fivetran (for syncing GCP Cloud SQL → Databricks).

Challenge: Connection issues between Fivetran and Databricks.

Workaround: Data was manually loaded into Databricks to proceed with analysis.

### 2. Data Structure Overview
The dataset, ecom_orders, emulates transactional sales data with the following schema:

| Column Name   | Description                         |
| ------------- | ----------------------------------- |
| `customer_id` | Unique identifier for each customer |
| `order_date`  | Date of the order                   |
| `order_id`    | Unique identifier for each order    |
| `row_id`      | Unique numeric row identifier       |
| `sales`       | Monetary amount of the sale         |


### 3. Data Transformation in Databricks
#### Objective: Prepare data for cohort analysis by deriving key retention metrics.

**Key Steps:**
Identified each customer's first purchase date.
Determined the second purchase date, if available.
Calculated the days between first and second purchases.
Saved the transformed dataset as a new table: cohort_analysis.

All analysis and data transformation were performed using **SQL queries** within Databricks.

### 4. Data Visualization in Databricks Dashboards
Three visualizations were developed to analyze customer behavior by cohort. Below are the results derived from SQL-based analysis:

### Key Performance Indicators (KPIs)
Based on the analysis of the e-commerce dataset, the following summary metrics were identified:
- Total Customers: 1,000
- Total Orders: 1,000
- Total Sales: $156,795

### Visualization 1: Retention Rate by Cohort
#### Result – Trend Over Time in Retention Rate
**Purpose:** To evaluate what percentage of customers from each monthly cohort made a second purchase within 1, 2, and 3 months after their initial purchase.

**Highest Retention Rates by Time Threshold**
1-Month Retention: June 2024 cohort – 80.00%
2-Month Retention: June 2024 cohort – 100.00%
3-Month Retention: May & June 2024 cohorts – 100.00%

**Notable Differences Across Cohorts**
1-Month Retention: Ranges from 34.62% (April) to 80.00% (June)
2-Month Retention: Overall increase compared to 1-month; June cohort perfect at 100%
3-Month Retention: May and June show strongest loyalty; older cohorts show gradual improvement

**Conclusion**
More recent cohorts (May & June 2024) show significantly higher short-term retention.
Older cohorts (February & April 2024) consistently underperform.
Indicates improved customer loyalty or acquisition quality in recent months.

### Visualization 2: Repeat Purchase Rate by Cohort
#### Result – Trends Over Time in Repeat Purchase Rates
**Purpose:** To assess how many customers from each cohort placed a 2nd, 3rd, or 4th order.

**Observations**
2nd Order: Consistently high repeat rates; slight dips in Feb & Apr 2024
3rd Order: Downward trend in recent cohorts; June cohort drops to 70.00%
4th Order: Clear declining trend from 83.33% (Jan) to 60.00% (June)

**Summary**
2nd purchase behavior remains strong across cohorts.
3rd and 4th purchase behaviors weaken over time, especially in more recent months.
May and June cohorts show lower long-term engagement.

**Consideration**
May/June 2024 cohorts have fewer customers, increasing volatility in rate calculations.
Despite smaller samples, the downward trend is consistent and notable.

### Visualization 3: Cohort Size by Month
#### Result – Cohort Size by Month Analysis
**Purpose:** To evaluate customer acquisition volume by month (i.e., cohort size).

**Key Findings**
Largest Cohort: January 2024 – 66 customers
Decline Over Time: February (48), March (33), April (27)
Smallest Cohorts: May (16), June (10)

**Conclusion**
There is a clear and consistent decline in new customer acquisition from January to June 2024.
Suggests a need to investigate marketing effectiveness, seasonal demand, or changes in acquisition channels.

<img width="533" alt="image" src="https://github.com/user-attachments/assets/6640d054-4ef1-424b-99e1-0362d7e3a00d" />

### Final Summary & Business Insights
This project showcased the power of the modern data stack for customer retention analytics:
- SQL-driven cohort analysis helped quantify and visualize how quickly customers repurchase.
- Recent cohorts show stronger short-term loyalty but weaker long-term engagement.
- Customer acquisition volume is declining, highlighting a potential area of concern for the business.

### Actionable Takeaways:
Examine strategies contributing to strong retention in May/June.
Address issues behind weak repeat engagement in newer cohorts.
Investigate factors causing acquisition decline and optimize marketing efforts accordingly.

## Final Databricks project with SQL Queries and Visualisation: 
https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/2637955189247778/771333345207615/4634868260923838/latest.html
