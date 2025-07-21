# 💳 Credit Card Financial Analysis Dashboard

A dynamic and insightful Power BI dashboard built using **Excel + SQL**, focused on analyzing credit card customer behavior, transaction trends, and revenue performance across various customer segments.

---

## 📌 Project Objective

> Build an interactive weekly dashboard that enables stakeholders to:
- Monitor revenue growth and KPIs
- Understand customer demographics and card performance
- Compare week-state-wise contributions
- Track weekly and quarterly changes in revenue and transaction volume

---

## 🧰 Tools & Technologies

| Tool         | Purpose                      |
|--------------|-------------------------------|
| **Power BI** | Dashboard development         |
| **Excel**    | Initial data source formatting|
| **SQL**      | Data cleaning and management  |
| **DAX**      | Calculated columns & measures |

---

## 📁 Dataset Overview

- **Customer Data**: Age, Gender, Income, Education, Marital Status, Job, Dependents  
- **Transaction Data**: Card Category, Interest, Fees, Total Transaction Amount, Week  
- **Weekly Revenue Data**: Calculated Revenue, WoW changes, Activation & Delinquency rates

---

## 🛠️ Data Preparation Steps

1. Cleaned raw `.csv` files and imported into SQL tables
2. Connected Power BI to SQL database
3. Created DAX measures for:
   - `Revenue = annual_fees + total_trans_amt + interest_earned`
   - Week-on-week change in revenue
   - Grouping by age and income
4. Applied filters and slicers (Quarter, Gender, State, Card Type, etc.)

---

## 📊 Key Dashboard Insights

- **Total Revenue**: ₹57M  
- **Transaction Volume**: ₹46M  
- **Total Interest Earned**: ₹8M  
- **Top Contributors**:
  - **Age Group**: 30–40 years
  - **Income Group**: Medium
  - **Card Category**: Blue (dominates with 83%+ share)
  - **Top States**: TX, NY, CA (68% combined revenue)
- **Gender Revenue Split**:  
  - Male: ₹31M  
  - Female: ₹26M  
- **Delinquency Rate**: 6.06%  
- **Activation Rate**: 57.5%

---

## 📈 Visuals Included

- Revenue by Age Group, Income Group, Education & Marital Status  
- Transaction Type (Swipe, Chip, Online)  
- Card Category Comparison (Blue, Silver, Gold, Platinum)  
- Weekly & Quarterly Revenue Trends  
- Revenue by State & Gender

---

## 🧾 Sample DAX Calculations

```DAX
AgeGroup = SWITCH(
    TRUE(),
    'cust_detail'[customer_age] < 30, "20-30",
    'cust_detail'[customer_age] >= 30 && 'cust_detail'[customer_age] < 40, "30-40",
    'cust_detail'[customer_age] >= 40 && 'cust_detail'[customer_age] < 50, "40-50",
    'cust_detail'[customer_age] >= 50 && 'cust_detail'[customer_age] < 60, "50-60",
    'cust_detail'[customer_age] >= 60, "60+",
    "Unknown"
)

Revenue = 'cc_detail'[annual_fees] + 'cc_detail'[total_trans_amt] + 'cc_detail'[interest_earned]

📁 CreditCardDashboard/
├── Credit_Card_Dashboard.pbix
├── credit_card_customers.csv
├── credit_card_transactions.csv
├── SQL_Table_Scripts.sql
├── DAX_Formulas.txt
└── README.md

👩‍💻 Author
Snehal Nalawade
📧 snehalrnalawade2003@gmail.com
🔗 https://www.linkedin.com/in/snehal-nalawade-834010262 
🌐 https://Snehal027.github.io/Myportfolio/


