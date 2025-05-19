# SQL-Driven Cohort Analysis Pipeline with BigQuery and Databricks

## Objective

The objective of this project was to develop a modern marketing analytics solution focused on understanding customer retention in an e-commerce context. The key business question addressed:

***"How long does it take for customers to make their second purchase, and how does this vary across different customer cohorts?"***

This initiative provided hands-on experience using the modern data stack, spanning from data ingestion and transformation to cohort-based visualisation — ultimately delivering actionable insights into customer behaviour.

## High-Level Workflow
### 1. Data Ingestion
- **Source:** Simulated e-commerce transaction data from a BigQuery table named ecom_orders.
- **Planned Tool:** Fivetran (for syncing GCP Cloud SQL → Databricks).
- **Challenge:** Connection issues between Fivetran and Databricks.
- **Workaround:** Data was manually loaded into Databricks to proceed with analysis.

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
1. Identified each customer's first purchase date.
2. Determined the second purchase date, if available.
3. Calculated the days between the first and second purchases.
4. Saved the transformed dataset as a new table: cohort_analysis.

All analysis and data transformation were performed using **SQL queries** within Databricks.

### 4. Data Visualisation in Databricks Dashboards

### Key Performance Indicators (KPIs)
Based on the analysis of the e-commerce dataset, the following summary metrics were identified:
- Total Customers: 200
- Total Orders: 1,000
- Total Sales: $156,795


Three visualisations were developed to analyse customer behaviour by cohort. Below are the results derived from SQL-based analysis:
## Visualisation 1: Retention Rate by Cohort
<img width="1022" alt="image" src="https://github.com/user-attachments/assets/4f6e1a03-2d58-4678-ae4b-9ac68b1707dc" />

### Result – Trend Over Time in Retention Rate
**Purpose:** To evaluate what percentage of customers from each monthly cohort made a second purchase within 1, 2, and 3 months after their initial purchase.

**Highest Retention Rates by Time Threshold**
- 1-Month Retention: June 2024 cohort – 80%
- 2-Month Retention: June 2024 cohort – 100%
- 3-Month Retention: May & June 2024 cohorts – 100%

**Notable Differences Across Cohorts**
- 1-Month Retention: Ranges from 34.62% (April) to 80.00% (June)
- 2-Month Retention: Overall increase compared to 1-month; June cohort perfect at 100%
- 3-Month Retention: May and June show the strongest loyalty; older cohorts show gradual improvement

**Summary**
1. More recent cohorts (May & June 2024) show significantly higher short-term retention.
2. Older cohorts (February & April 2024) consistently underperform.
3. Indicates **improved customer loyalty** or acquisition quality in recent months.

## Visualisation 2: Repeat Purchase Rate by Cohort
<img width="1023" alt="image" src="https://github.com/user-attachments/assets/00b2b469-8eab-41df-9b15-4f0c6d6040e3" />

### Result – Trends Over Time in Repeat Purchase Rates
**Purpose:** To assess how many customers from each cohort placed a 2nd, 3rd, or 4th order.

**Observations**
- 2nd Order: Consistently high repeat rates; slight dips in Feb & Apr 2024
- 3rd Order: Downward trend in recent cohorts; June cohort drops to 70%
- 4th Order: Clear declining trend from 83.3% (Jan) to 60% (June)

**Summary**
1. 2nd purchase behaviour remains strong across cohorts.
2. 3rd and 4th purchase behaviours **weaken over time**, especially in more recent months.
3. May and June cohorts show **lower long-term engagement**.

**Consideration**
- May/June 2024 cohorts have fewer customers, increasing volatility in rate calculations.
- Despite smaller samples, the downward trend is consistent and notable.

## Visualisation 3: Cohort Size by Month
<img width="1024" alt="image" src="https://github.com/user-attachments/assets/f3e37a39-8ef1-457d-8f28-9eefb4fdf92d" />

### Result – Cohort Size by Month Analysis
**Purpose:** To evaluate customer acquisition volume by month (i.e., cohort size).

**Key Findings**
- Largest Cohort: January 2024 – 66 customers
- Decline Over Time: February (48), March (33), April (27)
- Smallest Cohorts: May (16), June (10)

**Summary**
1. There is a clear and consistent decline in new customer acquisition from January to June 2024.
2. Suggests a need to investigate marketing effectiveness, seasonal demand, or changes in acquisition channels.

## Dashboard
<img width="547" alt="image" src="https://github.com/user-attachments/assets/1ef3fb1e-354b-49b4-9dc0-4f2163eda63e" />

## Final Summary & Business Insights
This project showcased the power of the modern data stack for customer retention analytics:
- SQL-driven cohort analysis helped quantify and visualise how quickly customers repurchase.
- Recent cohorts show stronger short-term loyalty but weaker long-term engagement.
- Customer acquisition volume is declining, highlighting a potential area of concern for the business.

## Actionable Takeaways:
- Examine strategies contributing to strong retention in May/June.
- Address issues behind weak repeat engagement in newer cohorts.
- Investigate factors causing acquisition decline and optimise marketing efforts accordingly.

## Final Databricks project with SQL Queries and Visualisation: [
https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/2637955189247778/771333345207615/4634868260923838/latest.html

## SQL Codebook:
https://github.com/DeepshikhaChhetri/Project-Databricks/blob/e526a332aadd49c0b1cd3b8e22ea09fbab94aa30/SQL-Query

## Presentation Video:

