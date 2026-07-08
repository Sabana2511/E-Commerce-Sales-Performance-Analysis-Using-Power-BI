# 📊 E-Commerce Sales Performance Analysis Using Power BI

## 📖 Project Description

The **E-Commerce Sales Performance Analysis** project is designed to transform raw sales data into meaningful business 
insights using **Microsoft Power BI**. Organizations generate a massive amount of sales data every day, but without proper 
analysis, it becomes difficult to understand business performance, monitor sales trends, compare targets with actual sales, 
and identify profitable products.

This project demonstrates how **Business Intelligence (BI)** can help organizations make informed decisions by converting 
raw data into interactive dashboards and visual reports. Through effective **data modeling**, **DAX calculations**, and 
**visual analytics**, the dashboard provides a comprehensive view of sales performance across different categories, products, 
locations, and time periods.

The project follows the complete Power BI development lifecycle, including data preparation, relationship creation, 
calculated columns, measures, dashboard design, and business interpretation.

---

# 🎯 Project Objectives

The primary objectives of this project are:

* Analyze overall sales performance using interactive dashboards.
* Compare actual sales with predefined sales targets.
* Identify the most profitable product categories and sub-categories.
* Track monthly and yearly sales trends.
* Evaluate product profitability using DAX calculations.
* Analyze regional sales performance across different cities and states.
* Create meaningful KPIs to monitor business growth.
* Provide actionable insights that support data-driven business decisions.

---

# ❗ Problem Statement

Businesses collect thousands of sales transactions every month. Without proper reporting and visualization, 
decision-makers struggle to answer important business questions such as:

* Which product categories generate the highest revenue?
* Which products are the most profitable?
* Are sales targets being achieved?
* Which states contribute the highest sales?
* How are sales changing over time?
* Which products are generating losses?

This project addresses these challenges by building a fully interactive Power BI dashboard that enables users to 
explore business performance from multiple perspectives.

---

# 📂 Dataset Information

The project uses three interconnected datasets.

## 1. List of Orders

This dataset contains customer and order-level information.

### Columns

* Order ID
* Order Date
* Customer Name
* City
* State
* Category
* Sales Amount
* Profit

---

## 2. Order Details

This dataset stores product-level transaction details.

### Columns

* Order ID
* Category
* Sub-Category
* Quantity
* Sales Amount
* Profit

---

## 3. Sales Target

This dataset contains monthly sales targets assigned to each product category.

### Columns

* Category
* Month of Order Date
* Target

---

# 🔄 Data Modeling

A proper data model was created to ensure accurate calculations and efficient reporting.

<img width="1428" height="652" alt="image" src="https://github.com/user-attachments/assets/ac733504-2b17-479c-8beb-7fa8fdf37b6d" />



The following steps were performed:

* Imported multiple datasets into Power BI.
* Established relationships using **Order ID**.
* Created a **Bridge Table** for Category to remove many-to-many relationships.
* Connected the Sales Target table with the sales data.
* Optimized relationships for faster dashboard performance.

---

# 🧮 DAX Calculations

## Calculated Columns

### **Category Type**

Combined Category and Sub-Category into a single column.

**Category Type = Order_DB[Category]&" "&Order_DB[Sub-Category]**



### **Revenue per Order**

Calculated revenue using: Revenue = Amount × Quantity

**Total Revenue = Order_DB[Quantity]*Order_DB[Amount]******



### **Sales Category**

Categorized orders into:
•	Above Average
•	Below Average
based on the average sales amount.

**Sales Category = 
IF(
    Order_DB[Total Revenue] >='Measure Table'[Average Revenue],
    "Above Average",
    "Below Average"
)**

---

**DAX Measures**
The following measures were created:

### **Order Count**

Total Orders = COUNT(Order_DB[Order ID])**



### **Total Sales**

Total sales = SUM(Order_DB[Total Revenue])**



### **Total Profit**

Total Profit = SUM(Order_DB[Profit])**



### **Total Quantity**

Total sold Quantity = SUM(Order_DB[Quantity])**



