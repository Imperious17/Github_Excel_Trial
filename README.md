# Github\_Excel\_Trial

First Dummy project I create so that I can understand how to use Github and excel

# **📦 Inventory Replenishment & Risk Analysis Project**

## **📘 1. Project Overview**

This project performs a complete **Inventory Replenishment and Risk Analysis** using a dataset of **6,000 SKUs** distributed across multiple warehouses, categories, and suppliers.

The project simulates a real-world supply chain environment and focuses on:

* Identifying stockout risks
* Detecting overstock and working capital inefficiency
* Optimizing reorder quantities
* Analyzing supplier performance and lead-time impact
* Building an interactive dashboard for management review

The dataset includes:

* Daily demand
* Lead time
* Safety stock
* Current inventory
* Reorder points
* Unit cost
* Inventory value
* Supplier & warehouse details
* Stockout risk scores

---

## **🛠 2. Tools Used**

### **Microsoft Excel**

* Excel Tables
* Advanced formulas
* Nested IF logic
* PivotTables
* PivotCharts
* Slicers
* Conditional formatting
* Scenario analysis (What-If modeling)
* Dashboard creation

Excel was selected because:

* It is ideal for 5k–10k row operational datasets
* Fast to prototype insights
* Widely used in operations & supply chain roles
* Easy to visualize and share results

---

## **🎯 3. Project Goals**

1. Compute essential operational metrics:

   * Demand during lead time
   * Recommended reorder quantity
   * Inventory status
   * Risk segmentation
   * Inventory value

2. Analyze performance through PivotTables:

   * Warehouse-level inventory exposure
   * Category-wise risk matrix
   * Supplier performance (lead time vs risk)

3. Visualize insights:

   * Stacked risk distribution charts
   * Warehouse inventory charts
   * Top 20 critical SKU chart

4. Perform scenario modeling:

   * Measure the impact of **20% lead-time reduction**

5. Build a professional Excel Dashboard:

   * KPIs
   * Charts
   * Filters
   * Actionable insights

---

## **🧭 4. How I Did the Project**

### **### Step 1: Dataset Preparation**

* Imported CSV into Excel
* Converted to a Table named `Inventory`
* Cleaned and validated fields
* Added new calculated columns

### **### Step 2: Calculated Key Metrics**

Added computed columns including:

* **Demand During Lead Time**

  ```
  =[@Daily_Demand] * [@Lead_Time_Days]
  ```

* **Recommended Reorder Quantity (ROQ)**

  ```
  =MAX(0, [@Demand_During_Lead_Time] + [@Safety_Stock] - [@Current_Inventory])
  ```

* **Inventory Status Flag** (Urgent / Normal / Overstocked)

  ```
  =IF(
      OR([@Current_Inventory] < [@Safety_Stock],
         [@Current_Inventory] < [@Reorder_Point]),
      "Urgent Reorder",
      IF(
          [@Current_Inventory] > 2 * ([@Demand_During_Lead_Time] + [@Safety_Stock]),
          "Overstocked",
          "Normal"
      )
  )
  ```

* **Inventory Value**

  ```
  =[@Current_Inventory] * [@Unit_Cost]
  ```

* **Risk Band Classification**

  ```
  =IF([@Stockout_Risk_Score] >= 0.8, "Critical",
      IF([@Stockout_Risk_Score] >= 0.6, "High",
         IF([@Stockout_Risk_Score] >= 0.3, "Medium", "Low")
      )
  )
  ```

### **### Step 3: PivotTable-Based Analysis**

Created PivotTables to analyze:

#### **Warehouse Analysis**

* Total inventory value
* Critical-risk SKU count
* Warehouse exposure

#### **Supplier Analysis**

* Average lead time
* Average risk score
* Item count

#### **Category-Level Risk Analysis**

* Inventory value segmented by Risk_Band
* Used for stacked column visualization

### **### Step 4: Visualization Layer**

Created the following charts:

* **Stacked Column Chart**
  Risk distribution by category

* **Warehouse Inventory Chart**
  Total value per warehouse

* **Top 20 Critical SKUs Chart**
  Highest-risk SKUs sorted by risk score

### **### Step 5: Scenario Analysis (What-If)**

Modeled a **20% reduction in lead time**:

Added:

* Adjusted Lead Time

  ```
  =[@Lead_Time_Days] * 0.8
  ```

* Adjusted Reorder Quantity

  ```
  =MAX(0, [@Daily_Demand] * [@Adj_Lead_Time] + [@Safety_Stock] - [@Current_Inventory])
  ```

Compared:

* Current total ROQ
* Adjusted ROQ
* Quantified improvement in working capital

### **### Step 6: Dashboard Development**

Dashboard includes:

* Total Inventory Value
* No. of SKUs
* Urgent Reorder count
* Critical Risk Value
* Lead Time metrics
* Slicers for Category, Supplier, Warehouse, Risk Band
* Pivot-linked charts

---

## **📊 5. Key Insights (Placeholders)**

```
[Insert: Which warehouse carries highest risk]

[Insert: Supplier with longest average lead time]

[Insert: Most risk-heavy category]

[Insert: Effect of reducing lead time by 20%]
```

You will fill these after finishing the analysis.

---

## **📷 6. Screenshots (Placeholders)**

Add actual screenshots into an `/images` folder:

```
![Dashboard](images/dashboard.png)

![Pivot Table](images/pivot.png)

![Risk Chart](images/risk_by_category.png)

![Scenario Analysis](images/scenario.png)
```

---

## **📌 7. Conclusion**

This project demonstrates end-to-end operational analytics using Excel—covering data preparation, inventory logic, risk scoring, multi-criteria evaluation, scenario modeling, and executive dashboard creation.

It reflects real responsibilities of:

* Supply Chain Analyst
* Inventory Planner
* Operations Analyst
* Business Analyst
* Demand & Replenishment Specialist




