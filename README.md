# Solitaire Game Analytics – Power BI Project

## Project Overview
This Power BI project analyzes a US-centric Solitaire-style mobile game with 100 levels.  
It is designed as a full-stack analytics project for gaming companies, covering:

- User Acquisition (UA): installs, channels, campaigns, retention, LTV
- Engagement: time spent, level conversion, churn paths
- Monetization: ads vs IAP, ARPDAU, ARPPU, eCPM
- Prediction: campaign-specific LTV horizons (30, 60, 90, 120, 150, 365 days)

The dataset is synthetic but realistic, generated to mimic an 80% Ads / 20% IAP revenue split.

---

## Repository Structure
```text
solitaire-game-powerbi/
 ├─ data/
 │   ├─ users.csv
 │   ├─ daily_metrics.csv
 │   ├─ level_events.csv
 │   ├─ churn_events.csv
 │   ├─ campaign_retention_arpdau.csv
 │   ├─ ltv_prediction.csv
 │   ├─ time_spent_by_day.csv
 │   └─ data_dictionary.csv
 ├─ assets/
 │   ├─ product_dashboard.png
 │   ├─ levels_dashboard.png
 │   ├─ churn_dashboard.png
 │   ├─ retention_dashboard.png
 │   ├─ ltv_dashboard.png
 │   ├─ monetization_dashboard.png
 │   └─ ua_dashboard.png
 ├─ Solitaire_Game.pbix
 └─ README.md
```

## Dashboards & Reports

### 1. Product Overview
**Purpose:** Provides an overall snapshot of the game’s health — installs, DAU, engagement, and revenue.  
**KPI Cards:** Installs, DAU, Total Revenue, Ads %, IAP %, ARPDAU, Avg Time Spent.  
**Visuals:**
- DAU trend (line chart)  
- ARPDAU trend (line chart)  
- Revenue split (stacked area: Ads vs IAP)  
- OS/Device split (map or treemap)  

![Product Dashboard](/assets/product_dashboard.png)

---

### 2. Level Conversion & Difficulty
**Purpose:** Track player progression through levels and identify high drop-off points.  
**KPI Cards:** Avg Level Reached, Highest Level Completed, Level with Highest Dropoff.  
**Visuals:**
- Conversion % by level (line chart)  
- Fail % and Retry % across levels (line chart)  
- Avg Moves & Booster Use (combo chart)  
- Table of Top Drop-off Levels (Level | Starts | Completes | Conversion % | Fail % | Booster Use %)  

![Levels Dashboard](/assets/levels_dashboard.png)

---

### 3. Churn Journeys
**Purpose:** Analyze when and why players leave the game.  
**KPI Cards:** Churned Users, Avg Churn Day, Avg Last Level.  
**Visuals:**
- Distribution of churn reasons (stacked bar)  
- Last level × reason heatmap (matrix with conditional formatting)  
- Booster vs No-Booster churn (matrix or bar chart)  
- Churn flow (optional Sankey diagram)  

![Churn Dashboard](/assets/churn_dashboard.png)

---

### 4. Retention & Engagement
**Purpose:** Measure how sticky the game is and how much time users spend.  
**KPI Cards:** D1 Retention %, D7 Retention %, D30 Retention %, Avg Session Time.  
**Visuals:**
- Retention curves by campaign (line chart, day-since-install vs retention rate)  
- Cohort heatmap of retention (matrix, conditional formatting)  
- Avg Time Spent vs day-since-install (line chart)  
- Table of D0–D30 time spent (minutes)  

![Retention Dashboard](/assets/retention_dashboard.png)

---

### 5. LTV & Prediction
**Purpose:** Forecast campaign-specific value over time.  
**KPI Cards:**
- LTV (Selected Horizon)  
- Predicted Revenue (Installs × LTV)  
- D1 Retention %  
- D30 Retention %  
- ARPDAU @ D7  

**Visuals:**
- LTV by campaign (bar chart, horizon selectable by slicer)  
- Retention × ARPDAU combo (line + area chart)  
- Campaign summary table (Installs, Retention, ARPDAU, LTV)  

![LTV Dashboard](/assets/ltv_dashboard.png)

---

### 6. Monetization
**Purpose:** Explain ad vs IAP revenue drivers.  
**KPI Cards:** Total Revenue, Ads %, IAP %, ARPPU, Effective eCPM.  
**Visuals:**
- Revenue split over time (stacked area: Ads vs IAP)  
- Ad load analysis (impressions per DAU vs eCPM, combo chart)  
- IAP by price point (bar chart)  
- OS monetization split (clustered column: iOS vs Android)  
- Ad vs IAP share (pie chart, optional)  

![Monetization Dashboard](/assets/monetization_dashboard.png)

---

### 7. User Acquisition
**Purpose:** Evaluate UA quality and efficiency of campaigns.  
**KPI Cards:** Installs, D1 Retention %, D30 Retention %, ARPDAU @7, LTV @90.  
**Visuals:**
- Installs trend by channel (line chart)  
- Retention curves by campaign (line chart)  
- LTV @90 by campaign (bar chart)  
- Revenue split by OS (100% stacked column)  
- Treemap of Installs by Campaign (optional)  

![User Acquisition Dashboard](/assets/ua_dashboard.png)

---

## Dataset Description
The repository includes multiple CSVs with realistic, US-focused synthetic data:

- **users.csv** → User installs, OS, device, channel, campaign, state  
- **daily_metrics.csv** → DAU, ad impressions, time spent, daily ad/IAP revenue  
- **level_events.csv** → Level starts, completes, fails, retries with moves and booster usage  
- **churn_events.csv** → Churn day, last level, churn reason, last session details  
- **campaign_retention_arpdau.csv** → Cohort retention & ARPDAU by campaign × day-since-install  
- **ltv_prediction.csv** → Campaign-specific LTV predictions at multiple horizons  
- **time_spent_by_day.csv** → Avg session minutes D0–D30  
- **data_dictionary.csv** → Column-level descriptions  

---
