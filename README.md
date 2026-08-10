# E-Commerce-Sales-Inventory-Customer-Analytics
Developed an end-to-end data analytics solution using SQL, Python, Excel, and Power BI to analyze 100K+ products, 200K orders, customers, vendors, sales, ratings, and inventory. Built interactive dashboards with DAX KPIs, slicers, trend analysis, product performance, vendor insights, and stock alerts to support data-driven business decisions.


🛒 Marketplace Analytics Project — Complete Details
1. 🎯 Project Objective

The objective was to analyze an e-commerce/marketplace business and build a complete analytics solution covering:

Customer activity
Orders and sales
Products
Vendors
Reviews and ratings
Inventory
Revenue
Product performance
Low-stock monitoring
Business KPIs

The project followed a complete data-analysis pipeline:

Raw Data
   ↓
Excel
   ↓
Python / Pandas
   ↓
MySQL / SQL
   ↓
Power BI
   ↓
Interactive Dashboard
   ↓
Business Insights
2. 📂 Dataset We Used

We worked with 6 main CSV files/tables.

1. Users
user_id
name
email
phone
city
state
country
registration_date
is_active

Used for:

Customer analysis
Customer count
Geography
Registration analysis
Active/inactive customers
2. Vendors
vendor_id
vendor_name
contact_email
city
gst_number
commission_rate
verified
created_date

Used for:

Vendor performance
Vendor revenue
Vendor ranking
Vendor verification
3. Products
product_id
vendor_id
product_name
category
subcategory
price
cost_price
stock
created_date
is_active

Used for:

Product analysis
Category analysis
Pricing
Inventory
Low-stock analysis
Product performance
4. Orders
order_id
user_id
order_date
total_amount
discount_amount
final_amount
status
delivery_address
payment_method
created_at

Used for:

Order analysis
Revenue
Customer orders
Payment methods
Order status
Monthly sales
5. Order Items
order_item_id
order_id
product_id
vendor_id
quantity
unit_price
discount_percent
total_price

Used for:

Quantity sold
Product sales
Revenue calculations
Product-level analysis
Vendor-level sales
6. Reviews
review_id
product_id
user_id
order_id
rating
review_title
review_text
verified_purchase
helpful_count
created_date

Used for:

Average rating
Product ratings
Customer feedback
Review analysis
3. 📗 Excel — What We Used

Excel was part of the data preparation and analysis workflow.

We worked with concepts such as:

Basic functions
SUM
AVERAGE
COUNT
COUNTA
COUNTIF
COUNTIFS
SUMIF
SUMIFS
IF
Lookup functions
VLOOKUP
INDEX-MATCH

You also practiced lookup-based analysis using student and sales datasets before applying the concepts to the marketplace project.

Excel analysis

We used Excel concepts for:

Data validation
Checking missing/inconsistent values
Basic calculations
Filtering
Sorting
Pivot Tables
Lookup operations
KPI calculations
Why Excel?

Excel was useful for quick validation and initial exploration before moving toward Python, SQL and Power BI.

4. 🐍 Python — What We Used

The main Python library was:

Pandas

Used for:

Reading CSV files
Data cleaning
Data transformation
Checking columns
Handling datasets
Preparing data for SQL

Example workflow:

import pandas as pd

users = pd.read_csv("users.csv")
orders = pd.read_csv("orders.csv")
products = pd.read_csv("products.csv")

We also worked with:

NumPy

For numerical/data operations.

OS / file handling

Used for handling file paths and importing multiple files.

MySQL Connector

Used to connect Python with MySQL and load/process marketplace data.

5. 🐍 Python Problems We Faced

This is actually important for your interview because it shows that you didn't just use Python—you troubleshot real data problems.

Problem 1 — Incorrect file path

We encountered errors such as:

NotADirectoryError

and:

TypeError: unsupported operand type(s) for /: 'str' and 'str'
What caused it?

The CSV path was being handled incorrectly.

Solution

We changed the file-path handling and used proper path construction, including os.path.join().

We also added checks to identify:

File location
File name
Whether the path actually existed
Which file was being read
6. 🐍 Python → MySQL Problem

One major issue was:

Unknown column 'name' in 'field list'
Why?

The CSV contained:

name

but the database schema had a different structure, such as:

first_name
last_name

So Python was trying to insert a column that didn't exist in the MySQL table.

Lesson

The source CSV schema and database schema must match before loading data.

We identified the mismatch and worked through the table/schema alignment.

This is a very good interview point:

"During the ETL process, I encountered a schema mismatch between the CSV and MySQL table. I compared the source and target schemas and corrected the mapping before loading the data."

7. 🗄️ SQL — What We Used

SQL was the core database analysis layer.

We worked with concepts including:

Basic SQL
SELECT
FROM
WHERE
ORDER BY
GROUP BY
Aggregations
SUM()
COUNT()
AVG()
MIN()
MAX()
Conditional logic
CASE
Filtering
WHERE
HAVING
Joins

Especially important because the marketplace had multiple related tables:

