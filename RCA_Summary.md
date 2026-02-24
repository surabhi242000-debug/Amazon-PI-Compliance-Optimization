#📑 Project Report: PI Compliance & Image Quality Optimization


# 1. STARR Analysis

- Situation: The Product Image (PI) audit workflow was experiencing significant friction, with a rejection rate representing 15% of the total sample volume. Analysis of 2,000,000 cases revealed that the "First Time Approval Rate" (FTAR) was stagnating at 82%, largely due to strict automated or manual application of "Blurred Image" reason codes. This led to unnecessary vendor re-submissions and increased operational lead times.

- Task: My objective was to perform a deep-dive Root Cause Analysis (RCA) to determine if rejections were technically accurate or if "Soft Failures" could be converted into approvals. The goal was to increase the FTAR by identifying and implementing valid image exceptions without compromising marketplace quality standards.

- Action: * Data Mining: Used SQL to aggregate rejection data by Seller_ID, focusing on the PI Non-Compliant reason code.

      - Stratified Sampling: Extracted a representative 15% sample size for manual audit to ensure statistical significance.

      - SME Collaboration: Partnered with Subject Matter Experts (SMEs) to define a "Compliance Gray Area"—identifying cases where images were technically flagged but still met the customer’s need for product clarity.

      - Stakeholder Influence: Presented a "Correction Report" to cross-functional leadership, advocating for a policy shift regarding specific image artifacts.

- Result: * Successfully increased the FTAR from 82% to 89% within a single quarter.

      - Achieved a 7% net uplift in approval efficiency.

      - Standardized the new SME Exception Logic across multiple nodes, reducing vendor friction globally.

### Performance Impact: Before vs. After
The implementation of the SME Exception Logic resulted in a significant shift in operational efficiency.

| Metric | Pre-Implementation | Post-Implementation | Delta |
| :--- | :--- | :--- | :--- |
| **First Time Approval Rate (FTAR)** | 82% | **89%** | **+7% Net Increase** |
| **Non-Compliant Rejection Rate** | 18% | **11%** | **38% Reduction in Rejections** |
| **Process Standard** | Manual/Ad-hoc | **Standardized SOP** | **Consistency** |
| **Data Volume** | 2,000,000 Cases | 2,000,000 Cases | **Scalable** |



# 2. The "Exception" Logic Implementation
The core of this project was the transition from a Binary Logic (Blurry = Reject) to a Functional Logic (Does the blur affect the customer's buying decision?.)

I implemented a framework that allowed auditors to approve images previously marked as "PI Non-Compliant" based on three specific criteria:

     - Intentional Depth-of-Field: If the background was blurred but the Product Detail (text and labels) was 100% sharp, the case was moved to "Approved."

     - Minimal Grain Exception: Images with high-ISO "noise" that did not obscure the product's identifying features were no longer rejected as "Blurred."

     - Macro-Focus Allowance: For particular text addresses, slight edge-softness was permitted if the primary contact point was in clear focus.
                                                                                                         
                                                                                                         

# 3. Technical Methodology
                                                                                                         
- Tooling: SQL for data extraction and grouping.

- Analytical Technique: Pareto Analysis (Top 10 Sellers) and Random Stratified Sampling.

- Impact Tracking: Quarter-over-Quarter (QoQ) percentage growth monitoring.

