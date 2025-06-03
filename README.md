
## Project Background

**Shop Easy** is a leading online retailer in the sporting goods and fitness sector, operating for over a decade as a direct-to-consumer (D2C) e-commerce business. Despite recent investments in digital marketing and campaign launches, Shop Easy has faced declining customer engagement and conversion rates, with high marketing expenditures yielding suboptimal return on investment (ROI). As a data analyst at Shop Easy, my role is to deliver actionable insights by integrating marketing, engagement, and customer feedback data, enabling the business to optimize strategy, improve customer experience, and drive growth.

---

## Insights and Recommendations Are Provided on the Following Key Areas:

- **1. Customer Engagement & Conversion Trends**
- **2. Product & Funnel Performance**
- **3. Social Media & Content Effectiveness**
- **4. Customer Review & Sentiment Analysis**

> - The SQL queries used to inspect and clean the data for this analysis can be found here: [SQL Cleaning Scripts](./Sql.docx)
> - Targeted SQL queries regarding business questions can be found here: [Business SQL Queries](./Sql.docx)  
> - The interactive Power BI dashboards used to report and explore sales and marketing trends are included in this repository.  
> - The Python script for sentiment analysis is included here: [Python Sentiment Analysis](./python-sentiment-analysis.docx)
> - Link for Dataset - 

---

## Data Structure & Initial Checks

The company’s main database structure consists of the following core tables ([tables-and-datasources-info.docx])

- **dim_product**: Product details (ID, name, price, price category)
- **dim_customer**: Customer demographics and geography (joined from customers and geography tables)
- **calendar**: Date dimension table (generated in Power BI)
- **fact_customer_journey**: Customer journey events (view, click, purchase, etc.), cleaned for duplicates and missing durations
- **fact_engagement_data**: Engagement metrics (views, clicks, likes, campaign info), 
- **fact_customer_reviews_with_sentiment**: Customer reviews, ratings, and sentiment scores/categories (enriched using Python/NLTK)
- **_calculations**: DAX measures for KPIs and advanced analytics

**Total row count (approximate):**
- Products: ~20  
- Customers: ~10,000  
- Reviews: ~1,400  
- Engagements: ~9 million  
- Customer journeys: ~4,000

**Entity Relationship Diagram:**  
*Dim tables link to fact tables on IDs; calendar links to all facts by date.*  
*(Insert ERD image if available)*

## Executive Summary

**Overview of Findings**

Shop Easy’s marketing initiatives have not yet reversed the decline in customer engagement and conversion rates. Analysis reveals that **negative product sentiment is a key driver of reduced engagement, with certain products and content types disproportionately affecting overall performance.** Social media and campaign efforts show varying effectiveness by channel and geography, while customer review analysis surfaces actionable product pain points. Focusing on product quality, campaign optimization, and addressing key negative feedback can significantly boost engagement and conversions.

> **Top 3 Insights **
> 1. **Negative sentiment in customer reviews directly correlates with drops in engagement and conversion rates, especially for high-priced products.
> 2. Cart abandonment and micro-conversion rates highlight specific bottlenecks in the funnel, with some products consistently underperforming.
> 3. Social media content type and country-specific sentiment reveal opportunities for targeted campaign optimization and product improvement.
**
![Overview Dashboard](./overview_dashboard.jpg)[1]

---

## Insights Deep Dive

### 1. Customer Engagement & Conversion Trends

- **Engagement rate declined** from **29.1% in January to 17.6% in December,** closely tracking an increase in negative reviews.
- **Conversion rate is 9.6%,** with a** YoY decrease of -5.04%**. **The highest conversion rates are in Q1, with a notable drop in Q3 and Q4.**
- **Insight 3:** Funnel analysis shows a significant drop-off from clicks to likes (**only 4.6% of views result in a like**), **indicating issues with content relevance or site experience.**
- **Insight 4:** Monthly conversion rates and engagement metrics consistently fall below industry benchmarks and averages, particularly during campaign-intensive months.

![Engagement & Conversion Trends](./overview_dashboard.jpg)

---

### 2. Product & Funnel Performance

- **Product conversion rates** vary widely, with **Hockey Stick (15.5%) and Silver Goggles (14.4%) outperforming**, **while Swim Goggles (5.6%) and Running Shoes (6.3%) underperform**.
- **Cart abandonment** is **highest for Swim Goggles (87.8%) and Basketball (85.1%),** indicating friction in the checkout process or product-specific issues.
- **Micro-conversions (36.1%) and average journey duration (2.62 min)** suggest **customers are engaging but not progressing to purchase for certain products.**
- **Year-over-year analysis** shows some products improving in conversion, but many declining, highlighting the need for targeted interventions.

![Product & Funnel Performance](./conversion_dashboard.jpg)

---

### 3. Social Media & Content Effectiveness

- **Video content has the highest CTR (24.6%)** but similar engagement rates to social media posts and blogs.
- **Sentiment distribution** by country shows** Austria, Belgium, and France have the highest rates of negative sentiment,** suggesting a need for localized content or support.
- Monthly trends show **engagement and sentiment scores declining in the second half of the year**, despite increased campaign activity.
- **Social media campaigns** are numerous (20 tracked), but only a subset drive above-average engagement and sentiment.

![Social Media Details](./social_media_dashboard.jpg)

---

### 4. Customer Review & Sentiment Analysis

- **16.6% of reviews are negative**, and products like **Soccer Ball are 1.63x more likely to receive mixed negative sentiment.**
-  Word cloud and frequency analysis surface** “unclear instructions,” “average experience,” and “money” as top negative themes**.
- **Negative review count and low average rating** are highly correlated for products **like Boxing Gloves and Hockey Stick**.
- **Positive reviews (61.6%) and net sentiment score (45%)** indicate room for improvement, especially for underperforming products.

![Customer Review Details](./customer_review_dashboard.jpg)

---

## Recommendations

Based on the insights and findings above, we recommend Shop Easy’s marketing and product teams:

- **Address top negative review themes** (e.g., unclear instructions, value for money) with improved product documentation and targeted product updates.
- **Prioritize checkout experience improvements** for products with high abandonment (Swim Goggles, Basketball) to reduce friction and increase conversions.
- **Optimize campaign and content strategy** by focusing on video and high-engagement content types, and tailoring messaging for countries with high negative sentiment.
- **Monitor and act on sentiment trends** by integrating regular review analysis into product and marketing cycles.
- **Expand positive review solicitation** for high-performing products to boost overall sentiment and trust.

---

## Assumptions and Caveats

- Missing country records were assumed to be from the company’s primary market and coded accordingly.
- Some review texts were missing or incomplete; sentiment analysis was performed only on available data.
- Cart abandonment data was only available for the most recent year; earlier periods may understate true rates.
- Product categories and price buckets were derived from available price data; any pricing errors could affect category assignment.
- Duplicate and null values in customer journey data were cleaned using SQL transformations as described above.

---

*This project demonstrates how combining advanced sentiment analysis with rigorous marketing analytics can drive actionable business improvements for online retail.*


