# A-360-Financial-Services-Performance-Dashboard
An end-to-end Power BI dashboard that gives banking leadership a single, interactive view of financial health — spanning executive KPIs, customer and account behaviour, loan portfolio risk, and transaction and branch performance.

# 📑 Table of Contents
1. Overview
2. Business Problem
3. Dataset
4. Dashboard Preview
5. Dashboard Pages
6. Key Insights
7. Measures Used
8. Tools & Skills
9. Repository Structure

# 📌 Overview

BankPulse consolidates data on 720 customers, ~2,000 accounts, 330 loans, and 50,000 transactions across ~50 branches into one drill-down-friendly Power BI report. It's built to answer four questions a bank's leadership and operations teams ask every week: How healthy is the balance sheet overall? Who are our customers and how do their accounts behave? How is the loan book performing, and where is the risk? Where and how is transaction activity happening across the branch network?

# 💼 Business Problem

Banking data is typically scattered across separate systems for accounts, loans, and transactions, making it hard to get a single, trustworthy view of performance. BankPulse brings these three areas together into one connected model with consistent filters (Year, Account Type, Account Status), so stakeholders can move from a high-level executive summary down to branch- and loan-level detail without switching reports.

# 🗂️ Dataset

The report is built on four related tables: Customers, Accounts, Loans, and Transactions, linked by customer and account IDs. Fields include account type and status, loan principal, interest rate and status, transaction type and amount, branch, and country, spanning 2018–2025.

# Dashboard Preview 
1. Executive Overview 
<img width="1139" height="636" alt="image" src="https://github.com/user-attachments/assets/045455b6-6284-4436-915e-3d83112090e7" />

2. Customer & Account Analysis
<img width="1145" height="640" alt="image" src="https://github.com/user-attachments/assets/2b8bdb96-f563-4044-a89f-bb44133f8d60" />

3. Loan Analysis 
<img width="1139" height="639" alt="image" src="https://github.com/user-attachments/assets/60973bbd-0f58-4742-b9fe-f0f4d3892c20" />

4. Transaction & Branches 
<img width="1139" height="635" alt="image" src="https://github.com/user-attachments/assets/411df748-ee37-435b-801e-ffe238fb1a54" />

# 📊 Dashboard Pages

1. Executive Overview — Total Balance, Total Customers, Total Accounts, Total Loan Principal, and Total Transaction Volume, alongside loan portfolio status, account portfolio status, and transaction mix by type.

2. Customer & Account Analysis — Highest, lowest, and average account balance; customer segmentation by individual vs. business; account and loan counts by customer type; total balance by account type; and an account balance trend over time.

3. Loan Analysis — Average interest rate, overdue loan principal, loan status distribution, loan principal trend over time, and a loan performance table by status (count and average interest rate).

4. Transactions & Branches — Total transaction value and count, transaction volume by branch, a geographic distribution map, average transaction amount by type, and a monthly transaction volume trend.

Each page shares a consistent slicer panel (Year, Account Type, Account Status where applicable) so filtering carries across the analysis.

# 🔍 Key Insights
Active loans make up 72.4% of the loan book; overdue loans sit at a notable 10.3% share (1.67M in overdue principal)
Business customers make up 68% of the customer base, and account counts outnumber loan counts across every account type — signalling room to grow lending relationships
Overdue loans carry the lowest average interest rate (8.11%) of any loan status, which is worth a closer look
Transaction volume is evenly spread across ~50 branches, concentrated in North America and Europe
At least one account carries a negative balance (-486.68), flagging a potential overdraft/risk case
# 🧮 Measures Used

1. Total Balance = SUM(Accounts[Balance])
2. Total Customers = DISTINCTCOUNT(Customers[CustomerID])
3. Total Accounts = DISTINCTCOUNT(Accounts[AccountID])
4. Total Loan Principal = SUM(Loans[LoanPrincipal])
5. Total Transaction Volume = SUM(Transactions[Amount])
6. Average Interest Rate = AVERAGE(Loans[InterestRate])
7. Overdue Loan Principal = CALCULATE(SUM(Loans[LoanPrincipal]), Loans[Status] = "Overdue")
8. Total Transaction Value = SUM(Transactions[Amount])
9. Average Transaction Amount = AVERAGE(Transactions[Amount])
10. Total Transactions = COUNTROWS(Transactions)

# 🛠️ Tools & Skills
1. Power BI — data modeling, relationships across 4 tables, DAX measures, interactive visuals
2. DAX — aggregations, CALCULATE with filter context, ratio/percentage measures
3. Data Visualization — KPI cards, donut charts, clustered bar charts, line/trend charts, filled maps, matrix tables
4. Dashboard Design — multi-page navigation, consistent slicer panels, executive-to-detail drill path
