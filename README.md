# Streamline Logistics Dashboard Project

## Table of Contents
- [Project Overview](#project-overview)
- [Business Introduction](#business-introduction)
- [Business Problem](#business-problem)
- [Rationale for the Project](#rationale-for-the-project)
- [Aim of Project](#aim-of-project)
- [Data Sources](#data-sources)
- [Tools Used](#tools-used)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results / Findings](#results--findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)

---

## Project Overview
This project focuses on diagnosing operational inefficiencies within **Streamline Logistics Solutions** and developing a fully interactive **Excel dashboard** to monitor order fulfilment performance.  
The project leverages real-world delivery data to analyse backlogs, delays, driver performance, city-level metrics, and customer feedback.

**Goal:** Reduce operational bottlenecks, enhance customer satisfaction, and provide leadership with real-time performance visibility.

---

## Business Introduction
Streamline Logistics Solutions is a leading logistics company with over two decades of nationwide delivery operations. Renowned for reliability and swift delivery, the company has maintained strong customer trust over the years.

However, operational inefficiencies, particularly in routing and resource allocation, have resulted in order backlogs, delayed deliveries, and increased costs.  
This project aims to address these challenges through a **data-driven strategy**.

---

## Business Problem
The organisation is facing four major challenges:

1. **Mounting Order Backlogs**  
   Inefficient routing has increased pending orders, threatening delivery timelines.

2. **Visibility Gap**  
   Customers lack real-time updates on order progress.

3. **Customer Frustration**  
   Rising complaints due to delays and poor communication.

4. **Escalating Costs**  
   Overtime and expedited shipping are increasing operational expenses.

---

## Rationale for the Project
Order fulfilment involves inventory management, order processing, picking, packing, and shipping. Delays or inefficiencies impact customer satisfaction and revenue.

The project aims to:
- Improve delivery timelines and communication  
- Reduce waste and operational costs  
- Optimise resource allocation through data  
- Maintain Streamline Logistics' reputation for reliability  

---

## Aim of Project
The primary objectives of the dashboard project include:
- Efficient allocation of delivery resources  
- Real-time monitoring of order progress  
- Early detection of potential delays  
- Reduction of backlogs and operational expenses  
- Increasing customer satisfaction through transparency  

---

## Data Sources
A single dataset was used for this case study, containing:
- Order ID – Unique order identifier  
- Delivery Address  
- Order Timestamp  
- Order Status (In Progress / Completed)  
- Driver ID  
- Vehicle Info  
- Current Location  
- Delivery Time (in minutes)  
- Delays (in minutes)  

---

## Tools Used
- **Excel** – Data cleaning & dashboard creation  
- **SQL Server** – Data analysis  

*(Excel was used for the final dashboard in this project)*

---

## Data Cleaning & Preparation
Tasks performed include:
- Data formatting and inspection  
- Removal of inconsistencies  
- Standardisation of timestamps  
- Handling missing values  
- Extracting date/time components for analysis  
- Creating calculated fields for delay metrics  

---

## Exploratory Data Analysis
Key business questions explored:
- How many orders are currently backlogged?  
- What is the average delivery delay?  
- Which cities and routes have the highest delays?  
- What is the distribution of customer feedback?  
- What proportion of orders use Expedited Rules vs Custom?  

---

## Data Analysis
Example SQL snippet:

```sql
SELECT 
    DriverID,
    AVG(DelayMinutes) AS AvgDelay
FROM Delivery_data
GROUP BY DriverID
ORDER BY AvgDelay DESC;
```
---

## Results / Findings

<details>
<summary>📌 Delivery Performance</summary>

- **Total Orders:** 1,500  
- **Completed:** 733  
- **In Progress:** 767  
- **Backlog Rate:** 51.31% → *critical bottleneck*  

</details>

<details>
<summary>📌 Delivery Timing</summary>

- **Average Delivery Time:** 151.77 mins  
- **Average Delay:** 14.51 mins  
- **Peak Delays:** Between 10 AM – 2 PM  

</details>

<details>
<summary>📌 Driver Performance</summary>

- Consistently high delays: **D86, D44, D29**  
- All drivers show avg delays between **14.1–14.8 mins**  

</details>

<details>
<summary>📌 Vehicle Performance</summary>

- **Van A:** Best performer → 14.15 mins  
- **Bike C:** Least efficient  

</details>

<details>
<summary>📌 Route Analysis</summary>

- **Best Route:** Route 5 — 13.69 mins delay  
- **Worst Routes:** Routes 1–3  

</details>

<details>
<summary>📌 City Analysis</summary>

- **City E:** Highest delays (15.29 mins)  
- **City D:** Most efficient (14.09 mins)  

</details>

<details>
<summary>📌 Backlog Counts</summary>

**Top Cities:**
- City B: 105  
- City D: 95  
- City A: 90  

**Top Routes:**
- Route 5: 105  
- Route 3: 95  
- Route 1: 90  

</details>

<details>
<summary>📌 Customer Feedback</summary>

- Negative: 40%  
- Neutral: 28%  
- Positive: 32%  
- Negative deliveries = highest delays (**15.8 mins**)  

</details>

<details>
<summary>📅 Day-of-Week Trends</summary>

- **Highest delays:** Wednesday (15.5 mins)  
- **Lowest delays:** Sunday (13.5 mins)  

</details>

<details>
<summary>🔍 Additional Observations</summary>

- Expedited rules have higher delays, contradicting their purpose  
- Zone performance varies significantly  
- 45 drivers across 5 key locations  

</details>

---

## Recommendations
- Reassign or retrain underperforming drivers  
- Redesign routing logic for high-delay routes  
- Reevaluate expedited delivery procedures  
- Enhance communication in high-delay zones  
- Promote high-performing vehicles (e.g., Van A)  
- Launch customer feedback improvement initiatives  
- Introduce real-time delivery tracking  

---

## Limitations
- Some records with zero delivery time or missing timestamps were removed  
- Driver‒city mapping contained inconsistencies  
- Feedback categorisation required re-classification  
- Lack of external factors data (traffic, weather) may affect accuracy  

---

## References
- Excel documentation  
- SQL Server documentation  
- Logistics best-practice articles  
- Stack Overflow  
