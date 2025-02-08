# Strategic Digital Marketing Performance Analysis: Evaluating Engagement, Conversion Rates, and ROI for Data-Driven Campaign Optimization


![image](https://github.com/user-attachments/assets/23be712d-a5e1-46c4-a0b0-bf990f296f14)


## Project Overview

This project examines digital marketing campaign performance by analyzing key metrics such as reach, engagement, conversion rates, and return on investment (ROI). The goal is to uncover trends in audience behavior, optimize ad spend, and provide strategic recommendations to enhance digital marketing effectiveness.


![Screenshot (63)](https://github.com/user-attachments/assets/e8ce470b-57ce-41eb-93de-d13f2bfd6951)

### About the Dataset:
The dataset includes:

* Campaign types (social media, email, paid ads, organic search)
* Impressions, clicks, and engagement rates
* Conversion metrics (leads, purchases, sign-ups, etc.)
* Cost per click (CPC) and cost per acquisition (CPA)
* Revenue generated from campaigns
* The data spans multiple platforms (Google Ads, Facebook, Instagram, etc.) over a set timeframe.

### Key Questions
1. Overall ROMI
2.  ROMI by campaigns
3.   Performance of the campaign depending on the date - on which date did we spend the most money on
advertising, when we got the biggest revenue when conversion rates were high and low? What were the average
order values?
4. When buyers are more active? What is the average revenue on weekdays and weekends?
5. Which types of campaigns work best - social, banner, influencer, or a search?
6. Which geo locations are better for targeting - tier 1 or tier 2 cities?

### Data Sources

##### The primary data set used was from Quantum Analytics NG digital marketing performance data "marketing_data.CSV" file, containing detailed information about digital marketing performance in the company 

### Tools

* Excel
* Power Bi

### Data Cleaning/ Preparation Assessment
##### Data quality is essential to ensure accurate and reliable analysis. The dataset was assessed and cleaned through several steps in Power Query, which helped to address data integrity issues. Here is a summary of the data quality processes applied:

* Duplicates Removal: Any duplicate rows were removed to avoid skewed campaign performance data or duplicated metrics.

* Missing Values Handling: Missing or incomplete values in campaign names or metrics (e.g., CPC, CPL) were filled based on contextual data when possible. For revenue data, any missing entries were replaced with estimates where appropriate.

* Data Type Standardization: Numeric fields, such as CPC, CPL, and ROI, were formatted consistently, and date fields were standardized to facilitate time-series analysis.

* Outliers Identification: High and low outliers in campaign performance metrics were reviewed to ensure they represented legitimate data points and were not the result of data entry errors.

* Consistency Checks: Campaign names and channel categories were standardized, addressing any variations in naming conventions across records.

##### Through these steps, the dataset was transformed into a reliable, high-quality foundation for meaningful analysis.

### Dashboard Overview:
The interactive dashboard provides insights into:

* Campaign Performance Summary – Click-through rates (CTR), impressions, and engagement.
* Conversion Funnel Analysis – From reach to final purchase or sign-up.
* Ad Spend vs. ROI – Cost-effectiveness of campaigns.
* Platform Comparison – Best-performing marketing channels.
* Audience Insights – Age groups, demographics, and behaviors.



### Data Analysis 
##### Includes some interesting Dax Measures i worked with 

```
Average_Order_Value = 
DIVIDE(
    SUM('Marketing'[Revenue]),
    SUM('Marketing'[Orders]),
    0
) 

CAC_By_Category = 
DIVIDE(
    SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Orders]),
    BLANK()
)

Conversion_Rate_1 = 
DIVIDE(
    SUM('Marketing'[Leads]),
    SUM('Marketing'[Clicks]),
    0
)

Conversion_Rate_2 = 
DIVIDE(
    SUM('Marketing'[Orders]),
    SUM('Marketing'[Leads]),
    0
)

CPC_By_Category = 
DIVIDE(
    SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Clicks]),
    BLANK()
)

CPC_By_Tier = 
DIVIDE(
    SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Clicks]),
    BLANK()
)

CPL_By_Category = 
DIVIDE(
    SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Leads]),
    BLANK()
)

CPL_By_Tier = 
DIVIDE(
    SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Leads]),
    BLANK()
)

ROMI = 
DIVIDE(
    SUM('Marketing'[revenue]) - SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Rounded_Mark_Spent]),
    BLANK()
)


ROMI_By_Category = 
DIVIDE(
    SUM('Marketing'[Revenue]) - SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Rounded_Mark_Spent]),
    BLANK()
)

ROMI_By_Tier = 
DIVIDE(
    SUM('Marketing'[Revenue]) - SUM('Marketing'[Rounded_Mark_Spent]),
    SUM('Marketing'[Rounded_Mark_Spent]),
    BLANK()
)

Total_Revenue_By_Day = 
SUMX(
    VALUES('Marketing'[DayOfWeek]),
    SUM('Marketing'[Revenue])
)
```

### Key Insights and Findings 

![Oluwanifesimi Adebayo Digital Marketing Analysis](https://github.com/user-attachments/assets/3f5c9052-ca92-4052-bfb5-55dfb902bc9d)

###### The analysis findings are as follow: 

### Sum of Revenue Vs Sum of Amount Spent on Marketing by Days of the week

![image](https://github.com/user-attachments/assets/444f9691-67fe-41f2-b4fc-25cce14db11a)

On Friday, INR 6.3M was spent on marketing and yielded a total revenue of INR 9.6M followed by Saturday, where INR 5.7M was spent on marketing and resulted to INR 8.5M as compared to other days of the weeks

### Total Revenue In a Day

![image](https://github.com/user-attachments/assets/2a3d054a-b7dc-4bdf-82e8-8baf0426539b)

The total revenue in a day is over INR 300M 

### Average Order Value by Category

![image](https://github.com/user-attachments/assets/ed669b44-0cb2-4774-a76d-05a6b39ae7a7)

This is the average value generated by each marketing medium with influencer with the highest accounting for over 7,000 orders compared to other marketing medium like social, search and media 


### Recommendations 
Based on the visual analysis of the data, several actionable insights and recommendations emerge:
* Reallocate Budget: Focus on YouTube and social media campaigns to maximize ROI.
* Optimize Landing Pages: Improve website user experience to reduce conversion drop-offs.
* Shift Budget to High-ROI Channels
* Enhance Retargeting Strategies: Retarget users who abandoned carts to increase conversions.
* Boost Organic Reach: Leverage SEO and content marketing to reduce dependency on paid ads.
* Target Tier 1 Cities: Increase marketing efforts in high-performing regions.
*  Improve Conversion Rates: Optimize landing pages and ad creatives for influencer marketing.

### Conclusion 
1. Media ads drive engagement, but Influencers yield the best ROMI.
2. Conversion drop-off suggests a need for better landing page optimization.
3. Organic search traffic is a strong performer in long-term marketing.
4. Ad spend should be allocated strategically based on channel performance.
5. Retargeting strategies can recover lost conversions.
6. Audience targeting should focus on high-engagement mobile users.

Overall, these insights highlight opportunities for strategic decision-making that align with market trends and operational efficiency. By implementing these recommendations, the organization can continue to thrive, enhancing customer satisfaction and driving sustained revenue growth.
