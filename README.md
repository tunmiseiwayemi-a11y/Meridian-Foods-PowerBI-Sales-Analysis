# Meridian-Foods-PowerBI-Sales-Analysis

MERIDIAN FOODS & DISTRIBUTION
Sales Performance Analysis, 2024
 
https://drive.google.com/drive/folders/1-2luZvb5H5mhbi6KXfY2r2VDi3pIcFwL?usp=drive_link

A Business Intelligence Case Study Developed in Microsoft Power BI

Prepared by: Oluwatunmise Esther Iwayemi 
2026

Executive Summary

This report presents a Power BI-based sales performance analysis of Meridian Foods & Distribution, a fictional grocery distribution business created to demonstrate business intelligence and data analytics capability. The analysis draws on a transactional dataset covering customer orders, salesperson activity, regional distribution, product category performance, and shipping operations across the 2024 financial year.
Data preparation, exploratory analysis, and interactive visualisation were developed using Microsoft Power BI. The resulting dashboard consolidates key performance indicators, regional and product trends, salesperson contribution, and monthly revenue movement into a single decision-oriented view, supported by the detailed visual and written analysis contained in this report.

The analysis indicates that Meridian Foods & Distribution generated total revenue of approximately $435,065.56 for the 2024 financial year, driven by strong performance in the Beverages category, the Northern and Eastern sales regions, and a small group of high-value customers and salespeople. December and June were the strongest months, while February and November were consistently weaker, suggesting a seasonal pattern that the organisation could plan around.

The strongest areas identified include the Beverages product category, the Northern region, and the performance of salesperson Nancy Freehafer, all of which significantly outpaced other segments. The main weaknesses identified include a concentration of revenue among a small number of customers and salespeople, underperformance in the Western and Southern regions, low performance in the Canned Meat category, and data quality issues including a shipping fee discrepancy and a small number of unclassified transactions.
Management should consider targeted seasonal promotions for historically weak months, structured coaching and knowledge-sharing among the sales team, closer investigation of regional performance drivers, and continued investment in data quality controls as the underlying dataset scales. These themes are developed in detail in the findings and recommendations sections of this report.

1. Introduction

   <img width="1298" height="733" alt="Dashboard" src="https://github.com/user-attachments/assets/ea44cba3-47b7-41fe-8e21-cc82c9b5a499" />
   

1.1 Background
   
Meridian Foods & Distribution operates a business-to-business grocery distribution model, supplying a range of grocery products to customer companies across multiple U.S. states, with occasional shipments to international destinations. As the business has grown, understanding which regions, products, customers and salespeople drive performance has become central to planning for the year ahead.

1.2 Business Context
   
This report examines transactional sales data for the 2024 financial year, covering order-level detail, customer information, salesperson assignment, regional territory, product category, shipping activity and payment type. The dataset supports analysis of revenue performance, operational efficiency, and customer behaviour across the business.

1.3 Project Objectives
   
Assess overall sales performance, including revenue trends across months, regions, states and cities.
Identify top-performing and underperforming customers, salespeople, product categories and shipping partners.
Surface operational inefficiencies, including shipping and data quality issues.
Examine relationships between order volume, revenue, shipping fees and payment behaviour.
Translate findings into practical, prioritised recommendations for 2025 planning.

1.4 Key Business Questions
   
Which regions, product categories and salespeople generate the most revenue?
How does revenue move across the calendar year, and where are the seasonal peaks and troughs?
Which customers and cities account for the largest share of revenue, and how concentrated is this contribution?
Where do data quality or shipping issues affect the reliability of reported figures?

1.5 Scope of Analysis

The analysis covers the full 2024 financial year unless otherwise stated. Where the Power BI dashboard labels a panel with a shorter reporting window, this is explicitly flagged and reconciled against the full-year findings in Section 6.6, so that figures are not inadvertently mixed across different time periods.

3. Data Story and Dataset Overview

   
2.1 Dataset Description
   
The dataset captures the full transaction lifecycle for Meridian Foods & Distribution's 2024 grocery sales operation. Each record begins with a unique order identifier and order date, allowing trend analysis across the year. Customers are primarily U.S.-based businesses, identified by customer ID and name, with associated city, state, ZIP or postal code and country information.
Salespeople are assigned to specific regional territories and are responsible for outreach and order fulfilment, with shipped dates logged to track delivery efficiency. Shipments are managed by named shipping partners and include both domestic and international destinations, each with its own address detail.

