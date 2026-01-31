# DataCo-Supply-Chain

## Problem Statement
For this project, I chose the DataCo Global Supply Chain dataset from Kaggle to conduct a supply chain performance analysis. My objective was to address several key challenges, such as delivery performance and its effects on the sales. I designed this case study and utilized Tableau to develop the dashboard to provide an overview of supply chain performance, with a detailed view of late delivery risk across various dimensions.


## Objective
The goal of this analysis was to help enhance supply chain operations and optimize resource allocation by identifying inefficiencies and highlighting areas for improvement in shipping and delivery logistics. Through this dashboard, I aimed to present actionable insights into how DataCo Global can address these logistical challenges, improve delivery performance, and ultimately boost profitability.

## Data Preparation
I processed a dataset of 53 columns, selecting 41 relevant columns for analysis. I addressed missing values, removed irrelevant columns, and renamed fields for clarity (e.g., "Type" to "Payment Type"). I also extracted date components (date, month, year) to enable time-based analysis. After preprocessing the data in Python, I ingested it into a MySQL database for efficient analysis and integration with Tableau for supply chain and delivery performance visualization.

## Lofi Design

<img width="806" height="1239" alt="image" src="https://github.com/user-attachments/assets/dc8721e0-2da5-4577-9f5e-7ccbbba43bd8" />



##  Overview Dashboard
For the Overview Dashboard, I aimed to provide a high-level summary of the supply chain’s performance across key areas such as shipping, delivery, regional efficiency, and profitability. This dashboard was designed to enable stakeholders to quickly identify strong performance areas and potential bottlenecks without needing to delve into granular details. The objective of this dashboard is to offer a data-driven approach to monitoring and optimizing the supply chain by highlighting critical issues in shipping, delivery, and order processing. The insights allow stakeholders to improve shipment times, reduce late delivery risks, and maximize profit margins, which directly contribute to enhanced customer satisfaction and operational efficiency.
​

### Key Questions Addressed:

1. How is the supply chain performing in terms of shipping and delivery times?

2. Which regions and shipping modes are excelling or encountering difficulties?

3. What is the overall profitability, and which areas need optimization?
​

### Story Flow:
I structured the dashboard to flow logically, starting with the regional and financial performance followed by the shipping performance. This progression allows stakeholders to assess the overall health of the supply chain in an intuitive manner.


## Detailed Dashboard - Late delivery risk

### Late Delivery Risk % vs. Avg Shipping Time % Over Time
In the Late Delivery Risk % vs. Avg Shipping Time % Over Time visualization, I compared two key metrics:
- Late Delivery Risk (%): The percentage of orders at risk of being delivered late. A higher percentage indicates more late deliveries.
- Average Actual Shipping Time (%): This measures how actual shipping times compare to scheduled times, expressed as a percentage.
    - 100% means shipping matched the schedule.
    - Above 100% indicates delays.
    - Below 100% means shipping was completed faster than expected.
 
The goal of this comparison is to illustrate the correlation between these two metrics. As Average Shipping Time (%) increases (i.e., orders take longer than scheduled), the Late Delivery Risk (%) tends to rise. Conversely, when shipping times are faster, the risk of late delivery decreases.

I also added a reference line at 119%, indicating that, on average, it takes 19% longer than the scheduled shipping time. This suggests a systemic delay in the shipping process, contributing to higher Late Delivery Risk. When the Average Shipping Time exceeds this line, it points to operational inefficiencies that can lead to more late deliveries.


### Late Delivery Risk Rate by Market, Customer Segment & Shipping Mode
In the Late Delivery Risk Rate by Market, Customer Segment & Shipping Mode visualization, I analyzed late delivery risks across three key dimensions: market, customer segment, and shipping mode. This helps identify where late deliveries are more common and how they impact overall shipping performance.

By examining these specific dimensions, stakeholders can gain deeper insights into which markets, customer segments, or shipping methods are facing the most challenges. This information is essential for improving delivery efficiency and reducing delays, ultimately enhancing customer satisfaction and operational effectiveness.



## Key Metrics & Filters
### KPIs:
 - Total Sales = SUM(Order Item Total)
 - Total Profit = SUM(Order Profit Per Order)
 - Profit Margin (%) = (Total Profit / Total Sales) * 100
 - On-time delivery rate = SUM([On Time]) / COUNT([Order Id])
 - Late Delivery Risk % = SUM([Late delivery risk]) / COUNT([Order Id])​​

### Filters:
Order Region,
Market,
Customer Segment,
Shipping Mode,
Order From Date,
Order To Date.


## Key Findings
- The delivery performance by region indicates a consistent trend of late deliveries across all regions. However, Western Europe and Central America stand out with the highest rates of late deliveries, at 55.85% and 54.75%, respectively, highlighting significant areas for improvement in these regions.
  ​
- In terms of profitability, Southern Africa shows a promising profit margin of 15.09%, while Eastern Asia, with a profit margin of 11.05%, requires further attention to improve its sales and supply chain efficiency.
  
- For individual products, the Garmin Forerunner has performed relatively well when examining shipping time variance, which is calculated as the difference between actual and scheduled shipping time. Although this product performs better than others, being closer to the reference line at -1 day, it still faces delays, indicating room for improvement.
  ​
- During February 2018, the late delivery rate spiked to 66.67%, while the on-time delivery rate was only 15%, indicating poor delivery performance. This increase in late deliveries could be attributed to factors such as operational bottlenecks or unexpected demand fluctuations during that period.
