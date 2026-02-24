# 🚀 Project: Image Compliance Optimization & FTAR Uplift


## 📌 The Business Challenge
In a massive dataset of 2,000,000 cases, the Product Image (PI) rejection rate was identified as a significant operational bottleneck. Approximately 15% of the sampled volume was being rejected for "Blurred Images" (PI Non-Compliant), many of which were potential false positives. This led to high vendor friction and lowered the First Time Approval Rate (FTAR).



## 🛠️ The SQL Engine (Data Extraction)
I engineered a targeted query to isolate the "Culprit Vendors." By filtering for resolved cases specifically flagged under the PI Non-Compliant reason code, I mapped the landscape of rejection.

Query Logic Overview:

- Fields: Seller_ID, Case_ID, Case_Status, Reason_Code, Resolution.

- Filters: Case_Status = 'Resolved' AND Reason_Code = 'PI_Non_Compliant'.

- Aggregation: Grouped by Seller_ID to identify high-frequency offenders.

_Note: I did not include the raw script for data privacy, but the logic utilized Window Functions to rank sellers by rejection volume and JOINs to correlate resolution paths_.

```sql
[SELECT Seller_ID, COUNT(Case_ID) AS Rejection_Count
FROM Global_PI_Database
WHERE Case_Status = 'Resolved' 
  AND Reason_Code = 'PI_Non_Compliant'
GROUP BY Seller_ID
ORDER BY Rejection_Count DESC;]
```



## 🔍 Methodology & SME Deep-Dive
- Stratified Sampling: Performed random sampling of Case IDs per Seller ID to conduct a manual audit.

- Root Cause Analysis (RCA): Collaborated with Subject Matter Experts (SMEs) to identify "Approvable exceptions"—images that were technically compliant but rejected due to overly sensitive automated filters.

- Stakeholder Collaboration: Led cross-functional meetings with the Global Quality and Vendor Teams to redefine approval criteria.



## 📊 Visual Insights & Deliverables
- The "Pareto" of Rejections: A Pie Chart visualizing the Top 10 Seller IDs responsible for the highest rejection volume.

  ![Rejection sample chart](https://github.com/surabhi242000-debug/Amazon-PI-Compliance-Optimization/blob/main/Top%2010%20Seller%20Rejections.png).
  

- The Correction Report: A detailed case-study report showcasing "Before vs. After" approval examples to align stakeholders.

  ![Correction Report](https://github.com/surabhi242000-debug/Amazon-PI-Compliance-Optimization/blob/main/Implementation_.png).



## 📈 Quantifiable Business Impact
- Efficiency Gain: Increased the First Time Approval Rate (FTAR) by 7% within a single quarter.

- Accuracy Shift: Improved the overall approval rate from 82% to 89%.

- Global Scale: Successfully implemented the new SOP (Standard Operating Procedure) across multiple nodes, standardizing the exception-handling process for millions of cases.


![Improved Approval Rate](https://github.com/surabhi242000-debug/Amazon-PI-Compliance-Optimization/blob/main/Implementation_.png).
