# Digital Marketing Analysis


![image](https://github.com/user-attachments/assets/23be712d-a5e1-46c4-a0b0-bf990f296f14)


##### Project Overview: Analyze digital marketing campaign performance to optimize ROI and allocate budgets effectively.
##### Key Questions: Which channels generate the highest ROI? What is the cost per lead (CPL) and cost per click (CPC)? How do conversion rates vary by channel?

### Data Sources:

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


### Exploratory Data Analysis 
Analyze the marketing spending.
What to answer
1. Overall ROMI
2.  ROMI by campaigns
3.   Performance of the campaign depending on the date - on which date did we spend the most money on
advertising, when we got the biggest revenue when conversion rates were high and low? What were the average
order values?
4. When buyers are more active? What is the average revenue on weekdays and weekends?
5. Which types of campaigns work best - social, banner, influencer, or a search?
6. Which geo locations are better for targeting - tier 1 or tier 2 cities?

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

1. ROMI: ₹0.40 overall return on marketing investment.
2. Top-Performing Channel: YouTube campaigns had the highest ROMI (₹2.8).
3. Cost Metrics:
  * CPC: 
social media had the lowest CPC at ₹9.2
  * CPL: ₹466.47.
4. Conversion Rates: Influencer marketing had the highest conversion rate (0.18).
5. Geographic Performance: Tier 1 cities generated the highest ROMI.

![Screenshot (63)](https://github.com/user-attachments/assets/e8ce470b-57ce-41eb-93de-d13f2bfd6951)


### Recommendations 
Based on the visual analysis of the data, several actionable insights and recommendations emerge:
* Reallocate Budget: Focus on YouTube and social media campaigns to maximize ROI.

* Target Tier 1 Cities: Increase marketing efforts in high-performing regions.

* Improve Conversion Rates: Optimize landing pages and ad creatives for influencer marketing.


## Business Value: 
Companies can optimize marketing spend and improve campaign performance.



### Limitations 
* Data Scope: The dataset only includes data from specific campaigns, limiting the generalizability of the findings.

* Temporal Bias: The data may not account for recent changes in customer behavior or platform algorithms.
