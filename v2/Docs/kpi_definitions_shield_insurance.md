# KPI Definitions

## Total Revenue
- Business meaning: Total premium revenue generated from all insurance policies during the selected period.
- Formula: SUM('fact_premiums'[final_premium_amt(INR)])

## Net Revenue After Settlement
- Business meaning: Actual retained revenue after accounting for settlement payouts.
- Formula: Total Revenue - Expected Settlement

## Settlement Risk
- Business meaning: Percentage of premium revenue expected to be paid out as settlements.
- Formula: Expected Settlement / Total Revenue

## Expected Settlement
- Business meaning: Estimated payout liability based on settlement percentage.
- Formula: Total Revenue × Avg Settlement %

## Online Adoption Rate %
- Business meaning: Percentage of customers or revenue generated through online channels.
- Formula: Online Revenue / Total Revenue

## Online Revenue
- Business meaning: Revenue generated through digital channels such as apps and websites.
- Formula: Revenue filtered where Channel Group = Online

## Offline Revenue
- Business meaning: Revenue generated through offline channels such as agents and branches.
- Formula: Revenue filtered where Channel Group = Offline

## Total Customers
- Business meaning: Unique customers who purchased policies.
- Formula: DISTINCTCOUNT(customer_code)

## Total Policies Sold
- Business meaning: Total number of insurance policies sold.
- Formula: DISTINCTCOUNT(policy_id)

## Revenue Per Customer
- Business meaning: Average revenue generated per customer.
- Formula: Total Revenue / Total Customers

## Avg Final Premium
- Business meaning: Average final premium amount paid by customers.
- Formula: AVERAGE(final_premium_amt(INR))

## Avg Base Premium
- Business meaning: Average base premium before adjustments.
- Formula: AVERAGE(base_premium_amt(INR))

## Avg Base Cover
- Business meaning: Average insurance coverage amount offered.
- Formula: AVERAGE(base_coverage_amt(INR))

## Cover To Premium Ratio
- Business meaning: Indicates coverage value provided per unit of premium.
- Formula: Avg Base Cover / Avg Final Premium

## High Risk Customer %
- Business meaning: Percentage of customers with high settlement risk.
- Formula: High Risk Customers / Total Customers

## Revenue Share %
- Business meaning: Contribution percentage of a segment to total revenue.
- Formula: Segment Revenue / Total Revenue

## Customer Share %
- Business meaning: Share of customers contributed by a segment.
- Formula: Segment Customers / Total Customers

## Channel Revenue Share %
- Business meaning: Revenue contribution split between online and offline channels.
- Formula: Channel Revenue / Total Revenue

## Policy Premium Uplift %
- Business meaning: Increase in premium value compared to base premium.
- Formula: (Final Premium - Base Premium) / Base Premium

## Settlement Risk Ratio
- Business meaning: Measures payout exposure against revenue.
- Formula: Expected Settlement / Net Revenue

## Revenue vs Settlement Gap
- Business meaning: Difference between generated revenue and expected settlements.
- Formula: Total Revenue - Expected Settlement

## YoY Revenue Growth %
- Business meaning: Year-over-year revenue growth comparison.
- Formula: (Current Revenue - Previous Year Revenue) / Previous Year Revenue

## MoM Revenue Growth %
- Business meaning: Month-over-month revenue growth trend.
- Formula: (Current Month Revenue - Previous Month Revenue) / Previous Month Revenue

## MoM Customer Growth %
- Business meaning: Month-over-month customer acquisition growth.
- Formula: (Current Customers - Previous Month Customers) / Previous Month Customers

## MoM Policies Growth %
- Business meaning: Month-over-month policy sales growth.
- Formula: (Current Policies - Previous Policies) / Previous Policies

## Risk Signal
- Business meaning: Indicator used to highlight high-risk settlement scenarios.
- Formula: Conditional logic based on settlement thresholds.

## Revenue Trend Signal
- Business meaning: Indicates positive or negative revenue trend.
- Formula: Conditional comparison against previous month revenue.

## Customer Trend Signal
- Business meaning: Indicates customer growth or decline trend.
- Formula: Conditional comparison against previous month customers.

