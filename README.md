# saas-product-usage-retention-analysis
SaaS analytics dashboard analyzing DAU, funnels, and cohort retention
# SaaS Product Usage & Retention Analysis

## Overview
This project analyzes user engagement, adoption, and retention patterns for a SaaS product using synthetically generated data. The goal is to simulate real-world product analytics workflows and demonstrate how product usage data can be transformed into actionable insights for improving onboarding, engagement, and long-term retention.

The analysis focuses on core SaaS metrics such as **DAU, MAU, engagement funnels, and cohort-based retention**, and presents findings through an interactive dashboard built using **Google Looker Studio**.

---

## Problem Statement
SaaS companies often struggle to understand:
- How actively users engage with the product over time
- Where users drop off during onboarding and early usage
- Which cohorts retain better and why
- How engagement differs across subscription plans and geographies

This project addresses these challenges by modeling user behavior data and applying structured analytical techniques commonly used by product and growth teams.

---

## Dataset Overview
The project uses four CSV files:

| File Name | Description |
|----------|-------------|
| `users.csv` | User signup information and geography |
| `events.csv` | User activity events within the product |
| `subscriptions.csv` | Subscription plans and lifecycle |
| `cohort_retention.csv` | Precomputed cohort retention metrics |

---

## Data Generation Methodology

### Overview
Due to the confidential nature of real SaaS production data, this project uses **synthetically generated datasets** designed to closely reflect real-world user behavior. The data generation process intentionally models realistic scenarios such as onboarding activity, engagement decay, feature adoption, and churn.

All datasets were generated using **Python (Pandas & NumPy)** in **Google Colab**.

---

### Users Dataset (`users.csv`)
Represents individual user accounts.

**Generation approach:**
- User signups distributed across multiple months to enable cohort analysis
- Each user assigned:
  - Unique `user_id`
  - `signup_date`
  - `country` sampled from common SaaS regions
- Signup timestamps randomized to avoid artificial clustering

**Purpose:**
- Define cohorts
- Support geographic segmentation
- Serve as the primary join table

---

### Events Dataset (`events.csv`)
Simulates user interactions within the product.

**Generation approach:**
- Events generated only after user signup date
- Multiple events per user over time
- Event types include:
  - `login`
  - `create_ticket`
  - `comment`
  - `view_board`
- Event frequency decays over time to simulate churn
- Engaged users generate multiple events per session

**Purpose:**
- Calculate DAU and MAU
- Analyze feature adoption
- Build engagement funnels
- Support retention analysis

---

### Subscriptions Dataset (`subscriptions.csv`)
Models monetization and plan segmentation.

**Generation approach:**
- Users assigned to Free, Pro, or Enterprise plans
- Paid users assigned higher engagement probability
- Subscription periods aligned with signup behavior

**Purpose:**
- Compare Free vs Paid engagement
- Segment retention by plan type
- Enable monetization analysis

---

### Cohort Retention Dataset (`cohort_retention.csv`)
Derived from users and events data.

**Computation approach:**
- Users grouped by signup month
- Active users counted in subsequent months
- Retention calculated as:

- Structured for cohort heatmap visualization

**Purpose:**
- Identify early churn patterns
- Compare cohort performance over time
- Support product retention insights

---

## Analysis Performed

### Key Metrics
- Daily Active Users (DAU)
- Monthly Active Users (MAU)
- Stickiness (DAU / MAU)
- Active Users by Plan Type

### Funnel Analysis
- Signup → Login
- Login → Feature Usage
- Feature Usage → Continued Engagement

### Retention Analysis
- Month-over-month cohort retention
- Engagement decay patterns
- Comparison across plans and cohorts

---

## Dashboard
An interactive dashboard was built using **Google Looker Studio** and includes:

- KPI scorecards for DAU, MAU, and Active Users
- Engagement trend analysis
- User funnel visualization
- Cohort retention heatmap
- Plan-based segmentation views

> 📊 The dashboard enables stakeholders to explore user behavior dynamically and identify actionable product insights.

---

## Key Insights
- Significant user drop-off occurs within the first week after signup
- Users who engage with core features early demonstrate stronger retention
- Paid users exhibit higher engagement consistency than free users
- Certain signup cohorts outperform others, indicating onboarding quality impact

---

## Tools & Technologies
- Python
- Pandas
- NumPy
- Google Colab
- Google Sheets
- Google Looker Studio


