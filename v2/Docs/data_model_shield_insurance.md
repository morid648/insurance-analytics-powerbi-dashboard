# Data Model

## Overview
The Shield Insurance Analytics dashboard follows a star schema data model optimized for Power BI reporting performance and scalable analytics.

---

## Fact Tables

### fact_premiums
Stores transactional premium and policy sales data.

#### Key Columns
- customer_code
- policy_id
- date
- final_premium_amt(INR)
- Channel
- Channel Group
- Medium
- sales_mode

#### Business Purpose
Primary revenue and customer acquisition table.

---

### fact_settlements
Stores settlement and payout-related information.

#### Key Columns
- age
- settlement %

#### Business Purpose
Used for risk analysis and payout exposure calculations.

---

## Dimension Tables

### dim_customer
Stores customer demographic details.

#### Key Columns
- customer_code
- city
- Age
- Age Group
- dob
- Settlement%

#### Business Purpose
Supports customer segmentation and demographic analysis.

---

### dim_date
Stores date intelligence attributes.

#### Key Columns
- date
- mmm_yy
- Sort_Month
- week_no
- day_type

#### Business Purpose
Supports time intelligence calculations and trend analysis.

---

### dim_policies
Stores policy-level information.

#### Key Columns
- policy_id
- base_coverage_amt(INR)
- base_premium_amt(INR)

#### Business Purpose
Supports premium and coverage analysis.

---

### Age Group Table
Stores custom age segmentation categories.

#### Key Columns
- Age Group
- Sort Order

#### Business Purpose
Used for custom sorting and demographic reporting.

---

### Waterfall Category
Helper table used for waterfall chart visualization.

#### Key Columns
- Category
- Sort_Order
- Waterfall Value
- WF Value

#### Business Purpose
Supports revenue vs settlement waterfall analysis.

---

## Relationships

### Active Relationships
- dim_date[date] → fact_premiums[date]
- dim_customer[customer_code] → fact_premiums[customer_code]
- dim_policies[policy_id] → fact_premiums[policy_id]

### Analytical Relationships
- dim_customer used for customer segmentation.
- dim_date used for MoM and YoY calculations.
- fact_settlements linked logically for risk analysis.

---

## Calculated Columns

### Age Group
Used to bucket customers into age segments:
- 18–24
- 25–30
- 31–40
- 41–50
- 51–65
- 65+

### Channel Group
Classifies channels into:
- Online
- Offline

### Month Sort
Custom sort column for chronological month ordering.

### Revenue Bucket
Used for revenue segmentation and trend analysis.

---

## Dashboard Architecture

### Executive Pulse
Focuses on:
- Revenue performance
- Customer growth
- Settlement risk
- Channel contribution

### Risk Exposure
Focuses on:
- Settlement risk
- Net revenue impact
- High-risk customers
- Age-group risk distribution

### Channel Intelligence
Focuses on:
- Online vs offline revenue
- Adoption trends
- Channel sales analysis
- Premium uplift analysis

### Customer DNA
Focuses on:
- Revenue per customer
- Customer hotspots
- Age-group contribution
- Customer segmentation

---

## Time Intelligence Features

### Implemented Metrics
- MoM Revenue Growth %
- YoY Revenue Growth %
- LM Revenue
- LY Revenue
- MoM Customer Growth %
- MoM Policies Growth %

### Supporting Date Logic
Implemented using:
- DATEADD
- CALCULATE
- DIVIDE
- Time-based filtering

---

## Visualization Techniques Used

- KPI Cards
- Trend Line Charts
- Donut Charts
- Waterfall Charts
- Heatmaps
- Clustered Bar Charts
- Stacked Flow Visuals
- Dynamic Insight Text

---

## Business Insights Generated

- Online channels contribute significantly to premium revenue.
- Settlement exposure heavily impacts retained earnings.
- Customers aged 31–50 generate the highest revenue contribution.
- Delhi NCR is the top-performing city by revenue.
- Revenue decline trends require customer retention intervention.
- High settlement ratios indicate elevated risk exposure in older age groups.