users
orders
order_items
products
vendors
reviews

We worked with relationships using:

INNER JOIN
LEFT JOIN
8. 🔗 Database Relationships

The logical structure was approximately:

Users
  │
  │ user_id
  ↓
Orders
  │
  │ order_id
  ↓
Order_Items
  │
  │ product_id
  ↓
Products
  │
  │ vendor_id
  ↓
Vendors

And:

Products
   │
   ↓
Reviews

This allowed us to connect:

Customer → Order → Product → Vendor → Review

9. 🧮 SQL Business Analysis

The database was designed so we could answer questions such as:

Revenue
What is total revenue?
What is revenue by month?
What is revenue by product?
What is revenue by category?
What is revenue by vendor?
Customers
How many customers are there?
Which customers placed orders?
Which cities have customers?
Products
Which products sell the most?
Which categories perform best?
Which products have low inventory?
Vendors
Which vendors generate the most revenue?
What are the top vendors?
Orders
How many orders were placed?
What are the order statuses?
Which payment methods are used?
Reviews
What is the average rating?
Which products have higher/lower ratings?
10. 📊 Power BI — Main Dashboard

Power BI became the final visualization and reporting layer.

We created 3 pages.

PAGE 1 — Executive Summary
Title

MARKETPLACE ANALYTICS DASHBOARD

Subtitle:

Executive Summary – Real-time Marketplace Performance

KPI Cards

You created:

💰 Total Revenue
🛒 Total Orders
👥 Total Customers
⭐ Average Rating
Visuals
Top 10 Vendors by Revenue

Bar chart showing the highest-performing vendors.

Monthly Revenue Trend

Line chart showing revenue over time.

Slicers

You added filters for:

Date
Status
City
Payment Method

This page is the management/executive overview.

PAGE 2 — Sales & Product Performance
Title

Sales & Product Performance

Subtitle:

Revenue | Qty Sold | Products | Average Order Value

Visual 1

Revenue by Category

Shows category-level revenue.

Visual 2

Revenue by Product Name

Shows product-level revenue.

Visual 3

Revenue by Subcategory

Shows subcategory performance.

Visual 4

Top Selling Products

Based on quantity sold.

Visual 5

Monthly Sales Trend

Shows sales/revenue movement over time.

Visual 6

Price vs Revenue

Scatter chart showing the relationship between product price and revenue.

Page 2 KPI Cards

We created:

Total Revenue
3.64bn
Quantity Sold
900K
Total Products
100K
Average Order Value
21.46K

These make the page much easier to understand at a glance.

PAGE 3 — Product Performance & Inventory
Title

PRODUCT PERFORMANCE & INVENTORY

Subtitle:

Top Products, Ratings & Stock Alerts

This page focuses on the product and inventory side of the marketplace.

KPI Cards

We added:

⭐ Average Product Rating
3.00
📦 Total Products
100K
⚠️ Low Stock Products
391
💰 Average Product Price
50.14K
Page 3 Visuals
Product analysis

A product-level chart showing product counts/performance.

Category analysis

Category-level analysis.

Inventory Status

We created:

Available
Low Stock

and displayed the distribution using a donut chart.

Total Inventory Value

We also created an inventory-value calculation.

Conceptually:

Total Inventory Value =
SUMX(
    products,
    products[stock] * products[cost_price]
)

The dashboard showed approximately:

6.86T

for the dataset.

11. 🧮 DAX — What We Used

DAX was used to create Power BI measures.

Total Products
Total Products =
DISTINCTCOUNT(products[product_id])

Result:

100K
Low Stock Products

We created a low-stock measure based on the stock threshold.

Stock < 20

Result:

391
Average Product Price

Used the average of:

products[price]
Average Order Value

Based on order values.

Total Inventory Value
Total Inventory Value =
SUMX(
    products,
    products[stock] * products[cost_price]
)
12. ⚠️ DAX Problem We Faced

One of the most important problems was the Inventory Status calculation.

Initially, we tried:

Inventory Status =
IF(
    products[stock] < 20,
    "Low Stock",
    "Available"
)

Power BI gave the error:

A single value for column 'stock' in table 'products' cannot be determined.

Why?

Because we created it as a measure.

A measure operates in filter context and cannot simply evaluate every individual row of products[stock] without an appropriate row context/aggregation.

Correct approach

For a row-by-row classification like:

Stock < 20 → Low Stock
Stock >= 20 → Available

we should use a calculated column, not a measure.

This was a valuable Power BI/DAX learning point.

13. 🔄 Power BI Problem — Visual Not Showing Numbers

We also faced situations where:

The value field was filled
The measure existed
The visual was blank
Refreshing didn't immediately solve it

We checked:

Measure definition
Visual type
Value field
Target field
Data model
Relationships
Refresh

Eventually the Total Products card displayed:

100K

This taught you an important Power BI troubleshooting workflow instead of simply recreating the visual.

14. 🎨 Dashboard Design

We also spent significant time on layout and visual placement.

