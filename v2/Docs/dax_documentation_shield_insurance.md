# DAX Documentation

## Total Revenue
- Purpose: Calculate total premium revenue across all policies.
- DAX:
```DAX
Total Revenue =
SUM('fact_premiums'[final_premium_amt(INR)])
```
- Logic notes: Core KPI used across all dashboard pages.

## Total Customers
- Purpose: Count unique customers purchasing policies.
- DAX:
```DAX
Total Customers =
DISTINCTCOUNT('fact_premiums'[customer_code])
```
- Logic notes: Avoids duplicate customer counting.

## Total Policies Sold
- Purpose: Count total policies sold.
- DAX:
```DAX
Total Policies Sold =
DISTINCTCOUNT('fact_premiums'[policy_id])
```
- Logic notes: Measures insurance policy volume.

## Online Revenue
- Purpose: Measure revenue generated through online channels.
- DAX:
```DAX
Online Revenue =
CALCULATE(
    [Total Revenue],
    'fact_premiums'[Channel Group] = "Online"
)
```
- Logic notes: Filters only digital channels.

## Offline Revenue
- Purpose: Measure revenue generated through offline channels.
- DAX:
```DAX
Offline Revenue =
CALCULATE(
    [Total Revenue],
    'fact_premiums'[Channel Group] = "Offline"
)
```
- Logic notes: Includes branch and agent-based sales.

## Online Adoption Rate %
- Purpose: Track digital channel penetration.
- DAX:
```DAX
Online Adoption Rate % =
DIVIDE([Online Revenue], [Total Revenue], 0)
```
- Logic notes: Indicates customer shift toward online platforms.

## Avg Final Premium
- Purpose: Calculate average final premium amount.
- DAX:
```DAX
Avg Final Premium =
AVERAGE('fact_premiums'[final_premium_amt(INR)])
```
- Logic notes: Used in premium trend analysis.

## Avg Base Premium
- Purpose: Calculate average base premium.
- DAX:
```DAX
Avg Base Premium =
AVERAGE('dim_policies'[base_premium_amt(INR)])
```
- Logic notes: Baseline premium before adjustments.

## Avg Base Cover
- Purpose: Calculate average insurance coverage amount.
- DAX:
```DAX
Avg Base Cover =
AVERAGE('dim_policies'[base_coverage_amt(INR)])
```
- Logic notes: Helps evaluate policy value.

## Cover To Premium Ratio
- Purpose: Compare coverage against premium amount.
- DAX:
```DAX
Cover To Premium Ratio =
DIVIDE([Avg Base Cover], [Avg Final Premium], 0)
```
- Logic notes: Higher values indicate better customer value proposition.

## Avg Settlement %
- Purpose: Calculate average settlement percentage.
- DAX:
```DAX
Avg Settlement % =
AVERAGE('fact_settlements'[settlement %])
```
- Logic notes: Used for payout risk estimation.

## Expected Settlement
- Purpose: Estimate payout liabilities.
- DAX:
```DAX
Expected Settlement =
[Total Revenue] * [Avg Settlement %]
```
- Logic notes: Forecast-based settlement exposure metric.

## Net Revenue After Settlement
- Purpose: Measure retained earnings after settlement payouts.
- DAX:
```DAX
Net Revenue After Settlement =
[Total Revenue] - [Expected Settlement]
```
- Logic notes: Critical profitability indicator.

## Settlement Risk Ratio
- Purpose: Evaluate payout exposure relative to retained revenue.
- DAX:
```DAX
Settlement Risk Ratio =
DIVIDE([Expected Settlement], [Net Revenue After Settlement], 0)
```
- Logic notes: Higher values indicate increased business risk.

## High Risk Customer %
- Purpose: Identify proportion of high-risk customers.
- DAX:
```DAX
High Risk Customer % =
DIVIDE(
    CALCULATE(
        [Total Customers],
        'dim_customer'[Settlement%] > 0.60
    ),
    [Total Customers],
    0
)
```
- Logic notes: Threshold-based segmentation.

## Revenue Per Customer
- Purpose: Calculate customer profitability.
- DAX:
```DAX
Revenue Per Customer =
DIVIDE([Total Revenue], [Total Customers], 0)
```
- Logic notes: Used in customer DNA analysis.

## Revenue Share %
- Purpose: Measure revenue contribution by segment.
- DAX:
```DAX
Revenue Share % =
DIVIDE(
    [Total Revenue],
    CALCULATE([Total Revenue], ALL('dim_customer')),
    0
)
```
- Logic notes: Dynamic contribution metric.

## Policy Premium Uplift %
- Purpose: Measure premium increase over base premium.
- DAX:
```DAX
Policy Premium Uplift % =
DIVIDE(
    [Avg Final Premium] - [Avg Base Premium],
    [Avg Base Premium],
    0
)
```
- Logic notes: Indicates pricing uplift performance.

## LM Revenue
- Purpose: Retrieve previous month revenue.
- DAX:
```DAX
LM Revenue =
CALCULATE(
    [Total Revenue],
    DATEADD('dim_date'[date], -1, MONTH)
)
```
- Logic notes: Used for month-over-month analysis.

## LY Revenue
- Purpose: Retrieve previous year revenue.
- DAX:
```DAX
LY Revenue =
CALCULATE(
    [Total Revenue],
    DATEADD('dim_date'[date], -1, YEAR)
)
```
- Logic notes: Used for YoY comparison.

## MoM Revenue Growth %
- Purpose: Track monthly revenue trend.
- DAX:
```DAX
MoM Revenue Growth % =
DIVIDE([Total Revenue] - [LM Revenue], [LM Revenue], 0)
```
- Logic notes: Positive values indicate growth.

## YoY Revenue Growth %
- Purpose: Track annual revenue growth.
- DAX:
```DAX
YoY Revenue Growth % =
DIVIDE([Total Revenue] - [LY Revenue], [LY Revenue], 0)
```
- Logic notes: Used for long-term business performance.

## Dynamic Insight
- Purpose: Generate contextual business commentary.
- DAX:
```DAX
Dynamic Insight =
SWITCH(
    TRUE(),
    [MoM Revenue Growth %] > 0, "Revenue growing steadily.",
    [MoM Revenue Growth %] < 0, "Revenue declining — intervention required.",
    "Revenue stable."
)
```
- Logic notes: Drives automated insight cards.

