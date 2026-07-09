🛍️ Customer Shopping Behavior Analysis
An end-to-end data analytics project exploring customer shopping behavior using transactional retail data. The project covers data cleaning and exploratory analysis in Python, business-question analysis in SQL (PostgreSQL), and an interactive Power BI dashboard for stakeholder reporting.
    
________________________________________
📋 Table of Contents
•	Project Overview
•	Dataset
•	Tech Stack
•	Project Workflow
•	Key Business Questions
•	Key Insights
•	Dashboard
•	Business Recommendations
•	Repository Structure
•	Getting Started
•	Author
________________________________________
📖 Project Overview
This project analyzes 3,900 retail transactions to uncover patterns in customer spending, product performance, and subscription behavior. The goal is to translate raw transactional data into clear, actionable insights that can guide marketing, retention, and pricing strategy.
The workflow follows a typical analytics pipeline:
1.	Clean and prepare the raw data in Python.
2.	Query and analyze the data in PostgreSQL to answer specific business questions.
3.	Visualize the results in an interactive Power BI dashboard.
________________________________________
🗂️ Dataset
Attribute	Details
Rows	3,900
Columns	18
Customer demographics	Age, Gender, Location, Subscription Status
Purchase details	Item Purchased, Category, Purchase Amount, Season, Size, Color
Shopping behavior	Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type
Missing data	37 missing values in Review Rating
Note: Update this section with a link to the dataset source (e.g., Kaggle) if it is publicly available, and add licensing details if required.
________________________________________
🛠️ Tech Stack
Layer	Tools
Data cleaning & EDA	Python, pandas
Database & querying	PostgreSQL, SQL
Visualization	Power BI
Version control	Git, GitHub
________________________________________
🔄 Project Workflow
1. Data Preparation & Cleaning (Python)
•	Data loading — imported the dataset using pandas.
•	Initial exploration — used df.info() and df.describe() to review structure and summary statistics.
•	Missing data handling — imputed missing Review Rating values using the median rating within each product category.
•	Column standardization — renamed columns to snake_case for consistency and readability.
•	Feature engineering: 
o	Created an age_group column by binning customer ages.
o	Created a purchase_frequency_days column from purchase-cycle data.
•	Data consistency check — identified that discount_applied and promo_code_used were redundant; dropped promo_code_used.
•	Database integration — loaded the cleaned DataFrame into PostgreSQL for SQL-based analysis.
2. Business Analysis (SQL / PostgreSQL)
Structured SQL queries were used to answer ten key business questions (see below).
3. Dashboard (Power BI)
An interactive dashboard was built to present the findings visually, with filters for subscription status, gender, category, and shipping type.
________________________________________
❓ Key Business Questions
#	Question	Query Focus
1	Revenue by Gender	Total revenue: male vs. female customers
2	High-Spending Discount Users	Customers who used a discount but still spent above average
3	Top 5 Products by Rating	Highest average review ratings
4	Shipping Type Comparison	Avg. purchase amount: Standard vs. Express
5	Subscribers vs. Non-Subscribers	Avg. spend and total revenue by subscription status
6	Discount-Dependent Products	Products with the highest discounted-purchase share
7	Customer Segmentation	New, Returning, and Loyal customer segments
8	Top 3 Products per Category	Best-selling products within each category
9	Repeat Buyers & Subscriptions	Do frequent buyers subscribe more often?
10	Revenue by Age Group	Revenue contribution by age group
________________________________________
💡 Key Insights
•	Male customers generated significantly more revenue than female customers ($157,890 vs. $75,191).
•	839 customers used a discount while still spending above the average purchase amount — a valuable segment for upselling.
•	Gloves, Sandals, and Boots received the highest average review ratings (3.8+).
•	Express shipping customers spend slightly more on average ($60.48) than Standard shipping customers ($58.46).
•	Non-subscribers drive the majority of revenue ($170,436 vs. $62,645 for subscribers), despite similar average spend per customer — indicating a large untapped opportunity to convert non-subscribers.
•	Hats, Sneakers, and Coats are the most discount-dependent products, with discount rates near 50%.
•	The majority of customers (3,116) fall into the "Loyal" segment, with only 83 classified as "New."
•	Repeat buyers (>5 purchases) are not predominantly subscribers (2,518 non-subscribers vs. 958 subscribers), suggesting purchase frequency alone doesn't predict subscription uptake.
•	Young Adults contribute the highest revenue ($62,143) among all age groups, followed closely by Middle-aged customers.
________________________________________
📊 Dashboard
An interactive Power BI dashboard summarizes the analysis with the following KPIs and visuals:
Metric	Value
Number of Customers	3,900
Average Purchase Amount	$59.76
Average Review Rating	3.75
Subscriber Share	27%
Visuals included:
•	Customer count, average purchase amount, and average review rating (KPI cards)
•	Subscription status breakdown (donut chart)
•	Revenue and sales by category (bar charts)
•	Revenue and sales by age group (bar charts)
•	Filters: Subscription Status, Gender, Category, Shipping Type
Add a screenshot of the dashboard here, e.g.: ![Dashboard Preview](assets/dashboard_preview.png)
________________________________________
✅ Business Recommendations
•	Boost subscriptions — promote exclusive benefits to convert non-subscribers, who represent 73% of the customer base yet drive the majority of revenue.
•	Strengthen loyalty programs — reward repeat buyers to move them into the "Loyal" segment and improve retention.
•	Review discount policy — balance short-term sales lift against long-term margin impact, particularly for heavily discounted products like Hats and Sneakers.
•	Optimize product positioning — feature top-rated, best-selling products (e.g., Gloves, Jewelry, Blouse) more prominently in marketing campaigns.
•	Sharpen targeted marketing — prioritize high-revenue age groups (Young Adult, Middle-aged) and Express-shipping users.
________________________________________
🚀 Getting Started
Prerequisites
•	Python 3.9+
•	PostgreSQL 13+
•	Power BI Desktop (to open the .pbix dashboard)
Setup
# Clone the repository
git clone https://github.com/<your-username>/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis

# Install Python dependencies
pip install -r requirements.txt

# Run the data cleaning / EDA notebook
jupyter notebook notebooks/data_cleaning_eda.ipynb
Loading data into PostgreSQL
psql -U <username> -d <database_name> -f sql/create_tables.sql
Then run the queries in sql/business_questions.sql to reproduce the analysis.
________________________________________
👤 Author
Satyajeet Gawali 📧 satyajeetgawali04@gmail.com 
________________________________________


