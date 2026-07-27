# Zomato India: Logistics Bottleneck Analysis 🛵📊

## 📌 Project Overview
This project uncovers the impact of delivery delays on daily order volatility within Zomato's logistics network[cite: 1]. By analyzing 45,000 transaction records and 1,320 active delivery partners, this analysis diagnoses the root causes of daily order stagnation and provides actionable, data-driven recommendations to optimize delivery performance and customer satisfaction[cite: 1].

## 🎯 Business Context & Problem Statement
Management identified a critical issue: daily order volumes experienced extreme stagnation, with a strong inverse operational pattern showing that spikes in delivery duration (`Time_taken`) directly suppress daily order volume[cite: 1]. 

**Key Business Questions Addressed:**
1. What specific factors (e.g., traffic density, multi-batching) cause daily delivery duration to fluctuate so aggressively?[cite: 1]
2. At what delivery duration threshold does customer rating begin to collapse, driving order volume down?[cite: 1]
3. How should Zomato rebalance driver allocation across city categories to stabilize delivery time and unlock order growth?[cite: 1]

## 🛠 Data Processing & Methodology
* **Data Scope:** 45K delivery transactions and 1.32K active delivery partners[cite: 1].
* **Feature Engineering:** 
  * Calculated exact delivery distances (`distance_km`) using the Haversine Formula from geospatial coordinates[cite: 1].
  * Grouped `Multiple Deliveries` into distinct batch tiers (Single, 1 Batch, 2 Batch, 3 Batch)[cite: 1].
* **Modeling:** Single Flat Transactional Schema processed into a Virtual Star-Schema in Power BI[cite: 1].
* **Statistical Analysis:** Applied Daily Aggregation specifically for March to eliminate row-level noise, revealing a definitive correlation (+0.96) between Total Orders and Average Rating[cite: 1].

## 💡 Key Insights & Discoveries
* **The Synchronization (Orders vs. Ratings):** Customer satisfaction has an immediate, same-day impact on retention. The daily count of orders moves exactly in tandem with the Average Delivery Ratings (Correlation: +0.96)[cite: 1].
* **The Core Bottleneck:** Delayed deliveries heavily drag down ratings (Correlation vs Total Orders: -0.98)[cite: 1]. Customer ratings remain high (4.7 - 4.8) for deliveries under 30 minutes, but drop sharply to 4.4 - 4.5 once the 30-minute SLA is breached[cite: 1].
* **Delay Cause 1 - Multiple Batching:** Systematically assigning drivers multiple concurrent orders exacerbates delays. 3-Batch Orders inflate delivery time to 47.8 mins, driving ratings down to an all-time low of 4.4[cite: 1].
* **Delay Cause 2 - Traffic Density:** Severe traffic jams push average delivery times to 31.3 mins, instantly dropping the average rating to 4.6[cite: 1].
* **The Geographic Imbalance:** Metropolitan areas heavily dominate demand (76.83% or 34,000 orders) but have an overwhelmed fleet of 1,320 drivers[cite: 1]. Meanwhile, Urban areas are overstaffed (1,281 drivers for only 10,000 orders)[cite: 1].

## 🚀 Strategic Recommendations
### Quick Wins
* **Dynamic Batching Restriction:** Cap the system at 1 Batch Order maximum to maintain delivery times safely under 27 minutes[cite: 1]. Temporarily disable 2 & 3 Batch features during peak surge hours (17:00-00:00) or during 'Jam' traffic statuses[cite: 1].
* **SLA Warning System:** If predictive logistics anticipate a delay exceeding 30 minutes, proactively issue a 'Free Delivery Voucher' in-app to secure customer retention[cite: 1].

### Long-Term Strategies
* **Fleet Reallocation:** Create targeted incentives to transfer underutilized drivers from Urban areas into Metropolitan zones[cite: 1]. Alternatively, launch an aggressive, geofenced hiring campaign specifically for Metropolitan areas[cite: 1].
* **Predictive Logistics Hubs:** Establish strategic Cloud Kitchens in identified traffic blind spots to combat the massive volume of 'Long Distance' orders in Metropolitan areas[cite: 1].
**Muhammad Rafly Alviansyah** 
* Data Analyst | Best Graduate in Geography Education (UPI)[cite: 1]
* [LinkedIn](https://www.linkedin.com/in/raflyalvish/)[cite: 1]
