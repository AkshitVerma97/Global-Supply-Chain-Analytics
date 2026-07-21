# Global-Supply-Chain-Analytics
End-to-end data analysis of 180K+ supply chain records using GCP BigQuery, SQL, and Power BI to diagnose regional profit margin bleed and operational bottlenecks.

# Global Supply Chain Analytics: Profitability & Operational Bottlenecks

## 1. Executive Summary
This project analyzes a global supply chain dataset (180,000+ records) to identify revenue leaks and operational inefficiencies. Using SQL for data extraction and Power BI for interactive visualization, the analysis isolates specific global regions suffering from severe margin compression and identifies logistical delays as the primary operational catalyst.

![Executive Overview](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/Page%201.png)

## 2. Analytical Methodology
To accurately diagnose the health of the supply chain, this analysis prioritized specific metrics:
* **Profit Margin (%) vs. Total Profit ($):** Profit Margin was chosen as the primary KPI to measure operational efficiency. High sales volume can mask logistical inefficiencies; analyzing the margin percentage reveals exactly where operational costs are disproportionately eating into revenue.
* **Region/Department Strategy:** The analysis utilized a Macro-to-Micro drill-down. We first evaluated broad Market/Department intersections to find high-level leaks, then drilled down into specific Order Regions and Categories to pinpoint exact points of failure.

## 3. The Financial Bleed (Initial Findings)
Initial SQL analysis revealed highly unprofitable sectors within the business. While global corporate profit margins appear healthy (~11%), specific Region/Category combinations were operating at severe negative margins:
* **Southeast Asia (Books):** -13.60% Profit Margin
* **Eastern Asia (Books):** -6.95% Profit Margin
* **Western Europe (DVDs):** -2.55% Profit Margin

![Market level performance by department](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/Market%20level%20performance%20by%20department.png)

![SQL Analysis Insights Regional Financial Performance by Product Category](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/Regional%20performance%20by%20category.png)


## 4. The Root Cause: Operational Failures
Drilling down into the logistical data for the failing regions revealed a systemic breakdown in the supply chain network. The regions bleeding the most profit correlate heavily with **Late Delivery Rates exceeding 50%**.

![Delivery status by Region](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/Delivery_status_by_region.png)

While the initial shipping cost is fixed, a 50%+ late delivery rate introduces massive hidden operational costs that destroy thin margins (e.g., Customer Service concessions, SLA breach penalties, and reverse logistics).

![Root Cause Analysis - Western Europe](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/Page%202.png)
*Above: Cross-filtering to the Western Europe region highlights a severe negative margin correlation with a 53% late delivery rate.*

## 5. Anomaly Detection & Phase 2 Strategy
While the initial analysis strongly correlated late delivery rates with negative profit margins in Western Europe and Asia, the exploratory Power BI dashboard revealed a critical anomaly: **The Oceania region possesses a higher late delivery rate (55%) yet maintains a highly profitable 19.31% margin.**

![Anomaly Detection - Oceania](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/Page%202_Oceania.png)
*Above: Despite a worse logistics failure rate, Oceania maintains robust profitability, indicating alternative market variables at play.*

![Discount by Market vs Profit Graph in Python libraries](https://github.com/AkshitVerma97/Global-Supply-Chain-Analytics/blob/main/proft_vs_discount_graph.png)

This contradiction indicates that "Late Deliveries" alone are not the sole root cause of the financial bleed, but rather the catalyst for hidden costs in specific markets with lower price elasticity. 

**Proposed Phase 2 Analysis:**
To provide actionable strategy for the executive team, I would request access to the following datasets to investigate why Europe's profit margins are brittle while Oceania's are resilient:
1. **Refund & Concession Data:** Does Western Europe have a higher SLA-breach refund rate per capita than Oceania?
2. **Pricing & Cost of Goods (COGS):** Is the baseline pricing structure in Oceania sufficiently elevated to absorb the financial penalties of late logistics? 
3. **Carrier Penalty Contracts:** Are European 3PL partners charging compounding storage fees for late last-mile delivery that do not exist in Pacific freight routes?

## 6. Strategic Recommendations
Pending Phase 2 data, the following interventions are recommended for Europe and Asia:
* **Adjust Scheduled Delivery Promises:** Update front-end SLAs to reflect actual transit times, instantly reducing SLA breaches and automatic refund requests.
* **Decentralize High-Volume Inventory:** For high-volume, low-margin items like DVDs in Western Europe, shift inventory to localized micro-fulfillment centers closer to the customer to reduce last-mile transit times.
