# Order Fulfillment & Delivery Performance Analysis | Excel

## Project Overview

This project analyzes order fulfillment and delivery performance using Microsoft Excel. The goal was to transform raw e-commerce order data into a structured analysis that could help identify fulfillment trends, evaluate delivery reliability, and highlight areas of operational inefficiency.

The project covers the full Excel analytics workflow, including data cleaning and transformation with Power Query, data quality validation, Excel formulas, PivotTables, exploratory analysis, and dashboard development.

The final dashboard focuses on the reporting period from **January 2017 to August 2018** and provides a concise view of order volume, delivery performance, and fulfillment efficiency.

---

## Business Questions

The analysis was designed to answer the following questions:

- How did order volume change over time?
- What percentage of evaluable deliveries arrived on time?
- How long did the average order take to move through the fulfillment process?
- How does typical fulfillment time compare with the overall average?
- Which stage of the fulfillment process accounted for the most time?
- Were periods of longer fulfillment times associated with weaker on-time delivery performance?

---

## Tools & Excel Skills

- Microsoft Excel
- Power Query
- PivotTables
- PivotCharts
- Excel Tables and Structured References
- COUNTIF / COUNTIFS
- AVERAGEIFS
- MEDIAN
- FILTER
- Date calculations
- Conditional logic
- Data quality validation
- Dashboard design
- Data visualization

---

## Dataset

The project uses an e-commerce order dataset containing approximately 99,000 order records, including order purchase, approval, carrier handoff, customer delivery, estimated delivery, and order status information.

**Source:** [Customer Order Delivery Dataset - Kaggle](https://www.kaggle.com/datasets/zeynepustun/customer-order-delivery-dataset)

---

## Data Preparation

The raw order data was cleaned and transformed using Power Query before analysis.

Key preparation steps included:

- Reviewed missing values across order and delivery timestamps
- Created an `Order Month` field for monthly trend analysis
- Calculated approval duration in hours
- Calculated carrier handoff duration in hours
- Calculated delivery transit duration in hours
- Calculated total fulfillment duration in hours
- Calculated delivery variance in days
- Classified completed deliveries as `On Time` or `Late`
- Preserved missing delivery information rather than replacing it with artificial values
- Investigated inconsistent timestamp sequences in which carrier handoff occurred before order approval
- Created a `Handoff Data Quality` flag to distinguish valid, invalid, and unavailable handoff records
- Excluded invalid handoff sequences from handoff-time KPI calculations while retaining the original records

This approach allowed questionable records to remain traceable without allowing known data-quality issues to distort relevant performance metrics.

---

## Fulfillment Metrics

The analysis separated the fulfillment process into several stages:

**Order Purchase → Order Approval**

**Order Approval → Carrier Handoff**

**Carrier Handoff → Customer Delivery**

**Order Purchase → Customer Delivery**

This made it possible to analyze both overall fulfillment performance and individual stages of the process.

---

## Dashboard

<img width="896" height="745" alt="Order Fullfillment Dashboard" src="https://github.com/user-attachments/assets/2fae1551-4685-4f5d-84f5-c5bf7f2a7ecd" />

The final dashboard includes:

- Total Orders
- On-Time Delivery Rate
- Average Fulfillment Time
- Median Fulfillment Time
- Average Delivery Transit Time
- Monthly Order Volume
- Monthly On-Time Delivery Rate
- Delivery Status Breakdown
- Average Fulfillment Time by Month

### Reporting Period

The dashboard focuses on **January 2017 through August 2018**.

The underlying dataset contains additional records outside this period. The dashboard uses January 2017 through August 2018 as the primary reporting window because earlier months contained very limited observations and later months represented incomplete reporting periods. All source records were retained during data preparation and exploratory analysis.

---

## Key Findings

### 1. Overall delivery performance remained strong

Approximately **91.9% of evaluable deliveries were completed on time** during the reporting period.

### 2. Delivery performance weakened significantly in early 2018

The monthly on-time delivery rate reached its lowest point at approximately **78.6% in March 2018**, before recovering to approximately **94.7% in April 2018**.

### 3. Longer fulfillment times coincided with weaker delivery performance

Average fulfillment time increased to approximately **406.7 hours in February 2018** and **391.2 hours in March 2018**, coinciding with the period of weaker on-time delivery performance.

### 4. Delivery transit represented the largest portion of fulfillment time

Process-level analysis showed that the carrier-to-customer delivery stage accounted for substantially more time than order approval.

This suggests that changes in overall fulfillment performance were more closely associated with delivery transit than with the initial order approval stage.

### 5. Fulfillment performance improved after March 2018  

Fulfillment speed improved substantially after **March 2018**, with average fulfillment time declining to approximately **185.6 hours by August 2018**. However, monthly on-time delivery rates continued to fluctuate, indicating that shorter average fulfillment times did not consistently correspond with higher on-time performance.

---

## Average vs. Median Fulfillment Time

The analysis produced an average fulfillment time of approximately **300.9 hours**, while the median was approximately **245.0 hours** during the reporting period.

The difference between these measures indicates that unusually long fulfillment periods increased the overall average. For this reason, both the average and median were included to provide a more balanced view of the typical customer fulfillment experience.

---

## Data Quality Considerations

During the analysis, some records contained a carrier handoff timestamp that occurred before the corresponding order approval timestamp.

Rather than modifying the original timestamps without supporting information, these records were flagged as invalid sequences.

Carrier handoff performance calculations were restricted to records classified as valid, while the original observations remained preserved in the cleaned dataset.

Orders without sufficient delivery information were also left unclassified rather than being automatically treated as on-time or late deliveries.

---

## Project Outcome

This project demonstrates an end-to-end Excel analytics workflow, from raw data preparation and data-quality investigation to KPI development, exploratory analysis, and dashboard reporting.

The analysis was designed to go beyond visualizing results by investigating unusual records, validating calculations, comparing average and median performance, and examining which stages of the fulfillment process were most closely associated with delivery performance.

---

> **Note:** The complete Excel workbook contains approximately 99,000 order records and exceeds GitHub's browser upload size limit. The full workbook has therefore not been included in this repository. The dashboard, methodology, calculations, and key findings are documented here.