2.2 Key Variables
   
Order-level fields: Order ID, Order Date, Shipped Date
Customer fields: Customer ID, Customer Name, City, State, ZIP/Postal Code, Country/Region
Sales fields: Salesperson, Region
Shipping fields: Shipper Name, Ship Address, Ship City, Ship State, Ship ZIP/Postal Code, Ship Country/Region
Product fields: Product Name, Category, Unit Price, Quantity, Revenue, Shipping Fee
Transaction field: Payment Type

2.3 Business Relevance of the Data
   
Because revenue is a function of unit price, quantity and product category, and because shipping fees vary by product type rather than volume alone, the dataset supports analysis that connects operational detail (shipping, regional assignment, payment method) directly to commercial outcomes (revenue, customer concentration, product performance). This makes it well suited to a Power BI model built around a small number of clear, decision-oriented measures.

4. Data Preparation and Quality Assessment

   
Prior to building the Power BI data model, the underlying dataset was reviewed and cleaned to ensure that reported figures could be trusted for decision-making.
3.1 Data Cleaning
The dataset was loaded and reviewed for blank cells, outlier values such as negative quantities or revenue, and dates falling outside the 2024 financial year. A copy of the original data was preserved separately before any cleaning was applied, so that the source data remained auditable.

3.2 Missing Values
   
Blank entries in critical fields, including revenue, shipping fee and shipped date, were identified and addressed, either through removal or through reasonable imputation based on comparable records (for example, estimating a shipping fee from similar products where a value was missing).

3.3 Duplicate Records
   
Duplicate records were identified using order ID and order date as key fields. This step reduced the dataset by approximately 2 percent without removing any unique orders, improving the reliability of downstream aggregations.

3.4 Data Type Standardisation
   
Text fields such as region, product category and payment type were standardised for consistent capitalisation and spelling, and extra whitespace was removed. Date and numeric fields were converted to proper date and number formats to support accurate calculation and time-based analysis.

3.5 Validation and Consistency Checks
   
Cross-checks were performed to confirm that shipped dates followed order dates in a logical sequence, that revenue values were consistent with unit price multiplied by quantity, and that city, state and country fields aligned correctly. One shipping fee discrepancy of $10.00, associated with salesperson Anne Larsen, and one unclassified product category record valued at approximately $30.00 were identified during this process and are flagged in Section 8 as data quality items for follow-up.
3.6 Data Modelling / Preparation for Power BI
Following cleaning, the dataset was structured for use in Power BI, with fields organised into a working data table suitable for building the report's core measures: total revenue, quantity purchased, and revenue broken down by region, salesperson, product, state, city and month. The model supports the slicers and visuals presented in the dashboard in Section 6, allowing the underlying figures to be filtered interactively by salesperson, product category and region.

5. Analytical Approach

   
4.1 Exploratory Analysis

Exploratory analysis was used to establish the overall shape of the dataset before deeper investigation, including the distribution of revenue across regions, months, product categories, customers and salespeople, and the general spread of individual transaction values.

4.2 Key Performance Indicators
Total Revenue: aggregate revenue generated across all transactions in the reporting period.
Quantity Purchased: total unit volume of products sold.
Regional Lead by Revenue: the region contributing the largest share of total revenue.
Top Product, Customer and Salesperson by Revenue: the highest-contributing entity in each category.
4.3 Measures and Calculations
Core measures were built around summation of revenue and quantity, grouped by the relevant dimension (region, month, salesperson, product, state or city). Percentage share calculations, such as each region's proportion of total revenue, were derived directly from these summed values.


4.4 Analytical Questions
   
Which product category generates the highest revenue, and which the lowest?
How does revenue move month to month, and which months are consistently weak?
Which salespeople and customers contribute disproportionately to total revenue?
How does performance vary by region, state and city?
Where do shipping timelines, fees or data quality issues affect operational efficiency?

6. Sales Performance Analysis
   
5.1 Overall Revenue Performance
   
Meridian Foods & Distribution generated total revenue of approximately $435,065.56 for the 2024 financial year, alongside a total purchased quantity of approximately 21,000 units. This places the business on a solid overall footing, though, as the following sections show, this revenue is not evenly distributed across regions, products, customers or salespeople.

Figure 2: Key Performance Indicator Overview — Total Revenue, Quantity Purchased and Regional Lead

