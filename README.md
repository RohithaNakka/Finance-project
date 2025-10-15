# Finance-project
.

**📘**Project Overview****

This project demonstrates end-to-end data analytics and business intelligence skills by analyzing a banking dataset to uncover insights about loan performance, deposits, and customer engagement.

The dataset was imported into SQL Server, cleaned and explored using Python (Pandas, NumPy, Matplotlib, Seaborn) in VS Code, and visualized through an interactive Power BI dashboard.

**🎯 **Problem Statement****

To develop a data-driven understanding of risk analytics in the banking and financial services sector — helping banks minimize lending risks, understand customer engagement, and make informed decisions on loans and deposits.

**💡 **Objective****

Build an interactive Banking Dashboard showing key metrics such as:

Loan Analysis

Deposit Analysis

Client Engagement Summary

These insights support data-backed decisions on customer lending, deposit strategies, and client retention.

**🧩 About the Dataset**

The dataset contains detailed client and banking information across multiple related tables:

Client-Banking

Banking Relationship

Gender

Investment Advisor

Period

Columns include:
Client ID, Name, Age, Location ID, Joined Bank, Nationality, Occupation, Fee Structure, Estimated Income, Superannuation Savings, Credit Card Balance, Bank Loans, Bank Deposits, Checking Accounts, Saving Accounts, Foreign Currency Account, Business Lending, Risk Weighting, etc.

**🧹 Data Cleaning & Preparation**

Performed in Python (Pandas) and SQL Server:

Created new column Engagement Timeframe to calculate the client’s banking duration.

Added Engagement Days = DATEDIFF(Joined Bank, TODAY(), DAY).

Binned Estimated Income into Low (<100K) and Mid (<300K) as Income Band.

Created Processing Fees column based on Fee Structure (e.g., High = 0.05).

Removed duplicates, handled missing values, and standardized column names.

**🧮 Calculated Metrics (Power BI DAX Functions)**

Key DAX functions used for KPI calculations:

Function	Purpose	Example
SUM	Adds up all numerical values	Bank Deposit = SUM('Clients - Banking'[Bank Deposits])
DISTINCTCOUNT	Counts unique values	Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])
SUMX	Row-wise sum for an expression	Total Fees = SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])
DATEDIFF	Calculates date difference	Engagement Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)
SWITCH	Returns results based on conditions	Used for custom income bands
**📊 Key Performance Indicators (KPIs)**
KPI	Description	Formula
Total Clients	Number of unique clients	DISTINCTCOUNT('Clients - Banking'[Client ID])
Total Loan	Total loan exposure	[Bank Loan] + [Business Lending] + [Credit Card Balance]
Bank Loan	Total loans issued	SUM('Clients - Banking'[Bank Loans])
Business Lending	Loans to small businesses	SUM('Clients - Banking'[Business Lending])
Total Deposit	Combined customer deposits	[Bank Deposits] + [Saving Accounts] + [Foreign Currency Account] + [Checking Accounts]
Total Fees	Processing and maintenance charges	SUMX('Clients - Banking', [Total Loan] * [Processing Fees])
Credit Card Balance	Total outstanding credit	SUM('Clients - Banking'[Credit Card Balance])
**📈 Power BI Dashboard
**
The dashboard provides an intuitive interface with three main views:

**🏠 Home Dashboard**

Overview of all KPIs and metrics

Total engagement, client counts, and account summaries

**💰 Loan Analysis**

Distribution of loans by income band, occupation, and geography

**Insights:**

Bank loans are highest for mid-income clients

European countries have the most loans

Australian countries show the lowest loan amounts

**💵 Deposit Analysis**

Total deposits by nationality and income level

Insights:

European clients lead in total deposits

African regions have the lowest average deposits

**📊 Summary View**

Comparative analysis of loan and deposit trends

Visual representation of engagement and loyalty classification

**📚 Tools & Technologies Used**

SQL Server: Data import, schema creation, and basic joins

Python (VS Code): Data cleaning, feature engineering, and EDA

Libraries: Pandas, NumPy, Matplotlib, Seaborn

Power BI: Data visualization and KPI dashboard creation

DAX: Custom measures and calculated columns

**🔍 Key Insights**

Mid-income clients take the highest number of loans, while high-income clients borrow less.

European clients dominate in both loan and deposit metrics.

Private banks hold more clients than public ones, suggesting better engagement.

The average engagement period directly correlates with loyalty classification.

**🚀 Conclusion**

Power BI dashboards empower the banking sector with real-time data visibility and actionable insights.
This project demonstrates how data analytics and visualization can:

Improve lending decisions

Identify high-value clients

Optimize deposit and fee strategies
