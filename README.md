# ANALYZE-THE-IMPACT-OF-MARKETING-ACTIVITIES-ON-THE-BUSINESS-PERFORMANCE-OF-A-FASHION-BRAND
With operations in 14 countries, a fashion eCommerce business must quickly grasp fashion styles and media trends to reach and attract target customers effectively. Therefore, analyzing the effectiveness of marketing activities from 2019 to 2023 can help propose strategies to boost business performance in the future.

# Overviews
The analysis project covers the following areas:

+ **Data collection**: The dataset is sourced from a simulated dataset on Kaggle for TheLook fashion eCommerce website. Operating across 14 countries, the dataset offers business performance insights for the fashion shop over five years (2019-2023), including information related to products, orders and web events tied to digital marketing strategies.
+ **Data exploration**: Quickly summarize the values related to calculated data fields and explore the distribution of related factors.
+ **Data preparation**: Cleaning and formating the data for analysis.
+ **Descriptive analytics**: Calculate the necessary metrics for the analysis.
+ **Data modeling**: Identify the fact tables, dimension tables, common columns for referencing information, and establish relationships between the tables.
+ **RFM analysis**: Classify and segment customers into appropriate groups using specific RFM criteria.
+ **Propose solutions**: Propose some integrated solutions to boost marketing efforts and improve the company's business performance.

# Applied Skills
ETL Data, Data Analysis, Data Visualization (using Power BI & Python)

# Key Findings
**Overview of business performance**

Examining revenue and orders during the 2019-2023 period, we observe:
+ Period 2019-2020: Total orders increased significantly (241%) but revenue saw a slight increase (13.7%). Due to the impact of Covid-19, most orders were either canceled or returned.
+ Period 2021-2023: There was a rapid recovery and growth in revenue (>100%) and total orders also increased substantially (>70%). Among these, completed orders accounted for about 75%, while canceled/returned orders remained stable.

**Customer**

*About demographics*:
+ By gender: The male-female ratio is almost equal, with no significant difference.
+ By age: The age group from 19-65 accounts for 80%, among which the working age group with high income (31-50) accounts for 33.83%.
+ By traffic sources: Most customers who become members come from search sources. This indicates that Search-Adwords is an effective channel to reach new customers.
+ By country: China is currently the primary market for the business (33k users), followed by the USA and Brazil.

*About customer segment*:
Based on the RFM analysis, we classify customers into 4 groups: Champions, Potential Customers, Need Attention, and At Risk. The analysis shows:
+ Champions: This is the core customer group, accounting for only about 20% of the total customers but generating the highest revenue, over 40% ($2.85M).
+ Potential Customers and At Risk: These groups have the highest number of users but achieve average revenue. Additionally, we can see that the completed orders in these two groups account for only about 62% (the ideal average completion rate is 75%).

**Price segment**

*The dispersion of selling prices*:

The selling prices of products across all three order statuses are widely distributed, ranging from approximately $0 to nearly $1000, indicating a diversity in the prices of the products sold. However, the majority of products have selling prices concentrated at the lower range (below $200).

*Business performance by price segment*:
+ Products priced under $50 account for a large share of total sales volume but contribute minimally to annual total revenue. Conversely, products in the $50-$200 range are a significant source of the company's revenue.
+ Given the company's scope of operations, selling products under $50 can effectively serve a broad and mass-market.
+ High-priced items bring added value and indicate that many customers are still willing to spend on higher-priced segments of the brand.

*Customer portrait*:
+ Three out of the four customer groups contribute significantly to the company's revenue by purchasing products in the $50-$200 price range.
+ However, products priced over $200, although highly anticipated, do not account for a substantial proportion of the company's revenue structure.
+ The Champions group has the highest order completion rate, contributing significantly to revenue from products at various price points.
+ The At Risk and Need Attention groups have low order completion rates, with a considerable proportion of canceled orders, especially for products priced in the $200-$500 and above $500 segments.

**Website traffic**

*Access sources and customer activities on the website*:
+ Email Marketing: This is the most effective channel, bringing in high traffic for both members and non-members. This source also has a high conversion rate (purchases).
+ Adwords: This source brings in the second highest traffic and also has a good conversion rate (purchases).
+ Other social traffic sources like Facebook and YouTube are not yet performing effectively, so the communication plans for these two channels need to be reconsidered.