The KPI overview summarises the year at a glance: total revenue of 435.04K, a purchased quantity of 21K units, and the North confirmed as the leading region by revenue. This view is intended as the entry point of the dashboard, from which a user can drill into the more detailed regional, salesperson and product visuals that follow.

5.2 Monthly Revenue Trends

Figure 3: Monthly Revenue Trend, 2024

Revenue followed a fluctuating pattern across the year rather than a steady upward or downward trend. January opened at a moderate $32,907.84, before February recorded the lowest revenue of the year at $19,985.50. A partial recovery through March and a dip in April preceded a stronger run into May and June, which peaked at $55,601.61, the second-highest month of the year.
A sharp decline followed in July, down to $27,318.54, with a gradual recovery through August and September before October rose to $53,033.59. November declined again to $31,773.43, before December closed the year as the strongest month, at $66,642.78. The analysis indicates a recurring seasonal pattern in which February and November are consistently weak and December and June are consistently strong. Further investigation should focus on the specific drivers of the July decline, such as competitive activity or reduced demand, since this is the sharpest single-month drop in the dataset.

5.3 Salesperson Performance

Figure 4: Salesperson Revenue Contribution (Top Performers)

Nancy Freehafer was the leading salesperson for the year, generating $104,252.34 in revenue, well ahead of Anne Larsen ($93,858.33), Andrew Cencini ($67,180.50) and Mariya Sergienko ($42,370.88). At the other end of the scale, Jan Kotas generated the lowest revenue among all salespeople, at $16,350.50, followed by Robert Zare at $32,530.60.
This performance gap is substantial, with the top salesperson generating more than six times the revenue of the lowest performer. This pattern highlights an opportunity for structured knowledge-sharing rather than an assumption about individual effort or ability; further investigation into territory size, customer mix and account tenure would be needed to fully explain the difference, and this is reflected in the recommendations in Section 9.

5.4 Customer Performance

Revenue is concentrated among a relatively small number of customers. Company D was the top customer for the year, generating $67,180.50, followed by Company H ($50,208.35) and Company BB ($43,713.00). The remaining top-ten customers, in descending order, were Company F ($37,428.00), Company A ($36,839.99), Company I ($32,530.60), Company J ($29,133.01), Company Z ($28,208.25), Company C ($27,005.38) and Company K ($21,937.08).
The three leading customers account for a disproportionate share of top-ten revenue compared with the remaining seven, which represents a concentration risk: the loss of any one of these accounts would have a material impact on overall revenue. This finding supports the customer retention recommendations set out in Section 9.


5.5 Regional Performance

Figure 5: Regional Revenue Distribution, 2024

The Northern region was the clear leader in 2024, generating $141,680.34 in revenue, equivalent to approximately 32.6 percent of total revenue. The Eastern region followed with $108,275.51 (24.9 percent), ahead of the Southern region at $93,858.33 (21.6 percent) and the Western region at $91,251.98 (21.0 percent), the lowest-performing territory.
The result may indicate stronger customer density, pricing effectiveness or sales activity in the North and East, though the data alone cannot confirm the specific cause. Further investigation into customer mix, order value and sales effort by region would be required to determine the drivers of this performance gap before any changes are made to resource allocation.


5.6 Product and Category Performance

Beverages was the standout product category for 2024, generating $110,577.11, substantially ahead of Sauces ($69,000.00), Jams and Preserves ($51,541.00), Dairy Products ($33,129.60) and Dried Fruit & Nuts ($27,999.50). Canned Meat generated the lowest category revenue at $25,465.60. A small number of transactions, together valued at approximately $30.00, could not be assigned to a category during data preparation and were traced to a shipping-related data entry error rather than a genuine product gap.

Figure 6: Product Revenue Performance (Top Individual Products)

At the individual product level, Coffee was the strongest single product shown on the dashboard, contributing approximately $75,486.00, followed by Curry Sauce ($69,000.00, consistent with the Sauces category total), Marmalade ($41,391.00) and Mozzarella ($33,129.60, consistent with the Dairy Products category total). This product-level view adds useful detail beneath the category totals, showing that category performance is often driven by one or two dominant products rather than being spread evenly across a category's full product range.

5.7 State Performance

Figure 7: State-Level Revenue Performance (Leading States)

