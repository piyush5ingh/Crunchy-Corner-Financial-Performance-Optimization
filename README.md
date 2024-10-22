# Crunchy-Corner-Financial-Performance-Optimization


This repository contains the analysis, optimization, and budgeting framework developed for **Crunchy Corner**, one of India's largest fast food chains. It serves as a comprehensive solution for financial performance analysis, business optimization, and detailed budgeting strategies using **Power BI** and **Excel**.

## Project Overview
Crunchy Corner is a fast food restaurant chain with over 1000 restaurants, offering the largest SKU in the industry. This project focuses on building a dashboard for financial performance analysis and optimization.

## Client Requirements
- **Dashboard** for Financial Performance Evaluation
- **Optimization** of Business Processes
- **Financial Planning** and **Budgeting**

---

### **Table of Contents**
1. [Project Overview](#project-overview)
2. [Tools Used](#tools-used)
3. [Data Modeling](#data-modeling)
4. [Financial Performance](#financial-performance)
5. [Business Optimization](#business-optimization)
6. [Budgeting Analysis](#budgeting-analysis)
7. [Advanced Analytics](#advanced-analytics)
8. [DAX Formulas & Visualizations](#dax-formulas-visualizations)

---

## 1. Project Overview

Crunchy Corner serves millions of customers daily across multiple locations in India. The goal of this project is to monitor financial health, optimize business operations, and improve budgeting processes.

- **Company Name**: Crunchy Corner
- **Industry**: Fast Food Chain
- **Goal**: Optimize Financial Performance, Business, and Budgeting.

## 2. Tools Used
- **Power BI Desktop**: For financial analysis and visualization.
- **Excel**: For data cleaning and reporting.
- **Power Query**: Used in both Power BI and Excel for data cleaning.

---

## 3. Data Modeling

The data is divided into **Fact Tables** and **Dimension Tables** to create a relationship model for effective reporting.

### Fact Tables
- **Actual**: Contains transactional data such as Gross Sales, Net Revenue, COGS, etc.
- **Budget**: Budgeted values for financial metrics.

### Dimension Tables
- **DimProduct**: Contains product-related details.
- **DimDate**: Contains date details.
- **DimLocation**: Location-based analysis.
- **DimChannel**: Sales and distribution methods.
- **DimClusterHead**: Responsible for overseeing operations in regions.

### Power BI Relationship: 

To create DAX formulas, establish a relationship between the columns in the Actual table (Fact table) and the Dimension tables.

**One-to-Many:** One-to-many relationship in DAX links dimension tables (unique values) to fact tables (repeated values), enabling efficient ```filtering``` and ```aggregation``` across tables. It ensures accurate analysis, with DAX functions like ```CALCULATE``` and ```RELATEDTABLE``` leveraging these relationships for data calculation and reporting in Power BI.

  a.  **Actual**```[Product_Id]```to **Dimproduct**```[Product_Id]``` | For Product Information. 
  
  b.	**Actual** ```[Date_Id]```to **Dimdate**```[ Date_Id]``` | For Date Information.
  
  c.	**Actual** ```[Cluster Head]``` to **Dimclusterhead**```[Cluster Head]```| For Cluster Head Information.
  
  d.	**Actual** ```[Channel]```to **Dimchannel**```[Channel]```| For Channel Information.
  
  e.	**Actual** ```[Location]``` to **Dimlocation**```[Location]``` | For Location Information.

### Dax Farmula for Calculating Matrix 
---
**•	Aggregation Functions**
---
```SUM```,```SUMX```, ```AVERAGE```, ```AVERAGEX ```, ```COUNT```,  ```COUNTA```, ```MIN```, ```MAX```

---
**•	Time Intelligence Functions**
---
```TOTALYTD```, ```PREVIOUSYEAR```, ```DATEADD```, ```SAMEPERIODLASTYEAR```, ```PREVIOUSMONTH``` ,```EOMONTH```,```EDATE```

---
**•	Logical and Conditional Functions**
---
```IF```, ```IFERROR```, ```SBLANL```, ```SWITCH```,```AND```, ```OR```, ```IN```

---
**•	Mathematical Functions**
---
```DIVIDE```,```MULTIPLICATION```

---
**•	Filter Functions**
---
```CALCULATE```, ```FILTER```, ```ALL```, ```ALLSELECTED```, ```SELECTEDVALUE```, ```VALUES```

---
**•	Text Functions**
---
```CONCATENATE```,```ORMAT```

---
**•	Ranking and Comparison Functions**
---
```RANKX```, ```TOPN```

---

## 4. Financial Performance

In this section, the following key metrics were calculated using **DAX** in Power BI:
- **Sales**, **Gross Profit**, **EBITDA**, **PAT**, and **SKU**
- **Year-over-Year (YoY)** change in Sales, Gross Profit, EBITDA, and PAT.

### Visuals:
- 100% stacked column chart showing Sales, Gross Profit, EBITDA, PAT.
- Sales bifurcation by **Category** & **Location**.
- Sales trends & comparison by Channel and Volume trends.

---

## 5. Business Optimization
-  Top Category by Gross Profit & Net Revenue (Scatter Plot)
-  Gross Profit & Volume Comparison with Average (Dynamic)
-  Pareto Analysis (Level 1,2,3).
-  Show highest sales by category and % of SKU Contribution bar line chart


### Key Focus Areas
1. **Top Categories** by **Gross Profit** and **Net Revenue** (scatter plot).
2. **Pareto Analysis**: Identifying top SKUs contributing to sales using the 80/20 rule.

### Optimization Steps
**Quadrant Analysis:** Quadrant Analysis to Identify category, Sub Category high Contribution by sales & Gross Profit Quadrant Analysis to Identify Location high Contribution by sales & Gross Profit.

**GP Comparison :** ```Gross Profit & Volume Comparison for Category.```

**Pareto Principle (80/20 Rule):** ```A principle that suggests that a small percentage of product (20%) are responsible for a large percentage of outcomes (80%)```

  **Level:1-** ```Ascending order (Total Sales / Ranking of SKU By Sales/ Cumulative Sales/ Calculate Total SKU Sales/ Cumulative % = Cum/Total SKU sales/ SKU Count/ Cumulative sku Count/ Net SKU Count/ Cum SKU %```
    
  **Level:2-** ```Descending order (Des SKU NR)```
    
  **Level:3-** ```Pareto Base/ Pareto % Top N revenue```

```Show Sales & % SKU```
```Calculate: Total Sales / %SKU Over Total SKU```


---

## 6. Budgeting Analysis

**a.	PVM Analysis**
**b.	Variance Analysis(Actual /Variance)**
**c.	Actual Vs Budget Financial Analysis for Business Drivers ( Sales, EBITDA, PAT, Volume) with Trend YoY**
**d.	Actual Vs Budget Financial Analysis for Cost  Drivers ( COGS, Packaging, Marketing) with Trend YoY**

### PVM Analysis (Price, Volume, Mix) 
PVM Analysis is a technique used to analyse the changes in a company’s revenue by breaking down the contributing factors into three main components:
  1.	**Price:** ```The impact of changes in the price of products or services sold.```
  2.	**Volume:** ```The effect of changes in the quantity of products or services sold.```
  3.	**Mix:** ```The impact caused by selling different types or categories of products with varying profit margins (high-margin vs. low-margin products).```
  
**The goal of PVM analysis is to understand how much each factor (Price, Volume, Mix) contributes to changes in revenue or profit, which helps businesses make better decisions around pricing strategies, sales efforts, and product portfolio management**
```PVM Analysis helps to understand the factors affected the business to Increase or Decrease``` 

### Formula for Actual vs. Budget PVM Analysis 
1.	**Price Impact:** This shows the effect of the difference in the prices between actual and budgeted values, assuming the volume stayed constant.

                                Price  = ({Actual Price} - {Budgeted Price}) *{Actual Volume}
•	**Change in revenue due to price deviations from the budget.**

2.	**Volume Impact:** This shows how changes in sales volume (actual vs. budget) impacted revenue, assuming the price remained the same.

                                 Volume = ({Actual Volume} - {Budgeted Volume}) * {Budgeted Price}
•	**Revenue difference caused by selling more or fewer units than planned.**

3.	**Mix Impact:** This shows how changes in the mix of products sold (high-margin vs. low-margin) affect revenue, assuming no price or volume change. This focuses on the composition of what was sold compared to what was budgeted.

                                  Mix = ({Actual Volume} * ({Actual Price} - {Budgeted Price}))

•	**The impact of changes in the mix of products or services sold compared to the budgeted plan.**

**Key Takeaways:**
•	Price Impact tells you how much revenue change is due to charging a higher or lower price than budgeted.
•	Volume Impact explains the effect of selling more or fewer units compared to the plan.
•	Mix Impact shows the revenue difference due to changes in the mix of products sold (e.g., selling more high-margin items).

**Why Use Actual vs. Budget in PVM Analysis?**

**Assess performance vs. expectations:** It breaks down how well you performed compared to the budget and why those differences occurred.
**Identify missed opportunities:** Understand if deviations were due to under/overpricing, lower/higher sales volume, or changes in the mix of products sold.
**Improve future planning:** Use insights to refine pricing strategies, set more realistic sales volume targets, or adjust the product mix in future budgeting.

### Variance (Actual vs Budget) with M3 Advanced Condition.

This analysis evaluates business performance by into three keys (M3): “More,” “Meet,” and “Misses.” These outputs are based on the year-over-year (YOY) net revenue growth percentage (NR Var. %) and the gross profit variance (GP Var. %). The final output is converted into numeric values (1, 2, or 3) for easier monitoring and reporting.


**Key Variables:**
  - ```Net Profit Variable Parameter: Represents a percentage parameter```
  - ```Gross Profit Variabl Parameter: Represents a percentage parameter```
  - ```Conditions: A scaling factor for the gross profit variance.```

**The formula categorizes the results into three groups and assigns them a numeric value:**
1.	**More (1):** ```Indicates high revenue growth and positive gross profit variance.```
2.	**Meet (2):** ```Represents stable or moderate growth with acceptable gross profit.```
3.	**Misses (3):** ```Reflects negative revenue growth and/or gross profit losses.```
   
**Purpose of the Formula:**
Performance Tracking: Helps track whether business performance in terms of net revenue growth and gross profit variance is exceeding expectations, meeting expectations, or missing targets.
Monitoring: The numeric output (1, 2, 3) allows for simple monitoring of trends, facilitating visualization and further analysis.


---

## 7. Advanced Analytics

**M3 DAX Formula:** Variance (Actual vs Budget) with M3 Advanced Condition.
```DAX
GP Var. Adjustments = GENERATESERIES(-50, 50, 0.5)
NR Var. Adjustment = GENERATESERIES(-50, 50, 0.5)
```
**M3 Advanced Condition**
```DAX
M3 Advanced Condition = 
VAR B = 'NR Var. Adjustment'[NR Adjustment  Value]
VAR C = 'GP Var. Adjustments'[GP Adjustments  Value]
Var A = if(
    [B/A]>B*0.01,
        if([B_GP Var %]>0,"More",if([B_GP Var %]<-C*0.01,"Misses","Meet")),
    if([B/A]<-B*0.01,
        if([B_GP Var %]>0,"Meet","Misses"),
    if([B_GP Var %]>-C*0.01,"Meet","Misses")))

Return SWITCH(A,
"More",1,
"Meet",2,
"Misses",3)
```

**PVM Analysis**
```DAX
   Create Table: PVM Analysis = 
DATATABLE(
    "ID", INTEGER,
    "Factor", STRING,
    {
        {1, "Actual NR"},
        {2, "Vol"},
        {3, "Price"},
        {4, "Mix"},
        {5, "Budget NR"}
    }
)

```

**Create Measure:** for created Column of table
```DAX
PVM Values = SWITCH(MAX('PVM Analysis'[id]),
                            1,[A_NR],
                                 2, [PVM Vol]
                                 ,3,[PVM Price],
                                 4,[PVM MIX],
                                 5,[BNR]          
                            )
```
**Diagram:** Waterfall Chart for comparison 

**Pareto (80/20 ) Analysis**
```DAX
Rank =
RANKX(ALL(Dim_Product[SKU Description]),[A_NR],,DESC)
```
```DAX
Cumulative SKU NR Total =  SUMX(TOPN([Rank],ALL(Dim_Product[SKU Description]),[A_NR],DESC),[A_NR])
```
```DAX
Total SKU NR = 
SUMX(ALL(Dim_Product[SKU Description]),[A_NR])
```

```DAX
Cumulative SKU NR Total % =
DIVIDE([20/80 CuM NR],[20/80 Total SKU NR],0)
```
**•	Same DAX calculation use for Cumulative SKU %**
**Pareto Base/ Pareto % Top N revenue :**
```DAX
Created Parameter Base Value = SELECTEDVALUE('Value'[1Parameter], 10000)
```

```DAX
Pareto Top NR =
VAR =If([SKU]>=SELECTEDVALUE('Value'[1Parameter]),
sumx(TOPN(SELECTEDVALUE('Value'[1Parameter]),ALLSELECTED(Dim_Product[SKU Description]),[A_NR]),[A_NR]),BLANK())

RETURN 
A
```

```DAX
Pareto % Top NR = 

VAR A = ([Pareto Top NR]/[A_NR])

return 
if(A>1,1,A)
```
   **For Previous YTD NR** 
```DAX
PYTD= 
TOTALYTD([A_NR],
SAMEPERIODLASTYEAR(Dim_Date[Month End_Date]),ALL(Dim_Date))
```
**Year Over Year Growth**
```DAX
YOY YTD = DIVIDE(([CYTD NR]-[PYTD NR]),[PYTD NR])
```
**Same period last Year**
```DAX
Same period last Year= CALCULATE([A_NR],

SAMEPERIODLASTYEAR(Dim_Date[Month End_Date]),ALL(Dim_Date))
```
**Non-Operating Expenses**
```DAX
Non-Operating Expenses = 
VAR _DC = SUM(Actual[Depreciation])*-1
VAR _offitem = SUM(Actual[One Off Item])*-1
VAR _Tax = SUM(Actual[Tax])*-1
VAR _IE = SUM(Actual[Interest Exp])*-1
VAR _II = Sum(Actual[Interest Income])
RETURN
_DC+_offitem+_Tax+_IE-_II
```
**Operating Expenses**
```DAX
Operating Expenses = [RM]+[F&V]+[Packing]+[S&D]+[G&A.]+[Marketing]+SUM(Actual[Other Inc & Exp])*-1
```
**Operating Profit**
```DAX
Operating Profit = [A_GP]-[Operating Expenses]
```
**OpProfitmargin**
```DAX
OpProfitmargin = DIVIDE([Operating Profit],[A_NR],0)
```


**DAX: Created  for custom Visualization and KPI Cards and Filter** 
**Channel label for bar chart**
```DAX
Channel label for bar chart = 
 VAR _item = SELECTEDVALUE(Dim_Channel[Channel])
 VAR _Val = FORMAT([A_NR],"#,##,,.0")
 VAR _PV = FORMAT([PY NR],"#,##,,.0")
 VAR _YOY = FORMAT([YoYGrowth],"0.00%")
 VAR _Lable = _item  & "|" &  _Val //& "|" & "PY: " &_PV & "|" & _YOY//

 RETURN

 _Lable
```

**label for bar chart** 
```DAX
label for bar chart = 
 VAR _item = SELECTEDVALUE(Dim_Product[Category])
 VAR _Val = FORMAT([A_NR],"#,##,,.0")
 VAR _PV = FORMAT([PY NR],"#,##,,.0")
 VAR _YOY = FORMAT([YoYGrowth],"0.00%")
 VAR _Lable = _item  & "|" &  _Val //& "|" & "PY: " &_PV & "|" & _YOY//

 RETURN

 _Lable
```

**DataBar** 
```DAX
DataBar = 
VAR NrIcons = 9
VAR PctoffBudget = DIVIDE([A_NR],[BNR])
VAR NrIcons_fil = PctoffBudget*NrIcons
var nriconsfilled = IF(NrIcons_fil<0,0,INT(NrIcons_fil))
VAR NrIcons_Empty = NrIcons-nriconsfilled
VAR Iconfill= "🟢"
VAR Iconemty = "🔴"

VAR _DataBar = 
REPT( Iconfill,NrIcons_fil)&
REPT( Iconemty, NrIcons_Empty)

RETURN
_DataBar
```



---

## **Conclusion & Further Resources**

This repository outlines a complete analysis framework for optimizing the financial performance of **Crunchy Corner**. Using **Power BI** and **DAX**, we evaluated critical business metrics such as **sales trends**, **profitability**, **budgeting**, and applied advanced analytics techniques like **Pareto** and **PVM (Price, Volume, Mix) Analysis**.

---

### **🔗 Power BI Dashboard**
To explore interactive visualizations of key financial insights, click the link below:  
[**Click here to view the Power BI Dashboard**](https://app.powerbi.com/groups/me/reports/2582e4e0-b40e-4c56-bdc8-b5ea864afd68/f0839393194979873654?experience=power-bi)

---

### **📄 Documents and Reports**
For detailed reports, project documentation, and other supporting materials, click the link below:  
[**Click here to view the Documents and Reports**](https://1drv.ms/w/c/c9e4d94d1be77dfb/EXU0dJ8wfQdOi1U3aGeEUIEBmzeRVlkMDawBiOHQgG418A?e=dyUpsC)

---

### **📊 Dataset Access**
To download or review the dataset used in this analysis, click the link below:  
[**Click here to view the Dataset**](https://1drv.ms/x/c/c9e4d94d1be77dfb/EY7LJ1uy6l1LoF_NbE7oSG0BBcgVqEgMzozbIEVce3YC6A?e=dwebux)

---

This concludes the **Crunchy Corner** financial performance optimization project. For further details, feel free to explore the repository files or use the links above.

---

### **Repository Files Overview:**
- **`/Data`**: Raw and cleaned dataset files.
- **`/DAX_Scripts`**: DAX code used in the analysis.
- **`/Visualizations`**: Screenshots of the Power BI reports.
- **README.md**: Overview and instructions.

---