For example, Page 2 initially had only one visual and then we arranged six visuals on one page.

The final structure became roughly:

┌───────────────────────────────────────────┐
│       SALES & PRODUCT PERFORMANCE         │
│ Revenue | Qty Sold | Products | AOV       │
├───────────────────┬───────────────────────┤
│ Revenue Category  │ Top Selling Products  │
├───────────────────┼───────────────────────┤
│ Revenue Product   │ Monthly Sales Trend   │
├───────────────────┼───────────────────────┤
│ Revenue Subcat.   │ Price vs Revenue      │
├───────────────────────────────────────────┤
│ KPI  │ KPI  │ KPI  │ KPI                  │
└───────────────────────────────────────────┘

We adjusted:

Visual sizes
Titles
KPI cards
Spacing
Alignment
Page layout
Slicer positioning
15. 🎛️ Slicers

We used slicers to make the dashboard interactive.

Page 1
Date
Status
City
Payment Method
Product/Inventory analysis

Potential filters included:

Category
Subcategory
Vendor
Inventory Status
Date
Price

This means the dashboard isn't just static reporting—it allows users to interactively explore the data.

16. 🧠 What We Actually Learned

This project covered almost the complete Data Analyst workflow:

                    DATA ANALYST WORKFLOW

                         Raw Data
                            ↓
                       Data Checking
                            ↓
                         Excel
                            ↓
                    Python / Pandas
                            ↓
                      Data Cleaning
                            ↓
                         MySQL
                            ↓
                           SQL
                            ↓
                    Business Analysis
                            ↓
                        Power BI
                            ↓
                          DAX
                            ↓
                       Visualization
                            ↓
                     Interactive KPI
                            ↓
                   Business Insights
17. 🛠️ Technologies Used

Your project stack can be presented as:

Technology	Purpose
Excel	Data validation, formulas, Pivot Tables, initial analysis
Python	Data processing and transformation
Pandas	CSV handling and data manipulation
NumPy	Numerical operations
MySQL	Database storage
SQL	Data querying and business analysis
Power BI	Dashboard and visualization
DAX	Measures and calculated analytics
CSV	Source data
Power BI Data Model	Relationships between tables
18. 🔥 Problems We Faced — Interview Version

If an interviewer asks "What challenges did you face?", don't just say "there were errors."

Tell them these:

1. Schema mismatch

CSV column:

name

Database expected a different structure.

Solution: Compared source and target schemas and corrected the mapping.

2. File-path problems in Python

Errors:

NotADirectoryError
TypeError

Solution: Corrected file-path handling and used proper path construction.

3. DAX context problem

Error:

A single value for column 'stock' cannot be determined

Solution: Understood the difference between a measure and calculated column and used row-level logic appropriately.

4. Blank Power BI visuals

Solution: Checked:

Measure
↓
Visual
↓
Value field
↓
Data type
↓
Relationship
↓
Refresh
5. Dashboard space/layout

We needed to fit multiple visuals into one page without making it overcrowded.

Solution: Used a structured grid layout with:

KPI row
2-column visual layout
Bottom filters
6. Large numbers

The dataset produced very large values such as:

100K
3.64bn
6.86T

We had to format the dashboard so these were readable rather than displaying long raw numbers.

19. 💼 What You Can Say You Did

A strong interview explanation would be:

"I developed a Marketplace Analytics solution using Excel, Python, MySQL, SQL and Power BI. I worked with six interconnected datasets covering users, orders, order items, products, vendors and reviews. I used Python and Pandas for data processing and validation, loaded the data into MySQL, and used SQL joins, aggregations and business queries to analyze revenue, orders, customers, products and vendors. I then connected the data to Power BI, created DAX measures and built a three-page interactive dashboard covering executive performance, sales and product performance, and inventory analysis. During the project, I also handled practical issues such as CSV-to-database schema mismatches, Python file-path errors, DAX filter/row-context problems and Power BI visual configuration issues."

That is a real project story, not just a list of tools. 🎯

20. ⭐ Your Final Project Structure

Your project can now be presented as:

MARKETPLACE ANALYTICS
│
├── 📁 Raw Data
│   ├── users.csv
│   ├── vendors.csv
│   ├── products.csv
│   ├── orders.csv
│   ├── order_items.csv
│   └── reviews.csv
│
├── 📗 Excel
│   ├── Data validation
│   ├── Formulas
│   ├── Lookups
│   └── Pivot analysis
│
├── 🐍 Python
│   ├── Pandas
│   ├── NumPy
│   ├── Cleaning
│   ├── Transformation
│   └── MySQL loading
│
├── 🗄️ MySQL / SQL
│   ├── 6 tables
│   ├── Relationships
│   ├── JOINs
│   ├── Aggregations
│   ├── CASE
│   └── Business queries
│
└── 📊 Power BI
    ├── Page 1: Executive Summary
    ├── Page 2: Sales & Product Performance
    ├── Page 3: Product Performance & Inventory
    ├── DAX Measures
    ├── KPIs
    ├── Charts
    └── Slicers