### **Sales Target**

Sales Target = SUM(Sales_DB[Target])**



### **Average Profit in Delhi**

Avg Profit in Delhi = CALCULATE(AVERAGE(Order_DB[Profit]),'Orders List_DB'[State]="Delhi")**



### **Year-to-Date (YTD) Sales**

YTD = 
TOTALYTD([Total sales],'Orders List_DB'[Order Date].[Date])**



### **Minimum Target**

Minimum Target = MIN(Sales_DB[Target])**


These measures enable dynamic reporting and interactive filtering throughout the dashboard.

---

# 📊 Dashboard Visualizations

The dashboard contains multiple interactive visualizations.


## KPI Cards

Displays important business metrics such as:

* Total Sales
* Total Profit
* Total Quantity
* Order Count
* Sales Target

---

## Clustered Column Chart

Compares Sales Targets across different product categories to understand business expectations.

<img width="857" height="575" alt="image" src="https://github.com/user-attachments/assets/d519b4c8-ee3c-4283-b1c7-fad4433f2f8b" />

---

## Donut Chart

Displays maximum profit earned by each product sub-category and identifies the most profitable products.


<img width="772" height="583" alt="image" src="https://github.com/user-attachments/assets/6426113a-a15f-40b3-a934-61b4f926b38e" />


---

## Line Chart

Shows monthly sales target trends throughout the year and highlights seasonal business patterns.

<img width="1260" height="437" alt="image" src="https://github.com/user-attachments/assets/83614cf6-24ba-4174-8517-cc60d0bade91" />

---

## Scatter Chart

Compares Quantity Sold against Total Profit to identify:

* High-profit products
* High-volume products
* Loss-making products

<img width="1202" height="588" alt="image" src="https://github.com/user-attachments/assets/78595ead-ffce-4f48-b2f9-47b2e6ac3086" />

---

## Multi-row Card

<img width="345" height="137" alt="image" src="https://github.com/user-attachments/assets/4c84fb91-f27e-4eb8-bf93-c37e532df2c2" />

---

## Matrix Visuals

Provides detailed comparisons of:

* Monthly sales targets
* Annual sales targets
* Actual revenue
* Revenue differences
* Category-wise performance

---

## Map Visualization

Displays geographical sales distribution across different cities, helping identify high-performing and low-performing regions.

<img width="1171" height="650" alt="image" src="https://github.com/user-attachments/assets/67d394f8-4896-4e56-8737-cc0803520713" />

---

## Treemap

Represents sales contribution by each product sub-category using proportional rectangles for easy comparison.

<img width="957" height="543" alt="image" src="https://github.com/user-attachments/assets/2f42bc9d-77a3-4541-a241-d0da66b2c95c" />

---

## Funnel Chart

Ranks states according to total order count, highlighting regions with the highest customer activity.

<img width="712" height="588" alt="image" src="https://github.com/user-attachments/assets/6da59863-b3ba-4843-8cf8-e4fae6d74d7e" />

---

# ** 📈 Key Insights**

## **💰 Overall Business Performance**

- Total Sales: **₹21,46,870**

- Sales Target: **₹4,35,900**
  

## **Target Achievement**

- Sales exceeded the target by **₹17,10,970** (approximately 392% above the target).
 

## **🏆 Category Performance**

- Electronics generated the highest revenue of **₹8,16,583**, exceeding its target by **₹6,87,583**.

- Furniture generated **₹6,65,765**, surpassing its target by **₹5,32,865**.

- Clothing achieved **₹6,64,522**, exceeding its target by **₹4,90,522** despite having the highest assigned target.

 
## **🎯 Sales Target Analysis**

- Clothing had the highest sales target of **₹1,74,000**.

- Furniture was assigned **₹1,32,900**.

- **Electronics** had the lowest category target of **₹1,29,000**.

 

## **📅 Monthly Sales Targets**

- **March** recorded the highest monthly target of **₹43,800**.
  
- **April** had the lowest monthly target of **₹31,400**.
  