New York was the leading state by revenue, at $67,180.50, ahead of Oregon ($50,208.35) and Florida ($50,145.33). Further down the ranking, Tennessee ($43,713.00), Illinois ($41,095.01), Wisconsin ($37,428.00), Washington ($36,839.99), Utah ($32,530.60) and California ($27,005.38) recorded progressively lower revenue, with Idaho ($17,204.00) and Nevada ($15,365.50) the weakest states in the dataset.
From a business perspective, New York's clear lead suggests it is currently the strongest addressable market, while the sizeable gap down to Nevada and Idaho points to either limited market penetration or lower demand in those states. This presents an opportunity to examine what is working in New York and Oregon and to assess whether elements of that approach are transferable to the weaker states.

5.8 City Performance

At the city level, New York again led with $67,180.50 in revenue, ahead of Portland ($50,208.35) and Miami ($50,145.33), which recorded very similar totals. Memphis ($43,713.00), Chicago ($41,095.01) and Milwaukee ($37,428.00) completed the top six shipping cities by revenue, with Milwaukee the weakest of this group. The same six cities also make up the top five to six cities by overall revenue, reinforcing New York's position as the business's strongest single market and highlighting Portland and Miami as a closely matched second tier worth further investment.
5.9 Transaction Value Distribution
The majority of individual transactions were relatively modest in value: 218 transactions fell within the $0 to $1,000 range, followed by a sharp drop to 85 transactions between $1,000 and $2,000, and 31 transactions between $2,000 and $3,000. Transaction counts continued to decline through the higher value bands, with 24 transactions between $3,000 and $4,000, 8 between $4,000 and $5,000, 2 between $6,000 and $7,000, and a single transaction between $7,000 and $8,000.
This distribution indicates that Meridian Foods & Distribution's revenue base is built primarily on a high volume of smaller transactions rather than a small number of very large orders, which has implications for how promotional and loyalty strategies should be designed, as discussed in Section 9.

6. Power BI Dashboard
   
6.1 Dashboard Overview
   
The Power BI Sales Performance Dashboard consolidates the year's key results into a single interactive view, allowing a user to move from headline KPIs to regional, salesperson, product and monthly detail without leaving the page. The dashboard is built around three interactive slicers (salesperson, product inventory and regional domain), three KPI cards, and five supporting visuals covering regional distribution, monthly trend, salesperson performance, product performance and state-level performance.
6.2 Dashboard Design and Navigation
The layout follows a left-to-right, top-to-bottom reading order that mirrors how a manager would naturally interrogate the data: filters and narrative callouts sit along the top and left edge, core KPI cards occupy the centre, and supporting trend and breakdown visuals are arranged around them. A Home button in the top navigation bar indicates that this dashboard forms one page within a larger multi-page Power BI report.
6.3 Key Performance Indicators
Three KPI cards anchor the dashboard: Total Revenue (435.04K), Quantity Purchased (21K) and Regional Lead by Revenue (North). Each card pairs a large headline figure with a simple supporting icon and a short descriptive label, which keeps the top-level read fast and unambiguous.

6.4 Interactive Filters / Slicers
   
The dashboard provides three slicers, allowing the report to be filtered by Company Salesperson, Company Product Inventory and Company's Regional Domain. Each slicer is set to "All" by default, showing the full dataset, and can be narrowed by a user to isolate the performance of a single salesperson, product or region.

6.5 Dashboard Insights
   
The dashboard includes short narrative callouts alongside the filters, for example a note to prioritise coaching for the lowest-performing salesperson and to focus marketing activity on the weaker months of February and November. These callouts translate the underlying figures into the same actionable language developed in full in Section 9 of this report.

6.6 Reporting Period and Data Consistency
   
Several panel subtitles within the dashboard reference "Q1" (for example, "Regional Trend by Revenue Generated in Q1"). However, the underlying values shown for total revenue (435.04K), the twelve-month trend line, and the regional and salesperson breakdowns reconcile closely with the full 2024 annual figures established in Sections 5.1 to 5.5 of this report. On this basis, the "Q1" wording is treated as a residual label carried over from the dashboard template rather than an indication that the figures are restricted to the first quarter. All figures in this report are presented as full-year 2024 results, and this distinction is noted here so that readers do not mistake the dashboard's panel titles for a different reporting period.

6.7 Complete Dashboard

Figure 1: Power BI Sales Performance Dashboard — Meridian Foods & Distribution

7. Dashboard Design Analysis
   
