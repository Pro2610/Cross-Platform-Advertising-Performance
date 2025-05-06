# 📣 Marketing Performance Dashboard: Facebook & Google Ads Analytics

## 🔍 Overview
This project analyzes performance data from Facebook Ads and Google Ads to evaluate the efficiency of marketing campaigns across both platforms.  
Using SQL, I joined and cleaned raw ad data, unified the schema, and created a foundation for cross-platform ad performance tracking.

## 🧰 Tools & Technologies
- SQL (BigQuery or PostgreSQL)
- Data Joins, CTEs, Aggregations
- Advertising Datasets (Facebook & Google Ads)

## 🧠 Business Goal
To understand the return on advertising investment (ROAS), user engagement, and conversion potential across different campaigns and ad sets.

## 📈 Key Analyses
- Merged Facebook and Google Ads data into a single view
- Aggregated ad performance metrics by date, platform, campaign, and ad set
- Filtered out invalid data (e.g., 0 impressions or clicks)
- Summarized spend, impressions, clicks, and revenue across channels

## 🧪 Sample Query
```sql
-- Final Aggregated Output
SELECT
  ad_date,
  media_source,
  campaign_name,
  adset_name,
  SUM(spend) AS total_spend,
  SUM(impressions) AS total_impressions,
  SUM(clicks) AS total_clicks,
  SUM(value) AS total_value
FROM all_ads_data
WHERE spend > 0 AND clicks > 0 AND impressions > 0
GROUP BY ad_date, media_source, campaign_name, adset_name
ORDER BY ad_date, media_source;
