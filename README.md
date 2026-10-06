💳 Credit Card Financial Analytics Dashboard
An end-to-end Credit Card Financial Analytics project built using PostgreSQL, SQL, and Power BI.
The project combines customer information with credit-card transaction data to analyze revenue, transaction behavior, interest earned, customer segments, expenditure patterns, card categories, and quarterly performance.
📌 Project Overview
This project analyzes credit-card customer and transaction data and presents the results through two interactive Power BI dashboards:
1. Credit Card Customer Report
2. Credit Card Transaction Report
The data is first loaded and structured in PostgreSQL using SQL, and the resulting data is analyzed and visualized in Power BI.
The project includes:
- Customer demographic analysis
- Credit-card transaction analysis
- Revenue analysis
- Interest-earning analysis
- Transaction-volume analysis
- Customer segmentation
- Expenditure analysis
- Card-category analysis
- Quarterly and weekly performance analysis
- Geographic/state-level analysis
- Education and employment analysis
🛠️ Technologies Used
Technology	Purpose
PostgreSQL	Database creation, table creation, and CSV data loading
SQL	Data preparation and database operations
Power BI	Interactive dashboard development and visualization
CSV	Source datasets
DAX / Power BI calculations	KPI and dashboard analysis


📂 Project Files
Credit-Card-Financial-Analytics/
│
├── credit_card.csv
├── customer.csv
├── cc_add.csv
├── cust_add.csv
│
├── Credit_card_sql_query.sql
├── SQL Query - Financial Dashboard Data.sql
│
├── credit_card_report.pbix
├── credit_card_report.pdf
│
└── README.md
Dataset files
- credit_card.csv — Main credit-card transaction dataset containing 10,108 records.
- customer.csv — Main customer dataset containing 10,108 records.
- cc_add.csv — Additional credit-card records containing 185 records, including Week 53 data.
- cust_add.csv — Additional customer records containing 185 records.
The transaction and customer datasets are linked through Client_Num.
🗄️ Database Design
The SQL scripts create two primary tables:
1. cc_detail
Contains credit-card and transaction-related information such as:
- Client number
- Card category
- Annual fees
- Activation status
- Customer acquisition cost
- Week and quarter
- Credit limit
- Revolving balance
- Transaction amount
- Transaction count
- Utilization ratio
- Chip/swipe usage
- Expenditure type
- Interest earned
- Delinquent account indicator
2. cust_detail
Contains customer-related information such as:
- Client number
- Customer age
- Gender
- Dependents
- Education level
- Marital status
- State
- ZIP code
- Car ownership
- House ownership
- Personal loan
- Contact type
- Customer job
- Income
- Customer satisfaction score
🔄 Data Preparation Workflow
CSV Files
   │
   ├── credit_card.csv
   ├── customer.csv
   ├── cc_add.csv
   └── cust_add.csv
          │
          ▼
     PostgreSQL
          │
          ├── cc_detail
          └── cust_detail
          │
          ▼
       Power BI
          │
          ├── Customer Report
          └── Transaction Report
