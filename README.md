# Part-2 The Look E-commerce business insights
Continuation of the initial exploratory data analysis of this synthetic e-commerce

##  Project Overview
Building upon the [Initial Exploratory Data Analysis (EDA) project](link_to_your_previous_repo_here), this second phase shifts the focus from data exploration to **actionable business intelligence**. 

By performing SQL joins across multiple BigQuery tables (`orders`, `order_items`, `products`, and `users`), I constructed a comprehensive, denormalized master dataset. The primary goal of this project is to act as a Data Analyst consulting for the e-commerce business, extracting strategic insights related to:
*   **Financial KPIs:** Revenue, Profit Margins, and Average Order Value (AOV).
*   **Portfolio Management:** Identifying highly profitable product categories and flagging underperforming brands.
*   **Demographic Profiling:** Analyzing spending behavior across age groups and mathematically testing gender spending differences.
*   **Time Series & Seasonality:** Mapping historical growth and identifying peak seasonal trends for inventory planning.

##  Data Source & Tools
*   **Data Source:** Google BigQuery Public Datasets (`bigquery-public-data.thelook_ecommerce`)
*   **Data Extraction & Merging:** SQL (Google Cloud BigQuery API)
*   **Data Manipulation & Feature Engineering:** Python (Pandas, NumPy)
*   **Data Visualization:** Matplotlib, Seaborn (Custom Executive Dashboards)
*   **Statistical Testing:** SciPy (Welch's T-Test for hypothesis testing)
*   **Environment:** Jupyter Notebook

## Executive Summary
The business is highly profitable, maintaining a strong margin across a massive customer base. However, the distribution of order values shows that the majority of purchases fall below the \$100 mark, highlighting the importance of volume and customer retention.

<img width="1389" height="821" alt="image" src="https://github.com/user-attachments/assets/42e1dc35-858b-4256-b333-c90cb277e8b6" />


<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/388fa517-eaf8-4c25-b4f0-364804e46c1a" />


---

## Product Portfolio Insights (Categories & Brands)
A deep dive into the 26 product categories and 2,717 brands revealed stark contrasts in operational efficiency. 

**Category Performance:**
*   **The Cash Cow:** `Outerwear & Coats` is the absolute best performer, generating the highest Revenue (\$1.33M) and Profit (\$738K), while maintaining excellent margins.
*   **The Margin Extremes:** `Blazers & Jackets` command the highest profit margin overall (61.9%), whereas `Clothing Sets` drag profitability down to a low of 38.4%.

<img width="1489" height="985" alt="image" src="https://github.com/user-attachments/assets/e0111f06-9f51-401d-82a5-106336e34ed6" />


**Strategic Brand Management:**
*   **Top 3 Brands to Prioritize:** *Calvin Klein* (\$106K Profit), *Diesel* (\$96K Profit), and *Carhartt* (\$92K Profit). These brands maintain high volume and solid margins (~50-51%).
*   **Catalog Optimization:** Out of 2,717 brands, over **1,352 brands require review**. Brands like *Nobis* and *Nau* have excellent margins but abysmal sales volume (under 15 units sold). 

---

##  Demographic Insights (Age & Gender)
Analyzing our 79,230 unique users (Ages 12 to 70) uncovered a massive behavioral difference driven by gender, rather than age.

*   **Age Contribution:** The core demographic is the **35-54 age group**, which drives the largest share of the total revenue.
*   **The Gender Gap:** While the revenue split between genders is relatively balanced (53.1% Men, 46.9% Women), a **Welch's T-Test proved a statistically significant difference in spending behavior**. Men consistently spend ~\$10 more per order (\$91+) compared to women (\$81+), regardless of their age group.

<img width="1790" height="635" alt="image" src="https://github.com/user-attachments/assets/db9be593-8389-403e-b337-0262c5cedccb" />


---

## Time Series & Seasonality
*(Note: Synthetic exponential growth patterns were observed. Focus was placed on the last 24 months and historical monthly averages).*

*   **Peak Volume:** March 2026 recorded the highest recent volume, reaching \$561,328 in a single month.
*   **Seasonality Patterns:** Historically, **March is the strongest month** of the year, while **May is the slowest season**.

<img width="1590" height="1180" alt="image" src="https://github.com/user-attachments/assets/e673ded9-3e41-4e3f-863d-436b9307d88c" />


---

## Actionable Business Recommendations
Based on the data extracted and analyzed, I recommend the following strategic actions:

1. **Merchandising & Portfolio Expansion:** Capitalize on the statistically significant Gender AOV gap through inventory planning. Since male shoppers consistently demonstrate a higher willingness to spend per cart (\$91+), the buying team should expand the assortment of premium male-focused brands and high-ticket categories. Matching our inventory to their proven spending behavior will organically increase revenue without relying on exclusionary pricing strategies.
2.  **Supply Chain Optimization:** Conduct a pricing and logistics review on `Clothing Sets` and lower-margin items. If margins cannot be improved, reduce warehouse space allocated to these items in favor of `Outerwear & Coats`.
3.  **Inventory Planning:** Capitalize on the March seasonal peak. Ad-spend and inventory stocking should be aggressively ramped up in late January and February, scaling back slightly heading into the May slump.
4.  **Catalog Trimming:** Discontinue or re-negotiate terms for the worst-performing brands (e.g., "Made in USA") and create dedicated marketing pushes for high-margin but low-volume brands.

---
