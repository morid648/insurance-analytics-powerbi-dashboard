# 🛡️ Shield Insurance Analytics — Executive BI Dashboard

**Domain:** Insurance Analytics · Business Intelligence  
**Tool Stack:** Power BI · DAX · Power Query · Star Schema Modeling  
**Period Analyzed:** Nov 2022 – Apr 2023  
**Version:** V2 (see `/v1` for original build)

---

## Business Problem

Insurance leadership teams need more than revenue summaries.
They need to know:
- Is growth consistent or accumulating?
- Which channels are structurally reliable vs. fragile?
- Where is settlement risk quietly concentrating?
- What does an operational slowdown actually signal?

This dashboard was designed to answer those questions at the
executive level — not as a report, but as a decision-support system.

---

## Analytical Objective

Transform raw insurance operational data into a CXO-level
business review covering:

- Revenue performance and trend quality
- Customer acquisition consistency
- Sales channel effectiveness and digital adoption
- Settlement risk exposure by demographic segment
- Geographic revenue concentration

---

## Tools & Technologies

| Tool | Usage |
|------|-------|
| Power BI | Dashboard design, executive reporting |
| DAX | KPI measures, risk calculations, trend logic |
| Power Query | Data transformation, table restructuring |
| Star Schema | Fact/dimension data modeling |
| Excel | Data validation, pre-modeling review |

---

## Data Model

Star schema architecture:

**Fact Tables:** Premiums · Settlements  
**Dimension Tables:** Customer · Date · Policies

Model required restructuring from raw format:
calculated columns on date, policy, and premium tables;
dedicated sorting tables; age group mapping table for
clean slicer logic across all dashboard pages.

---

## Dashboard Structure

| Page | Business Question Answered |
|------|---------------------------|
| Revenue Overview | Where is growth coming from, and is it slowing? |
| Customer & Channel Analysis | Which channels drive acquisition — and how resilient are they? |
| Settlement Risk Analysis | Where is payout exposure concentrating? |
| Executive Summary | What does leadership need to know right now? |

---

## Key Findings

- Revenue peaked at ₹264M in March 2023; moderated to
  ₹154M by April
- Delhi NCR contributed ₹402M — highest single-city concentration
- Offline channels drove 71%+ of total revenue across the period
- 65+ age group carried the highest settlement risk ratio at 72.28%
- April's online vs. offline decline appeared similar in absolute
  terms — offline fell roughly twice as steeply on a relative basis

---

## DAX Measures Developed

- Total Revenue · Net Revenue · Revenue per Customer
- Settlement Risk % · Expected Payout · Risk Ratio by Age Group
- Online Adoption Rate · High-Risk Customer %
- Customer Acquisition Trends · Channel Revenue Split

---

## V1 → V2: What Changed

| Dimension | V1 | V2 |
|-----------|----|----|
| Structure | 3 pages, independent | 4 pages, sequenced narrative |
| Data Model | Basic | Restructured with calculated columns + mapping tables |
| DAX | Standard KPIs | Custom insurance metrics (Settlement Risk %, Online Adoption Rate) |
| Framing | Reporting dashboard | Executive decision-support system |
| Insight depth | Surface trends | Segmentation, channel resilience, risk concentration |

---

## Repository Structure
shield-insurance-analytics/
├── v1/ Original dashboard build (Dashboard/, Docs/, Images/, Presentation/)
└── v2/
  ├── Dashboard/ Power BI file
  ├── Docs/ KPI definitions, DAX docs, data model
  ├── images/ Dashboard screenshots
  └── Presentation/ Case study PDF + PPTX

---

## Screenshots

→ See `/v2/images/` for full dashboard previews

---

## Future Improvements

- Add policy renewal rate KPI
- Build customer lifetime value segmentation
- Incorporate month-over-month DAX time intelligence
- Add city-level drill-through pages

---

## Acknowledgment

Developed as part of the
**Codebasics Data Analytics Bootcamp 5.0 — Virtual Internship**  
Mentors: **Dhaval Patel** · **Hemanand Vadivel**

> Dataset is part of the Codebasics Virtual Internship
> program and is not publicly shareable.
---
**Built by :**
- [Anshul](https://github.com/morid648)
- [LinkedIn](https://www.linkedin.com/in/anshul-chaudhary-508138308/)
