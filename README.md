# Product-analytics
Quantium is a data analytics and consulting company that specialises in using data to generate commercial insights for businesses, particularly in retail and consumer behaviour. In this project, Quantium provides transaction and customer data that allows us to analyse purchasing behaviour for chips across different customer segments.

Using this dataset, we can explore patterns such as total sales contribution by customer segment, purchasing frequency, brand preferences, and price sensitivity. The goal of this analysis is to identify key customer groups and behavioural trends that can support data-driven marketing and product decisions.
# Data preparation and Customer Analytics
Conduct analysis on our client's transaction dataset and identify customer purchasing behaviours to generate insights and provide commercial recommendations.

## Background information for the task
We need to present a strategic recommendation that is supported by data which she can then use for the upcoming category review however to do so we need to analyse the data to understand the current purchasing trends and behaviours. The client is particularly interested in customer segments and their chip purchasing behaviour. Consider what metrics would help describe the customers’ purchasing behaviour.

Main goals of this task were :
- Examine transaction data - check for missing data, anomalies, outliers and clean them
- Examine customer data - similar to above transaction data
- Data analysis and customer segments - create charts and graphs, note trends and insights
- Deep dive into customer segments - determine which segments should be targetted

Data Cleaning:

Date column was in integer format. So the date column was changed to date time format.
There are 365 days in a year but in the DATE column there are only 364 unique values so one was missing. As it was a Christmas day and store was closed there was no anomaly. Value was kept as zero transaction for "TOT_SALES". December sales
Checked if all the products in given data are chips.
Some product names are written in more than one way. Example : Dorito and Doritos, Grains and GrnWves, Infusions and Ifzns, Natural and NCC, Red and RRD, Smith and Smiths and Snbts and Sunbites. It was cleaned thereafter.
Split and frequency of each word in "PROD_NAME" column. Removed all rows containing "salsa" in "PROD_QTY" column.
Checked for outliers and removed outliers rows in "PROD_QTY" column.
Each word value was counted in "PROD_NAME" column to extract the brand name. Combined brands written in multiple ways. Created a new column "Cleaned_Brand_Names". Cleaned Brand Names

# Data Analysis on Customer Segments

- The 4 main questions answered in data analysis were:

1. Who spends the most on chips (total sales), describing customers by lifestage and how premium their general purchasing behaviour is?
2. How many customers are in each segment?
3. How many chips are bought per customer by segment?
4. What's the average chip price by customer segment?
   
We Groupby sum TOT_SALES column and identified top 3 highest total sales contributing segments.
<img width="826" height="461" alt="Screenshot 2026-02-06 at 16 03 03" src="https://github.com/user-attachments/assets/e122ef44-78cc-4fc7-812a-96102a7a2f1e" />

Total Sales by Segment
The high sales amount by segment "Young Singles/Couples - Mainstream" and "Retirees - Mainstream" are due to their large number of unique customers, but not for the "Older - Budget" segment. Next we'll explore if the "Older - Budget" segment has: High Frequency of Purchase and, Average Sales per Customer compared to the other segment.
Used p-value calculation and found statistically significant TOT_SALES difference (pval < 5%) between "Mainstream Young Midage" to "Budget and Premium Young Midage" segment.
Divided groupby sum to groupby nunique to get average amount of chips bought per customer segment. Older and Young Families bought the highest average amount of chips.
Unstacked the groupby and plotted it by segment: Average Chips per Customer

# Trends and Insights



- Top 3 total sales contributor segment are:
  1. Older families (Budget) $156,864
  2. Young Singles/Couples (Mainstream) $147,582
  3. Retirees (Mainstream) $145,16
- Young Singles/Couples (Mainstream) has the highest population, followed by Retirees (Mainstream). Which explains their high total sales.
- Despite Older Families not having the highest population, they have the highest frequency of purchase, which contributes to their high total sales.
- Older Families followed by Young Families has the highest average quantity of chips bought per purchase.
- The Mainstream category of the "Young and Midage Singles/Couples" have the highest spending of chips per purchase. And the difference to the non-Mainstream "Young and Midage Singles/Couples" are statistically significant.
- Chips brand Kettle is dominating every segment as the most purchased brand.
- Observing the 2nd most purchased brand, "Young and Midage Singles/Couples" is the only segment with a different preference (Doritos) as compared to others' (Smiths).
- Most frequent chip size purchased is 175gr followed by the 150gr chip size for all segments.

# Conclusion and Recommendations
Older Families: Focus on the Budget segment. Strength: Frequent purchase. We can give promotions that encourages more frequency of purchase. Strength: High quantity of chips purchased per visit. We can give promotions that encourage them to buy more quantity of chips per purchase.
Young Singles/Couples: Focus on the Mainstream segment. This segment is the only segment that had Doritos as their 2nd most purchased brand (after Kettle). To specifically target this segment it might be a good idea to collaborate with Doritos merchant to do some branding promotion catered to "Young Singles/Couples - Mainstream" segment. Strength: Population quantity. We can spend more effort on making sure our promotions reach them, and it reaches them frequently.
Retirees: Focus on the Mainstream segment. Strength: Population quantity. Again, since their population quantity is the contributor to the high total sales, we should spend more effort on making sure our promotions reaches as many of them as possible and frequent.
General: All segments has Kettle as the most frequently purchased brand, and 175g (regardless of brand) followed by 150gr as the preferred chip size. When promoting chips in general to all segments it is good to take advantage of these two points.
This can support the Category Manager by identifying where these customer segments are most likely to shop, measuring the impact of placement changes, and providing promotional recommendations such as “Buy 2, Get 1 Free” offers to further increase sales and  measure the impact of trials.