*Business performance by access source*:
+ The business focuses on investing in communication through two channels are Adwords and Email Marketing.
+ The resulting traffic and (estimated) revenue achieved are approximately 45% for Email Marketing and 30% for Adwords.
+ Additionally, two other social channels, Facebook and YouTube, have not been prioritized for communication activities, although they have the potential to create unique review content that attracts viewers.

# Outcomes
**General conclusions about customers**
+ The fashion business's main markets are China, the USA, and Brazil. The target customer group is both genders in the working age with a moderate to high income.
+ Most customers register as members through search traffic.
+ The customer group that the company should focus on nurturing is the Champions group, as it consists of a small number of customers but generates high revenue.
+ During the 2022-2023 period, the business has been quite effective in retaining customers and attracting new ones, reducing the At Risk customer group and increasing the Potential Customer group.

**General conclusions about price segment**
+ Overall, the brand's current customer segments still have demand and are willing to pay for products priced over $50. This indicates potential for profit margin exploitation when selling these products in the future.
+ Although customers have made purchasing decisions, they still exhibit different behaviors towards products at different price points.
+ This highlights that the company's customers continuously change their needs and expectations when shopping.

**General conclusions about Website traffic**
+ The business's online promotion activities mainly focus on two main channels: Email Marketing and Adwords. The goal is to attract new customers (90%) and remind the brand to existing customers.
+ Email Marketing generates the largest and highest quality traffic (resulting in orders), accounting for about 45% of total revenue.
+ Adwords (Search) provides the second highest quality traffic, accounting for about 30% of revenue.
+ Two other social channels, YouTube and Facebook, have not yet been heavily utilized.

# Propose solutions
**Products and Consumer Preferences**

Maintain the development and diversification of core product groups and enhance and diversify new models for the Suits & Sport Coats product group.

Develop product combos that combine core products and new products to increase the appeal and value of orders.

**Selling price**

For products in the over $200 price segment, the brand can promote and offer discounts to attract consumer demand.

For the Need Attention and At Risk customer segments, it's necessary to provide information and communicate the product's value to set more reasonable expectations.

As for Champions and Potential Customers, continue enhancing the shopping experience, maintaining product quality, and focusing on loyalty marketing to sustain long-term relationships with them.

**Customer**

Implement customer appreciation programs to reconnect with Champions, Potential Customers, and At Risk groups.

Launch special promotions for new members or first-time buyers to increase the number of new customers.

Provide free shipping codes or promotional vouchers to encourage customers to increase their order value and return for future purchases.

**Online promotion**

Specialize in developing promotional content (Email, Adwords) based on customer preferences in each region. At the same time, consider and increase the budget for advertising to reach new customers through the Adwords (Search) channel.

# Example Code
```
# Import library
import numpy as np
import pandas as pd
from datetime import datetime
from datetime import timedelta
import os
import seaborn as sns
import matplotlib.pyplot as plt
import regex as re

# Tách và chuyển đổi kiểu dữ liệu
orders['created_at'] = orders['created_at'].str.split('T').str[0]
orders['created_at'] = pd.to_datetime(orders['created_at'])

# Tạo cột tháng, năm
orders['month'] = orders['created_at'].dt.strftime('%Y-%m')
orders['year'] = orders['created_at'].dt.strftime('%Y')

# Phân khúc các mức giá cụ thể
orders['price_segment'] = None
orders['price_segment'][(orders['sale_price'] <= 50) & (orders['sale_price'] > 0)] = '<$50'
orders['price_segment'][(orders['sale_price'] <= 200) & (orders['sale_price'] > 50)] = '$50 - $200'
orders['price_segment'][(orders['sale_price'] <= 500) & (orders['sale_price'] > 200)] = '$200 - $500'
orders['price_segment'][orders['sale_price'] > 500] = '>$500'
```

# Project Structure
The project includes the following main components:
+ `README.md`: This file provides information and an overview of the analysis.
+ `ANALYZE THE IMPACT OF-MARKETING ACTIVITIES ON THE BUSINESS PERFORMANCE OF A FASHION BRAND`: The Google Colab file contains code for processing, transforming, and retrieving data.
+ `Dashboard`: Data visualization file using Power BI for each part of the analysis.