The SQL scripts use PostgreSQL COPY commands to load the CSV files into the database.
The project also includes a datestyle adjustment in the SQL script for handling date values stored in DD-MM-YYYY format.
📊 Dashboard 1 — Credit Card Customer Report
The Credit Card Customer Report provides a customer-focused view of revenue and customer characteristics.
Key KPIs
The dashboard displays:
- Income: 588M
- Total Interest: 8M
- Revenue: 57M
- Customer Satisfaction Score: 3.19
Visualizations
The dashboard includes:
- Revenue by Income Group
- Revenue by Customer Job
- Revenue by Age Group
- Revenue by Education Level
- Revenue by Marital Status
- Revenue by State
- Weekly Revenue Trend
- Gender-based revenue comparison
- Card-category filters
- Quarterly filters
- Week-start-date filter
- Expenditure/channel-related filters
Customer-level analysis
The dashboard compares revenue across customer job categories such as:
- Businessman
- White-collar
- Selfemployeed
- Govt
- Blue-collar
- Retirees
It also analyzes customer education levels, age groups, income groups, and marital status.
💰 Dashboard 2 — Credit Card Transaction Report
The Credit Card Transaction Report focuses on transaction performance and spending behavior.
Key KPIs
The dashboard displays:
- Transaction Amount: 45.5M
- Total Interest: 8M
- Transaction Count: 667.2K
- Revenue: 57M
Visualizations
The dashboard includes:
- Quarterly Revenue and Transaction Count
- Revenue by Expenditure Type
- Revenue by Education Level
- Revenue by Customer Job
- Revenue by Card Category
- Transaction Amount by Card Category
- Interest Earned by Card Category
- Transaction count analysis
- Swipe, Chip, and Online transaction analysis
Expenditure categories
The report analyzes revenue across:
- Bills
- Entertainment
- Fuel
- Grocery
- Food
- Travel
Card categories
The dashboard compares:
- Blue
- Silver
- Gold
- Platinum
📈 Key Dashboard Results
According to the Power BI report:
Customer Report
Total values shown in the customer report include:
Metric	Value
Revenue	56,517,011
Income	587,599,783
Interest Earned	7,982,480
Customer Satisfaction Score	3.19


Transaction Report
Metric	Value
Revenue	56,517,011
Transaction Amount	45,533,021
Interest Earned	7,982,480
Transaction Count	667.2K


Revenue by Card Category
Card Category	Revenue
Blue	47,188,612
Silver	5,659,109
Gold	2,533,682
Platinum	1,135,608
Total	56,517,011


The Blue card category contributes the largest share of revenue in the transaction report.
📅 Quarterly Performance
The transaction dashboard compares revenue and transaction count across Q1–Q4.
Quarter	Revenue	Transaction Count
Q1	14.0M	163.3K
Q2	13.8M	164.2K
Q3	14.2M	166.6K
Q4	14.5M	173.2K


Based on the dashboard, Q4 has the highest revenue and transaction count among the four quarters.
💳 Transaction Channel Analysis
Revenue is also analyzed by transaction method:
Transaction Type	Revenue
Swipe	36M
Chip	17M
Online	4M


Swipe transactions represent the largest revenue contribution among the three transaction methods shown in the dashboard.
🧑‍💼 Revenue by Customer Job
The transaction report shows the following revenue distribution:
Customer Job	Revenue
Businessman	17.7M
White-collar	10.3M
Selfemployeed	8.5M
Govt	8.3M
Blue-collar	7.0M
Retirees	4.6M


