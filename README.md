# 📊 Olist E-Commerce Analysis
### Sales Performance, Delivery Experience & Customer Retention

An end-to-end data analytics project exploring **96,000+ delivered orders** from Olist, a Brazilian e-commerce marketplace.

Built using **Python, Pandas, and Tableau**, this project investigates sales performance, delivery efficiency, customer satisfaction, and customer retention to uncover actionable business insights.

<p align="center">
  <a href="https://public.tableau.com/app/profile/muhamad.fahrudin/viz/OlistE-CommerceDashboard_17938854673210/OlistE-CommerceDashboard">
    <img src="https://img.shields.io/badge/View%20Interactive%20Dashboard-Tableau-blue?style=for-the-badge&logo=tableau" alt="Tableau Dashboard"/>
  </a>
</p>

<p align="center">
  <img src="images/dashboard.png" alt="Olist E-Commerce Dashboard Preview" width="100%"/>
</p>

---

## 📌 Project Overview

This project analyzes Olist's e-commerce transaction data to understand three important business areas:

- **Sales Performance:** How revenue develops over time and which product categories contribute the most.
- **Delivery Experience:** Whether late deliveries are associated with lower customer satisfaction and where delays are concentrated.
- **Customer Retention:** How frequently customers return and which customer segments contribute the most revenue.

The goal is to transform raw transactional data into meaningful insights and practical business recommendations.

## 🎯 Business Questions

| No. | Business Question | Analytical Focus |
|:---:|---|---|
| 01 | How did sales develop over time, and which product categories drive revenue? | Revenue trends & product performance |
| 02 | Do late deliveries hurt customer reviews, and where are delays concentrated? | Delivery performance & customer satisfaction |
| 03 | How many customers return to buy again, and which customers matter most? | Repeat purchase, cohort retention & RFM segmentation |

## 📂 Dataset

