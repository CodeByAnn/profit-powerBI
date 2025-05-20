# profit-powerBI
Profitability &amp; Sales Dashboard (Power BI) 

## **Summary**

This project involves the development of an interactive Power BI dashboard to analyze company performance across three key dimensions: gross profit, quantity, and sales. The report enables a comprehensive comparison between current year-to-date (YTD) and previous year-to-date (PYTD) values, with a focus on profitability segmentation and regional performance. The dashboard was built for dynamic business insights using layered filters and custom visualizations.

---

### **Dataset Overview**

- Internal company performance data for the year **2023**
- Metrics: **Gross Profit, Quantity Sold, Total Sales**, and **Gross Profit %**
- Granularity: Monthly data grouped by **country**, **product type**, and **customer segments**
- Simulated data to enable safe public sharing

---

### **Key Features**

### 1. **Gross Profit Analysis**

- Visualized YTD vs PYTD gross profit changes with a waterfall chart (Year-to-Date (YTD) and Previous Year-to-Date (PYTD))
- Segmented performance by product type and region
- Highlighted top contributors and detractors across months

### 2. **Quantity & Sales Breakdown**

- Created parallel dashboards to compare units sold and total sales value
- Used stacked bar charts to show seasonal trends by product type
- Line overlays visualize year-over-year changes

### 3. **Profitability Segmentation**

- Implemented a scatter plot to assess customer accounts by **GP%** and **Value YTD**
- Enabled quick identification of high-value, low-margin segments

---

### **Tech Stack**

- **Power BI Desktop**
- DAX for calculated KPIs
- Relational data model with multiple fact and dimension tables

---

---

### **Conclusion**

This dashboard delivers strategic visibility into financial performance through interactive analytics. It helps stakeholders quickly spot underperforming regions, evaluate product trends and assess customer profitability. The modular tab design and filtering options make it adaptable for different business needs and audiences.

**main DAX function I used:**

### **CALCULATE()**

**YTD Sales = CALCULATE([Total Sales], DATESYTD('Date'[Date]))**

With use of that function, we can modify the filter context to calculate total sales specifically for the year-to-date period.

---

### **DATESYTD()**

**YTD Sales = CALCULATE([Total Sales], DATESYTD('Date'[Date]))**

With use of that function, we can generate a running total from the beginning of the year up to the selected date in the filter context.

---

### **SAMEPERIODLASTYEAR()**

**PYTD Sales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))**

With use of that function, we can return the same date range from the previous year, enabling a year-over-year comparison.

---

### **DIVIDE()**

**GP% = DIVIDE([Gross Profit], [Total Sales])**

With use of that function, we can safely divide gross profit by total sales while avoiding errors caused by division by zero.

---

### **RANKX()**

**Country Rank = RANKX(ALL('Country'), [Total Sales])**

With use of that function, we can rank countries dynamically based on their total sales values within the entire dataset.