Businessman customers contribute the highest revenue among the listed customer-job categories.
🎓 Revenue by Education Level
The dashboard compares revenue across:
- Graduate
- High School
- Unknown
- Uneducated
- Post-Graduate
- Doctorate
The Graduate segment contributes the highest revenue in the transaction report.
🛠️ SQL Implementation
The SQL scripts handle:
1. Database creation
2. Table creation
3. CSV data import
4. Additional Week-53 data import
5. Date-format configuration
6. Basic data verification
Example database creation:
CREATE DATABASE ccdb;
Example table creation:
CREATE TABLE cc_detail (
    Client_Num INT,
    Card_Category VARCHAR(20),
    Annual_Fees INT,
    Activation_30_Days INT,
    Customer_Acq_Cost INT,
    Week_Start_Date DATE,
    Week_Num VARCHAR(20),
    Qtr VARCHAR(10),
    current_year INT,
    Credit_Limit DECIMAL(10,2),
    Total_Revolving_Bal INT,
    Total_Trans_Amt INT,
    Total_Trans_Ct INT,
    Avg_Utilization_Ratio DECIMAL(10,3),
    Use_Chip VARCHAR(10),
    Exp_Type VARCHAR(50),
    Interest_Earned DECIMAL(10,3),
    Delinquent_Acc VARCHAR(5)
);
The complete SQL implementation is available in:
- [`Credit_card_sql_query.sql`](Credit_card_sql_query.sql)
- [`SQL Query - Financial Dashboard Data.sql`](SQL Query - Financial Dashboard Data.sql)
📊 Power BI Dashboard
The Power BI report contains two report pages:
Page 1 — Credit Card Customer Report
Focuses on:
- Customer demographics
- Income
- Revenue
- Interest
- Customer satisfaction
- Age
- Education
- Job
- Marital status
- State
Page 2 — Credit Card Transaction Report
Focuses on:
- Revenue
- Transaction amount
- Transaction count
- Interest earned
- Card category
- Expenditure type
- Transaction channel
- Quarterly performance
Power BI source file:
[`credit_card_report.pbix`](credit_card_report.pbix)
PDF version:
[`credit_card_report.pdf`](credit_card_report.pdf)
🚀 How to Run the Project
Step 1 — Set up PostgreSQL
Create the database:
CREATE DATABASE ccdb;
Connect to the ccdb database.
Step 2 — Create the tables
Run the table-creation section from:
SQL Query - Financial Dashboard Data.sql
Step 3 — Import the CSV files
Update the file paths in the COPY commands according to your local machine.
Example:
COPY cc_detail
FROM 'D:\credit_card.csv'
DELIMITER ','
CSV HEADER;
Then import:
customer.csv
cc_add.csv
cust_add.csv
Step 4 — Configure the date format if required
The source data uses day-month-year date formatting. If PostgreSQL reports a date-format error, the SQL script includes:
SET datestyle TO 'ISO, DMY';
Step 5 — Open the Power BI report
Open:
credit_card_report.pbix
Connect/refresh the data source if necessary.
🔍 Business Questions Answered
This project helps answer questions such as:
- Which card category generates the most revenue?
- Which customer job contributes the most revenue?
- Which quarter has the highest revenue?
- How many transactions occur each quarter?
- Which expenditure categories generate the most revenue?
- How does revenue vary by education level?
- How does revenue vary across age groups?
- Which states contribute the most revenue?
- Which transaction method generates the most revenue?
- How much interest is earned across different card categories?
- How does customer income relate to revenue contribution?
- What is the overall customer satisfaction score?
📌 Main Insights
Based on the Power BI dashboards:
- Blue cards generate the highest revenue among the card categories.
- Q4 records the highest quarterly revenue and transaction count.
- Businessman customers contribute the highest revenue among customer-job categories.
- Graduate customers contribute the highest revenue among education groups.
- Swipe is the largest transaction channel by revenue.
- Bills is the largest expenditure category by revenue in the transaction report.
- The dashboards provide both customer-level segmentation and transaction-level performance analysis.
📁 Recommended GitHub Repository Structure
Credit-Card-Financial-Analytics/
│
├── data/
│   ├── credit_card.csv
│   ├── customer.csv
│   ├── cc_add.csv
│   └── cust_add.csv
│
├── sql/
│   ├── Credit_card_sql_query.sql
│   └── SQL Query - Financial Dashboard Data.sql
│
├── powerbi/
│   └── credit_card_report.pbix
│
├── report/
│   └── credit_card_report.pdf
│
└── README.md
Note: The structure above is a recommended organization. The current uploaded files can remain in the repository root if preferred.

🎯 Skills Demonstrated
This project demonstrates practical experience in:
- SQL
- PostgreSQL
- Data loading and database management
- Data modeling
- Power BI
- Dashboard development
- KPI design
- Data visualization
- Customer segmentation
- Financial analytics
- Transaction analysis
- Business intelligence
- Data-driven business insights
📄 Project Deliverables
Deliverable	File
Customer dataset	customer.csv
Transaction dataset	credit_card.csv
Additional customer data	cust_add.csv
Additional transaction data	cc_add.csv
SQL scripts	*.sql
Power BI dashboard	credit_card_report.pbix
Dashboard PDF	credit_card_report.pdf


👤 Author
Ravi Nandan
Data Analyst | SQL | Power BI | Python | Data Analytics
⭐ If you find this project useful
Feel free to explore the SQL scripts and Power BI dashboard to understand the complete workflow from raw CSV data → PostgreSQL → SQL → Power BI → business insights.