**Source:** [Brazilian E-Commerce Public Dataset by Olist – Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

| Description | Details |
|---|---:|
| Delivered Orders | 96,203 |
| Unique Customers | 93,096 |
| Order Items | 109,872 |
| Analysis Period | January 2017 – August 2018 |
| Tables Used | 8 datasets |

**Tables included:**
- Orders
- Order Items
- Customers
- Payments
- Reviews
- Products
- Sellers
- Product Category Translation

**Data Scope:** Only orders with `delivered` status were included. Data from 2016 was excluded because monthly order volume was too small for meaningful comparison.

## 🛠️ Tools & Methodology

| Stage | Tools | Activities |
|---|---|---|
| Data Preparation | Python, Pandas, NumPy | Data loading, missing value checks, duplicate checks, date conversion and table merging |
| Feature Engineering | Python | Created delivery days, delay days, late delivery flags and monthly order features |
| Exploratory Data Analysis | Pandas, Matplotlib, Seaborn | Sales trends, category performance, delivery delays, review scores and customer analysis |
| Customer Analysis | Python | RFM segmentation and cohort retention analysis |
| Data Visualization | Tableau Public | Interactive dashboard development and business insight presentation |

### Key Data Modeling Decisions

- Revenue is calculated using item `price`, excluding freight costs.
- Customers are identified using `customer_unique_id` rather than `customer_id`, since the latter can differ across orders.
- Delivery delay and review analysis are performed at the order level to avoid double-counting multi-item orders.
- Payment records are excluded from revenue calculations because a single order may contain multiple payment records.
- The latest review per order is retained for review analysis.

## 📈 Key Business Findings

### 1. Revenue Growth Was Primarily Driven by New Customers

Monthly revenue increased from **R$112K in January 2017** to a peak of **R$988K in November 2017**.

Throughout 2018, monthly revenue remained relatively flat, ranging between approximately R$830K and R$980K.

The top 10 product categories contributed around **62% of total revenue**, led by:

- Health & Beauty
- Watches & Gifts
- Bed, Bath & Table

**Business Insight:** Revenue growth became less pronounced after 2017, highlighting the importance of customer acquisition and repeat-purchase strategies.

### 2. Customer Retention Is Extremely Low

Approximately **97% of customers made only one purchase**.

Only 3.0% of customers placed more than one order.

Monthly cohort retention in the month following the first purchase ranged between **0.2% and 0.7%**, remaining relatively stable across cohorts.

**Business Insight:** The marketplace relies heavily on acquiring new customers rather than generating repeat purchases.

### 3. High-Value One-Time Buyers Contribute Most of the Revenue

Customers in the top spending quartile who purchased only once represent 23.2% of customers but generate 57.8% of revenue.

| Customer Segment | % of Customers | % of Revenue |
|---|---:|---:|
| One-time, High Value | 23.2% | 57.8% |
| One-time, Recent | 36.9% | 18.5% |
| One-time, Inactive | 36.9% | 18.1% |
| Repeat, Active | 1.6% | 3.1% |
| Repeat, Inactive | 1.3% | 2.4% |

**Business Insight:** High-value customers represent an important retention opportunity. Encouraging even a small portion of these customers to purchase again could help strengthen long-term revenue.

### 4. Late Deliveries Are Associated with Significantly Lower Review Scores

| Delivery Performance | Average Review Score |
|---|---:|
| On-Time Delivery | 4.29 |
| Late Delivery | 2.27 |

Only **6.8% of delivered orders** arrived late, but the difference in average review scores is substantial.

**Business Insight:** Delivery reliability is closely associated with customer satisfaction and should be treated as an important part of the customer experience.

### 5. Delivery Delays Are Concentrated in Specific Regions

States with the highest late delivery rates:

| State | Late Delivery Rate |
|---|---:|
| Maranhão | 17.5% |
| Ceará | 13.8% |
| Bahia | 12.2% |

Rio de Janeiro also stands out:

- Accounts for 12.8% of all orders.
- Contributes 22.9% of all late orders.
- Has an average delivery time of approximately 14.8 days.
- Records a 12.1% late delivery rate, compared with 6.1% in Rio Grande do Sul.

Despite having similar average delivery times, the late delivery rates differ considerably.

**Business Insight:** This suggests potential issues in delivery performance or estimated delivery dates rather than distance alone.

## 💡 Business Recommendations

Based on the analysis, three recommendations are proposed:

**1. Develop a Retention Program for High-Value Customers**

Prioritize one-time, high-value buyers through personalized promotions, targeted campaigns, and incentives for their next purchase.

**2. Investigate Delivery Performance in Rio de Janeiro and Northeast Brazil**

Focus on regions with disproportionately high late delivery rates. If Rio de Janeiro's late delivery rate decreased to São Paulo's level of 4.5%, the overall late delivery rate could potentially decline from 6.8% to approximately 5.8%.

*This is a rough scenario estimate assuming other regions remain unchanged.*

**3. Improve Estimated Delivery Time Accuracy**

Review delivery estimation methods in states where actual delivery times are similar but late delivery rates differ significantly.

Better estimates can help improve operational planning and customer expectations.

## ⚠️ Project Limitations

- The relationship between delivery delays and review scores indicates correlation, not causation.
- Only delivered orders are included; cancelled and unavailable orders are excluded.
- State-level analysis covers 17 states with at least 500 orders, representing approximately 95% of all late orders.
- High-value customers are defined as the top 25% based on total spending.
- Inactive customers are defined using a below-median recency threshold of approximately 218 days.
- The dataset covers approximately 20 months, limiting the observation of long-term customer retention.
- The available data does not explain why customers do not return, as acquisition and marketing campaign data are unavailable.

## 📁 Repository Structure

```text
olist-project/
│
├── data/
│   ├── raw/                # Original Kaggle CSV files (not committed)
│   └── tableau/            # Processed Excel files for Tableau
│
├── notebooks/
│   └── 01_analysis.ipynb   # Main analysis notebook
│
├── images/
│   └── dashboard.png       # Dashboard preview
│
└── README.md
```

## 🚀 How to Reproduce

**1. Download the dataset**

Download the [Olist Brazilian E-Commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) and place the original CSV files inside `data/raw/`.

**2. Install dependencies**

```bash
pip install pandas numpy matplotlib seaborn openpyxl
```

**3. Run the analysis**

Open and execute `notebooks/01_analysis.ipynb` from top to bottom.

**4. Rebuild the dashboard**

The notebook exports processed files into `data/tableau/`. Open the exported Excel files in Tableau to recreate the dashboard.

## 👨‍💻 Author

**Muhamad Fahrudin**

Data Analyst Candidate | Bandung, Indonesia

[![GitHub](https://img.shields.io/badge/GitHub-mmufaah-black?style=flat&logo=github)](https://github.com/mmufaah)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Muhamad%20Fahrudin-blue?style=flat&logo=linkedin)](https://linkedin.com/in/mmufaah)

---

<p align="center">
  <i>Turning data into insights and insights into better business decisions.</i>
</p>
