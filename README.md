# 🛡️ Shield Insurance Analytics Dashboard — V2
### Executive Business Intelligence & Risk Intelligence Review

A CXO-level Power BI analytics case study analyzing revenue performance, 
settlement risk exposure, channel effectiveness, and customer acquisition 
trends across a 6-month operational window (Nov 2022 – Apr 2023).

---

## 🔄 V1 → V2: What Changed

V1 tracked the right metrics but lacked a connecting narrative.  
V2 was rebuilt with one question per page:  
**"What decision does this support?"** — not "What can I show here?"

Key improvements:
- Restructured data model — date, policy, and premium tables rebuilt with calculated columns, dedicated sorting tables, and age group mapping table
- Added settlement risk segmentation by age group and channel resilience analysis
- Rebuilt DAX measures — Online Adoption Rate, Settlement Risk %, Risk Ratio, Expected Payout
- Reframed from reporting dashboard → executive decision-support system

---

## 📊 Dashboard Pages

| Page | Purpose |
|------|---------|
| Revenue Overview | Revenue trends, peak/moderation detection, city concentration |
| Customer & Channel Analysis | Acquisition trends, channel split, online adoption rate |
| Settlement Risk Analysis | Risk ratio by age group, expected payout, high-risk segmentation |
| Executive Summary | CXO-level narrative across all four dimensions |

---

## 📈 Key Findings (Nov 2022 – Apr 2023)

| Metric | Value |
|--------|-------|
| Peak Revenue | ₹264M (March 2023) |
| April Revenue | ₹154M (moderation signal) |
| Delhi NCR Contribution | ₹402M (highest city concentration) |
| Offline Channel Revenue Share | 71%+ |
| 65+ Settlement Risk Ratio | 72.28% (highest across all age groups) |

**Critical insight:** April's online vs. offline revenue drops appeared  
similar in absolute terms — offline declined roughly twice as steeply  
on a relative basis. This signal disappears in summary reports.

---

## 🛠️ Tools & Technical Stack

Power BI · DAX · Power Query · Star Schema Modeling  
Fact Tables: Premiums, Settlements  
Dimension Tables: Customer, Date, Policies

---

## ⚠️ Business Risks Identified

- Heavy geographic concentration — Delhi NCR dependency
- Offline channel structural dominance — digital adoption still early-stage
- Elevated settlement exposure in 65+ demographic
- April moderation signals potential acquisition consistency risk

---

## 📂 Repository Structure
Shield-Insurance-Analytics/
-├── v1/ → Original dashboard and analysis
-├── v2/ → Rebuilt executive dashboard (this version)
-└── README.md → Full project documentation

---


---

## 🎓 Acknowledgment

Case study developed as part of the  
**Codebasics Data Analytics Bootcamp 5.0 — Virtual Internship**  
Mentors: **Dhaval Patel** · **Hemanand Vadivel**

⚠️ Dataset is part of the Codebasics Virtual Internship  
and is not publicly shareable.
