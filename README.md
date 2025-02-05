# funnel_and_cohort_analysis

# 1. Introduction to Funnel Analysis
Hi! I'm Retno Anggraeni, BI Batch 11 student at dibimbing. I'm excited to share my experience in creating a case study project to explore insights from data displayed in funnel chart visualizations and cohort analysis. 

This project is a project that has very important information in a business and can determine the best strategy to advance the business.

## Objectives
- Identify patterns, trends, or significant findings in the data
- Visualization of exploratory data
- Create Funnel Chart
- Create Cohort Chart

## Work Flow
1. Data Understanding
2. Import Data to Tableau
3. Calculated Field
4. Data Visualization
5. Interpret & Summarize the results
6. Decision Making

## Funnel Analysis
- Funnel analysis is a method for analyzing and measuring the user conversion process within systems like websites or apps by tracking the steps users take from initial engagement to completion, such as purchasing a product.
- Its main purpose is to pinpoint where users tend to drop off, enabling marketing teams or developers to identify bottlenecks and enhance user experience.
- This analysis is typically performed after launching a new product, during shifts in marketing strategy, or regularly to improve conversion rates and sales efficiency.

## Dataset Information
The dataset has 418,279 entries and 12 columns. The following summarizes the key information:

- Columns with Complete Data: event_id, session_id, sequence_number, created_at, browser, traffic_source, and event_type contain 418,279 values.
- Columns with Missing Data: user_id, age, gender, city, and country have only 265,687 or 262,839 non-null values, indicating that there is missing data.
- Data Type: Consists of integers (int64), decimal numbers (float64), and objects (string).
- Potential Analysis: This dataset can be used to analyze user behavior based on demographics, traffic source, and time of occurrence.
- Overall, this dataset is rich in information but needs to address missing data for further analysis.

## Calculated Field
- customer_first_purchases: {FIXED[user_id]: MIN(DATETRUNC('month', [created_at]))}
- customer_early_periode: {FIXED[customer_first_purchases]: COUNTD([user_id])}
- retention_rate: COUNTD([user_id]/SUM[customer_early_periode])
- elapsed_monthly: DATEDIFF('month', [costumer_first_purchases], DATETRUNC('month', [created_at]))

## Event Engagement Funnel from Home to Purchases
- This funnel chart represents the stages of customer activity as well as the number of occurrences in each stage.
- The data shows that the activity with the highest frequency performed by customers is adding items to the cart.
- The activity with the lowest frequency is canceling a purchase.
- Email was recorded as the main source of traffic driving customer engagement, followed by paid advertising.
- The traffic source with the lowest contribution came from organic search.

# 2. Introduction to Cohort Analysis
- Cohort analysis is a data analysis method used to understand the behavior of a group of individuals or entities that share similar characteristics or experiences over a period of time.
- By analyzing cohort behavior over time, companies can identify trends, patterns, and the effectiveness of marketing strategies, and generate deeper insights into user retention, loyalty, and product influencing factors.
- By conducting cohort analysis at these times, companies can gain deeper insights and more appropriate strategies for growth and user satisfaction.

## Result of Cohort Analysis
- The number of users fluctuated throughout the period from January to November 2023.
- The month of February saw a decrease in user numbers, while the months of May and July-August experienced increases. However, there were declines in June and September.
- Overall, the number of users increased from 2246 in January to 2604 in November. The percentage increase in user numbers fluctuated, with an average decrease of 4% from January to November.
- This suggests that although there were some months of significant growth, overall growth was not as strong as expected.
- Furthermore, there was a systematic downward trend from month to month, indicating a potential problem with user retention.

# TREND IDENTIFICATION RESULTS
## 1. Monthly Retention Rate
- Retention rate based on event_type shows three similar curves, namely for product, purchase, and chart categories.
- Event_type home has the lowest curve pattern compared to the other three categories.
- The retention rate curve shows a sharp decline at the beginning of the period, especially from January to February, with a very steep pattern.
- Retention from the five traffic sources shows a similar curve pattern, with a consistent downward trend from January to December, as well as a sharp drop occurring between January and February.
- The email traffic source had the highest retention rate compared to the other sources throughout the analysis period.
- The retention curves for Facebook and YouTube show almost identical patterns, indicating similar user behavior from both sources.

## 2. Data Distribution
- The distribution of visitors by gender shows that despite fluctuations, the proportion of female visitors is consistently higher than that of male visitors.
- However, this difference does not have strong statistical significance, indicating a generally balanced trend.
- The highest total users by traffic source is email with 120,327 subscribers
- The lowest total users by traffic source is organic with 13,120 subscribers.
- The highest total users by event type are product and chart with 95,634 subscribers.
- The least total users by event type is cancel with 0 customers.

## 3. Map Distribution of Retention Rate
Based on the distribution map of retention rates, it can be observed that China has the highest retention rate at 33.66%, while Spain has the lowest retention rate at 0.04%.

# Summary
Customer Activity Stages:
- Highest Frequency: Adding items to the cart.
- Lowest Frequency: Cancelling a purchase.
Traffic Sources:
- Main Source: Email, driving significant customer engagement.
- Next Best Source: Paid advertising.
- Lowest Contribution: Organic search.
Retention Rates:
- Event Types: Similar curves for product, purchase, and cart categories; home has the lowest retention.
- Overall Trends: Sharp decline in retention from January to February, with a downward trend throughout the year.
- Email shows the highest retention compared to other sources.
- Facebook and YouTube have nearly identical retention patterns.
Gender Distribution:
- A higher proportion of female visitors compared to male, but no significant statistical difference.
Geographic Performance:
- Highest Retention: China (33.66%).
- Lowest Retention: Spain (0.04%).
- User Distribution:
  Highest Total Users (Traffic Source): Email (120,327).
  Lowest Total Users (Traffic Source): Organic (13,120).
  Highest Total Users (Event Type): Product and chart (95,634).
  Least Total Users (Event Type): Cancelling (0).
