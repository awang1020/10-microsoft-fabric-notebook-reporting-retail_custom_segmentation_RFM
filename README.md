🛍️ Customer Segmentation with RFM Analysis — Microsoft Fabric & Power BI
📌 Project Overview
This project is a customer segmentation analysis using the RFM (Recency, Frequency, Monetary) model, built on Microsoft Fabric with data modeling in PySpark and Power BI for visual storytelling.

It aims to help marketing teams identify customer behavior patterns and develop targeted strategies to increase engagement, retention, and revenue.

🔧 Tools & Technologies
Stack	Usage
Microsoft Fabric	DataLake, Lakehouse, Delta tables
PySpark (Spark)	Data preparation & processing
Power BI	Reporting and dashboard creation
Python / Pandas	Exploratory data analysis & feature eng.
GitHub	Project version control & documentation

🧮 RFM Model Explained
Recency (R): How recently a customer made a purchase

Frequency (F): How often they purchase

Monetary (M): How much money they spend

Each customer is scored on a scale (e.g. 1–5), and segments are created based on combined scores (RFM_Score) and clustering (KMeans).

📈 Segments Identified
Segment Name	Description
At Risk	Haven’t purchased in a long time, low spend
Big Spenders	High value, few recent purchases
Frequent Low Spenders	Buy often, lower spend per purchase
Recent Customers	New clients with good potential

🗂️ Data Sources
Retail transaction dataset uploaded to Fabric Lakehouse (retail_sales_dataset.csv)

Columns:

date, customer_id, totalamount, transactionid, age, gender, productcategory, etc.

🛠️ Key Steps
1. Data Cleaning & Preparation
Standardization of column names

Generation of customer_id if missing

Aggregation by customer: Recency, Frequency, Monetary

2. RFM Scoring
Quartile-based scoring for R, F, and M

Combined score (RFM_Score)

Custom logic for business segments

3. Clustering (KMeans)
RFM scores standardized and passed into KMeans (k=4)

Segments renamed for business readability

4. Joining Enriched Data
Joining RFM output with customer info (age, gender, nb_transactions)

Stored as a consolidated table: customer_segmentation

5. Power BI Report
Scorecards: Total clients, Total Revenue, Distinct Segments, Avg Spend

Donut chart: Clients by Segment

Bar charts:

Spend by Segment and Gender

Spend by Segment and Age Group

Table: Segment-level averages (monetary, frequency, recency)

📊 Sample Dashboard Preview
(You can paste a screenshot of your Power BI dashboard here in the repo)

📁 Folder Structure
bash
Copier
Modifier
├── data/                        # Retail dataset CSV
├── notebooks/                  # Fabric Notebooks (PySpark)
├── powerbi_report/             # Power BI report (.pbix)
├── visuals/                    # Screenshots of dashboard
├── README.md
🚀 Next Steps & Recommendations
Automate RFM updates weekly via Fabric pipelines

Add other customer features (e.g. tenure, category preference)

Enrich with external data (demographics, surveys)

Deploy Power BI Embedded or App for marketing team access
