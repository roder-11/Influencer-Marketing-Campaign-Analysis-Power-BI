# 📊 Influencer-Marketing-Campaign-Analysis-Power-BI
An end-to-end Business Intelligence project that measures the **performance, ROI and customer impact of social-media influencer campaigns** (Instagram, YouTube, TikTok) for a fashion e-commerce brand.

  ![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
  ![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge)
  ![Power Query](https://img.shields.io/badge/Power%20Query%20(M)-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
  ![Data Modeling](https://img.shields.io/badge/Star%20Schema-5C2D91?style=for-the-badge)


 ## 🎯 Business Context
A fashion brand sells **dresses, jackets, pants, accessories and tops** and invests in influencer marketing across three social platforms. Marketing leadership needs a single, interactive view to answer: *which campaigns, influencers, platforms and audiences actually generate revenue, and is the spend worth it?*

This report consolidates campaigns, influencers, orders, products and customers into one model and delivers **6 analytical dashboard pages** (plus 3 hidden supporting pages) with navigation buttons, slicers and conditional formatting.

## ❓ Objectives & Business Questions
| # | Business question | Dashboard page |
|---|---|---|
| 1 | What is the overall sales, order volume, conversion rate and ROI over the period? | Overall Performance |
| 2 | Which platform and which month generate the most revenue and conversions? | Marketing Campaign |
| 3 | Which influencers deliver the best ROI, and does follower count translate into conversions? | Influencers & Performance |
| 4 | Which products, sub-categories, seasons and styles drive sales? | Products & Sales Trends |
| 5 | Who are the customers (age, gender, income, location) and are we hitting new-customer targets? | Demographic Analysis |
| 6 | Is there a measurable relationship between cost, price, age, conversion and revenue? | Correlation & Advanced Insights |

## 🛠 Tools & Skills
- **Power BI Desktop** — report design, page navigation buttons, conditional formatting, KPI cards, treemaps, funnel, scatter plots with trend lines, map
- **Power Query (M)** — import from Excel, type casting, value cleaning, conditional column (`Network Code`)
- **DAX** — measures for ROI, customer counts and new-customer rate
- **Data modeling** — star-schema style model with 1:* relationships and a shared date dimension
- **Storytelling** — consistent layout, titles, slicers per page and a left-hand navigation bar

## 🗃 Dataset
Six Excel source files (campaigns, influencers, influencer-campaign performance, orders, products, customer demographics) covering **07 June 2024 → 28 June 2025** (the report's date slicer range).

## 🧩 Data Model

<img width="1367" height="654" alt="All the Tables" src="https://github.com/user-attachments/assets/90ae33f3-2093-4afd-a99d-ec21992c07a1" />

_ _ _

## Tables
| Role | Table |
|---|---|
| Fact | Orders, Influencer Campaign Performance |
| Dimensions | Campaign, Influencers, Products, Customer, Date |

## Relationships
| From (many) | To (one) | Cardinality | Filter direction |
|---|---|---|---|
| Orders[Campaign_ID] | Campaign[Campaign_ID] | Many → One | Single |
| Orders[Product_ID] | Products[Product_ID] | Many → One | Single |
| Orders[Source_Influencer_ID] | Influencers[Influencer_ID] | Many → One | Single |
| Orders[Order_Date] | Date[Date] | Many → One | Single |
| Influencer Campaign Performance[Campaign_ID] | Campaign[Campaign_ID] | Many → One | Single |
| Influencer Campaign Performance[Source_Influencer_ID] | Influencers[Influencer_ID] | Many → One | Single |
| Customer[Source_Influencer_ID] | Influencers[Influencer_ID] | Many → One | Single |
| Customer[Source_Campaign_ID] | Campaign[Campaign_ID] | Many → One | Single |
| Customer[Source_Campaign_ID] | Orders[Campaign_ID] | Many ↔ Many | Single |


## 🖥 Dashboard Tour
_ _ _

## 1️⃣ Performance overview

- Sales **$352.85M**; average conversion rate **3.75%**; marketing cost **$2.91M**; average cost per post **$197.2K**; **100K conversions** (influencers page).
- Top campaigns by conversions: CMP009 (10,117), CMP006 (10,116), CMP005 (10,110), CMP010 (10,033). CMP009 shows the highest ROI value among the top 10 ($1,233.49K) and CMP002 / CMP007 / CMP004 show a rising trend.


**Overall performance**


<img width="1367" height="696" alt="1_Overall_Performance" src="https://github.com/user-attachments/assets/8c42aaa0-870d-45b4-86a0-bb40b1f32262" />


### 2️⃣ Marketing Campaign Analysis


Conversion rate, revenue, marketing cost and ROI, with platform split (orders and sales), annual conversion-rate trend and an influencer ROI ranking. Slicers: year, month, quarter, campaign, platform.

**Marketing campaign**


<img width="1366" height="707" alt="2_Campaign Marketing" src="https://github.com/user-attachments/assets/18b9044e-9cab-4ba1-864b-986670bb03f8" />


## 3️⃣ Influencers & Performance

- Revenue by influencer level: **Mega 58.51%**, **Macro 35.47%**, Micro 4.63%, Nano the remainder.
- Highest ROI: **INF009**, **INF003**, then INF006, INF016, INF001. Lowest: INF012, INF008, INF019.
- Several influencers with high revenue (e.g. INF008, INF019, INF012) have low ROI, meaning revenue size and efficiency do not go together.
- Followers fall sharply from Instagram to YouTube to TikTok, and conversions follow the same pattern.
- Cost and revenue show a strong positive relationship, driven by a few high-spend influencer groups.


**Influencers**

<img width="1367" height="711" alt="3_Influencers and Campaign" src="https://github.com/user-attachments/assets/72ae1785-0f3e-4bd6-be96-593105d942fd" />


## 4️⃣ Products & Sales Trends

- Product revenue: **Dresses ≈ 35%**, Jackets ≈ 24%, Pants ≈ 16%, Accessories ≈ 16%.
- Best-selling products: PRD007 (Pants, $42.87M), PRD008 (Dresses), PRD017 (Dresses), PRD022 (Jackets), PRD003 (Dresses).
- **Leather** sub-category: $173.45M, versus $12.61M for polyester.
- Season: All-Season $145.83M, Summer $119.33M, Winter $87.70M.
- Monthly sales peak in **August (~$58M)** and drop to **~$6M in April and October**.
- Spend by gender: Female ≈ 41%, Male ≈ 33%, Unisex ≈ 26%. Style preferences are evenly spread (Luxury slightly ahead).


**Products and sales trends**


<img width="1368" height="706" alt="4_Product And Sales Trends" src="https://github.com/user-attachments/assets/ca4df36e-87df-481c-942c-746ad741984b" />


## 5️⃣ Customer & Demographic Analysis

- 9,036 new customers vs goal 8,072 (**+11.94%**).
- Average age 30; gender split almost even.
- Order value by income bracket: Medium $142M, Low $128M, High $47M.
- Average order value by age peaks around 30 and declines steadily afterwards.
- Locations are Indian states and union territories (e.g. Andhra Pradesh, Assam, Bihar, Delhi, Goa, Gujarat, Karnataka…).


**Demographic analysis**


<img width="1369" height="701" alt="5_Demographic Analysis" src="https://github.com/user-attachments/assets/1b199fa0-1f8d-4d5a-b5d6-2d002b4e269c" />


### 6️⃣ Correlation & Advanced Insights

| Pair | Observation |
|---|---|
| Marketing cost vs revenue | Strong positive trend |
| Unit price vs quantity ordered | Almost flat |
| Conversion rate vs ROI | Almost flat / slightly negative |
| Age vs average order value | Rises to ~30, then falls |


**Correlation analysis**


<img width="1367" height="708" alt="6_Correlation Analysis" src="https://github.com/user-attachments/assets/31893b7f-1559-405c-b80a-c4647a003d48" />


## 💡 Key Findings
*(Figures read from the dashboards; period 07/06/2024 – 28/06/2025.)*

- **Total sales: $352.85M**, average conversion rate **3.75%**, marketing cost **$2.91M**.
- **Instagram** is the largest revenue channel on the overview page (**$241.9M**), ahead of YouTube ($67.2M) and TikTok ($43.75M).
- **Mega influencers generate 58.5%** of revenue and **Macro 35.5%**; Micro and Nano together contribute under 6%.
- **Dresses lead product revenue (≈35%)**, then Jackets (≈24%) and Pants (≈16%). **Leather** is the top sub-category by far ($173.45M).
- **Seasonality:** monthly sales peak in **August (~$58M)** and fall to **~$6M in April and October**; the overview chart peaks in **June**.
- **Highest-ROI influencers:** INF009 and INF003, then INF006, INF016 and INF001.
- **Customers:** 9,036 new customers vs a goal of 8,072 (**+11.94%**); average age **30**; almost perfectly balanced gender split (30,103 men / 30,030 women).
- **Income:** Medium-income customers generate the most order value ($142M), then Low ($128M) and High ($47M).
- **Correlations:** cost and revenue are strongly positively related; **order value peaks around age 30** then declines; unit price vs quantity and conversion rate vs ROI show a nearly flat trend.


## Recommendations
1. Maintain Mega/Macro partnerships; pilot Micro/Nano influencers with performance-based pay.
2. Renew top-ROI influencers; renegotiate or drop the lowest-ROI ones.
3. Concentrate budget before the August peak and design reactivation offers for April and October.
4. Expand dress and leather assortments; bundle accessories and tops.
5. Focus creative and targeting on the ~30-year-old, medium-income segment.
6. Fix platform attribution and KPI definitions before using the numbers for budget decisions.

## 👤 Author
**Jean Rodrigue Awono** — Business Intelligence & Data Analyst, transitioning to Data Engineering
📍 Douala, Cameroon
🔗 [GitHub](https://github.com/Jean-Rodrigue-Awono) · [LinkedIn](https://www.linkedin.com/in/your-linkedin)