- The annual sales target across all months was **₹4,35,900**.
  
 
## **💹 Profitability Insights**

- Printers generated the **highest total profit** of approximately **₹6,000**.
  
- Bookcases recorded the **second-highest profit** of around **₹5,000**.
  
- Tables incurred the largest loss of approximately **₹4,000**.
  
- Electronic Games also showed a loss of around **₹1,500**.
  

## **🛍️ Sales by Sub-Category**

- Printers achieved the highest sales of **₹308K**.
  
- Bookcases followed with **₹296K**.
  
- Saree contributed **₹264K** in sales.
  
- Skirt recorded the lowest sales at ₹10K, while Kurti generated only **₹15K**.

 
## **🗺️ Regional Performance**

- **Madhya Pradesh** recorded the **highest** number of customer orders.
  
- **Maharashtra** ranked **second** with **290** orders.
  
- **Gujarat** and **Rajasthan** recorded **87** and **74** orders respectively.
  
- **Tamil Nadu** and **Sikkim** had the lowest order volumes with **26** and **24** orders.
  

## **📌 Minimum Sales Targets**

- **Clothing**-related sub-categories such as Saree, Shirt, T-Shirt, Kurti, Leggings, 
Skirt, Stole, Trousers, and Handkerchief had the **highest minimum target of ₹12,000**.

- **Furniture**-related products had a **minimum target of ₹10,400**.
  
- Accessories, Phones, Printers, and Electronic Games had the **lowest minimum target of ₹9,000**.

---

## 💡 Business Recommendations

* Increase investment in high-performing categories such as **Electronics** and **Printers** to maximize revenue and profitability.
  
* Review pricing, discounts, and operational costs for **loss-making products** like Tables and Electronic Games.
  
* Strengthen marketing efforts in **low-performing states** to improve customer reach and sales.
  
* Revise future **sales targets** based on historical performance, as current sales significantly exceed the targets.
  
* Optimize inventory planning before **peak sales periods** to ensure product availability and avoid stock shortages.
  
* Continuously monitor KPIs using Power BI dashboards to support faster, data-driven business decisions.
  

---

# 💻 Tools & Technologies Used

* Microsoft Power BI Desktop
* Power Query Editor
* DAX (Data Analysis Expressions)
* Data Modeling
* Microsoft Excel
* Data Visualization
* Business Intelligence

---

# 🚀 Skills Demonstrated

This project demonstrates practical experience in:

* Data Cleaning
* Data Transformation
* Data Modeling
* Relationship Management
* Bridge Table Creation
* DAX Calculations
* Time Intelligence Functions
* KPI Development
* Dashboard Design
* Business Intelligence Reporting
* Interactive Visualization
* Business Analytics
* Sales Performance Analysis

---

# 📷 Dashboard Preview

<img width="1348" height="768" alt="image" src="https://github.com/user-attachments/assets/ee7fec6d-d470-4880-8107-125e3428c6ae" />

---

# 🎓 Learning Outcomes

Through this project, I gained hands-on experience in:

* Building professional Power BI dashboards
* Writing DAX measures and calculated columns
* Creating efficient data models
* Implementing Time Intelligence calculations
* Designing interactive reports
* Performing sales and profitability analysis
* Converting business requirements into actionable insights

---

# 📌 Conclusion

This project demonstrates the complete workflow of developing a Business Intelligence solution using Power BI. 
Starting from raw sales data, the project applies data modeling, DAX calculations, and visualization techniques to 
create an interactive dashboard that supports strategic business decisions.

The dashboard enables stakeholders to monitor sales performance, evaluate profitability, compare targets with 
actual performance, identify regional trends, and make informed decisions based on real-time insights. It showcases 
strong analytical, visualization, and problem-solving skills that are essential for Data Analyst and Business 
Intelligence roles.

---

## 👩‍💻 Author

**Sabana Asmi**

Aspiring **Data Analyst** skilled in **Excel, SQL, Power BI, and Data Visualization**, 

Passionate about transforming raw data into actionable business insights.