The dashboard uses a dark navy blue theme throughout, with lighter blue panels used to group related visuals and pale cream or off-white tones used for the chart elements themselves (bars, donut segments and highlight boxes). This creates strong contrast between the data and its background, so that the charts remain the most visually prominent element on each panel.
Visual hierarchy is managed through size and position rather than colour alone: the three KPI cards sit at the centre of the page in the largest, boldest text on the dashboard, drawing the eye first. Supporting visuals are arranged around this core, with the regional donut chart and product showcase table given the top and right-hand positions typically associated with secondary but still high-priority information.
The overall layout supports a natural analytical path: a user starts at the KPI cards for a high-level read of performance, moves to the regional donut chart and state performance panel to understand where that performance is concentrated, reviews the salesperson bar chart and product showcase table to identify who and what is driving results, and finishes with the monthly trend line to understand how performance has moved through the year. The three slicers at the top of the page allow this same path to be repeated for any individual salesperson, product or region.
Based on the screenshot provided, the dashboard's confirmed functionality includes cross-filtering via slicers, KPI summary cards, and multiple chart types (donut, bar, line and table visuals). No claims are made in this report about drill-through pages, bookmarks, tooltips, automated data refresh, forecasting or other advanced Power BI functionality, as these cannot be confirmed from the available material.

9. Key Findings and Business Insights
   
8.1 Revenue and Seasonality

Total 2024 revenue reached approximately $435,065.56, with December ($66,642.78) and June ($55,601.61) as the strongest months, and February ($19,985.50) and November ($31,773.43) as the weakest.
The sharp decline between June and July ($55,601.61 to $27,318.54) is the single largest month-on-month drop in the dataset and warrants dedicated investigation.

8.2 Concentration Risk

The top three customers (Company D, Company H and Company BB) contribute a disproportionate share of top-ten customer revenue, representing a concentration risk if any one account were lost.
Salesperson performance is similarly concentrated, with Nancy Freehafer generating more than six times the revenue of the lowest-performing salesperson, Jan Kotas.

8.3 Regional and Geographic Patterns

The Northern and Eastern regions together account for over 57 percent of total revenue, while the Southern and Western regions lag behind.
New York is the strongest single state and city by a clear margin, with Oregon, Florida, Portland and Miami forming a closely matched second tier.

8.4 Product Performance

Beverages is the leading category by a wide margin, while Canned Meat is the weakest, and a small number of transactions could not be assigned a category due to a data entry issue.
At the individual product level, Coffee, Curry Sauce, Marmalade and Mozzarella are the leading contributors within their respective categories.

8.5 Data Quality

A $10.00 shipping fee discrepancy was identified in transactions associated with salesperson Anne Larsen.
Approximately $30.00 in revenue could not be mapped to a valid product category, traced to a shipping-related data entry error.
Deduplication reduced the working dataset by approximately 2 percent without affecting genuine unique orders.

10. Recommendations and Action Plan
    
Recommendations are grouped into seven categories below. Where the original analysis referenced a specific percentage improvement, this is retained here as a proposed target rather than a guaranteed outcome, since it has not been validated against actual post-implementation results.
A. Revenue Growth

Issue

Recommended Action

Expected Business Benefit

Priority
Timeline
February and November revenue consistently trail every other month of the year.
Plan and launch targeted seasonal promotions ahead of both months, with marketing materials prepared at least one month in advance.
Proposed target: uplift in February revenue relative to the $19,985.50 baseline.
High
Planning by end of January; repeat ahead of November
December is the strongest month but has not been deliberately optimised.
Introduce structured December promotions, including limited discounts and free shipping thresholds on larger orders.
Proposed target: 12–15% year-on-year growth in December revenue.
High
Planning from Q3 each year

B. Sales Team Performance

Issue
Recommended Action

Expected Business Benefit

Priority
Timeline
Wide performance gap between the top salesperson ($104,252.34) and the lowest ($16,350.50).
Introduce a structured coaching and mentorship programme pairing lower-performing salespeople with top performers, supported by monthly best-practice sessions.
Proposed target: 10% revenue uplift among coached salespeople.
Medium
First session within 1 month; ongoing
No formal recognition structure exists for high sales performance.
Introduce a tiered bonus structure for sales above defined thresholds, alongside public recognition of top performers.
Proposed target: 12% increase in overall sales value.
High
Immediate

C. Product Strategy

Issue
Recommended Action
Expected Business Benefit
Priority
Timeline
Canned Meat is the lowest-performing product category ($25,465.60).
Evaluate repositioning, bundling or reduced allocation for Canned Meat based on further demand analysis.
Improved category-level profitability.
Medium
Next quarter
Beverages significantly outperforms all other categories.
Trial complementary product bundles (for example, snacks) alongside Beverages to extend its strong demand to adjacent categories.
Proposed target: 10% increase in bundled-category sales.
Medium
Within 4 months

D. Regional Strategy

Issue
Recommended Action
Expected Business Benefit
Priority
Timeline
Western and Southern regions trail the North and East by a wide margin.
Review Northern and Eastern pricing, staffing and customer engagement practices to identify elements that could be tested in the Western and Southern regions.
Narrowing of the regional revenue gap.
Medium
Within 2 quarters
North and East already account for the majority of revenue.
Maintain prioritised investment in these regions while regional strategy work is carried out elsewhere.
Sustained regional revenue leadership.
High
Ongoing

E. Customer Retention

Issue
Recommended Action
Expected Business Benefit
Priority
Timeline
Top three customers represent a concentration risk.
Introduce dedicated account management and loyalty benefits for the top-tier customer accounts.
Improved revenue stability from key accounts.
High
Immediate
Lower-ranked top-ten customers (e.g. Company K) generate materially less than the leading accounts.
Run targeted outreach and tailored offers to grow underperforming key accounts.
Proposed target: measurable account growth within 1 quarter.
Medium
Next quarter
Limited structured insight into customer preferences.
Introduce a customer feedback survey programme to capture preferences and satisfaction.
Proposed target: 10% increase in sales via tailored offerings.
Medium
Within 3 months

F. Logistics / Shipping

Issue
Recommended Action
Expected Business Benefit
Priority
Timeline
A $10.00 shipping fee discrepancy was identified in the Southern region.
Conduct a review of the shipping fee calculation and data entry workflow, including relevant staff training.
Improved billing accuracy and customer trust.
High
Immediate
Milwaukee and Chicago are the weakest of the top shipping cities.
Review logistics and delivery service quality in these cities to identify improvement opportunities.
Improved delivery performance and city-level revenue.
Low–Medium
Within 4 months

G. Data Quality

Issue
Recommended Action
Expected Business Benefit
Priority
Timeline
A small number of transactions (approximately $30.00) could not be assigned a valid product category.
Implement scheduled data quality checks within the Power BI data preparation workflow to catch unclassified records earlier.
More reliable category-level reporting.
Medium
Ongoing


10. Conclusion
    
The 2024 performance of Meridian Foods & Distribution reflects a fundamentally healthy grocery distribution business, generating approximately $435,065.56 in revenue across a broad base of transactions. Beverages, the Northern and Eastern regions, and a small number of high-performing customers and salespeople, led by Nancy Freehafer, were the principal drivers of this result.
At the same time, the analysis indicates clear areas for attention: a recurring seasonal dip in February and November, a sharp and unexplained decline between June and July, meaningful concentration risk among top customers and salespeople, and a small number of data quality issues that, while minor in scale, should be addressed as the dataset continues to grow.
The Power BI dashboard developed for this project consolidates these findings into a single interactive view, supporting faster, more consistent decision-making than a static report alone. Acting on the prioritised recommendations in Section 9, particularly around seasonal promotions, sales coaching and regional investigation, would give Meridian Foods & Distribution a clear, evidence-based path toward stronger and more evenly distributed performance in the year ahead.

12. References / Appendix
    
11.1 Data Sources

The analysis is based on a transactional grocery sales dataset covering order, customer, salesperson, shipping and product information for the 2024 financial year. The dataset was prepared and modelled internally for the purposes of this project.
11.2 Tools Used
Microsoft Power BI — data modelling, measure development and dashboard visualisation.
Microsoft Excel— initial data cleaning and validation prior to import.

11.3 List of Figures
Figure 1: Power BI Sales Performance Dashboard — Meridian Foods & Distribution
Figure 2: Key Performance Indicator Overview
Figure 3: Monthly Revenue Trend, 2024
Figure 4: Salesperson Revenue Contribution (Top Performers)
Figure 5: Regional Revenue Distribution, 2024
Figure 6: Product Revenue Performance (Top Individual Products)
Figure 7: State-Level Revenue Performance (Leading States)
11.4 Disclaimer
Meridian Foods & Distribution is a fictional company. This report was produced as a data analytics and business intelligence portfolio project and does not represent the real, publicly reported performance of any organisation.
