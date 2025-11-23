## Experiment No. 9  
### Title: Dashboard Report Creation using SQL Server Reporting Services (SSRS)

---

## Step-by-Step Procedure

### 1. Create a New SSRS Project
- Open Visual Studio.
- Create a new Report Server Project.
- Verify the folders in Solution Explorer:
  - Shared Data Sources  
  - Shared Datasets  
  - Reports  

---

### 2. Create a Shared Data Source
- Right-click Shared Data Sources → Add New Data Source.
- Set:
  - Name: any meaningful name
  - Type: Microsoft SQL Server
- Click Edit to configure the connection.

---

### 3. Configure Connection Properties
- Enter Server Name.
- Select Windows Authentication.
- Choose the database: AdventureWorksDW2014.
- Test Connection → OK.

---

### 4. Set Credentials
- Open the Credentials tab.
- Select Windows Authentication.
- Click OK.

---

### 5. Create a New Report
- Right-click Reports → Add → New Item.
- Choose Report.
- Name it (example: FirstReport.rdl).
- A blank design page appears with:
  - Data Sources  
  - Datasets  
  - Parameters  
  - Images  
  - Built-in Fields  

---

### 6. Create Dataset With SQL Query
- In Report Data pane, right-click Datasets → Add Dataset.
- Choose Use a shared data source reference.
- Query Type: Text.
- Paste this query:

```sql
SELECT 
    Cat.[EnglishProductCategoryName] AS ProductCategory,
    SubCat.[EnglishProductSubcategoryName] AS ProductSubCategory,
    Prod.EnglishProductName AS ProductName,
    Prod.Color,
    Fact.OrderQuantity,
    Fact.TotalProductCost,
    Fact.SalesAmount,
    Fact.TaxAmt,
    Fact.[Freight]
FROM FactInternetSales AS Fact
INNER JOIN DimProduct AS Prod
    ON Fact.ProductKey = Prod.ProductKey
INNER JOIN DimProductSubcategory AS SubCat
    ON Prod.ProductSubcategoryKey = SubCat.ProductSubcategoryKey
INNER JOIN DimProductCategory AS Cat
    ON SubCat.ProductCategoryKey = Cat.ProductCategoryKey
```

---

### 7. Add Pie Chart (Sales by Subcategory)
- Right-click design area → Insert → Chart.
- Select Pie Chart.
- Set chart data:
  - Values: SalesAmount  
  - Category: ProductSubCategory
- Format labels and title.

---

### 8. Apply Dataset Filter (Only Bikes Category)
- Right-click Dataset → Dataset Properties.
- Open Filters tab.
- Add filter:
  - Expression: ProductCategory  
  - Operator: =  
  - Value: Bikes  
- OK.

---

### 9. Add Column Chart (Sales vs Cost by Color)
- Insert another chart → Column Chart.
- Set chart data:
  - Values: SalesAmount, TotalProductCost  
  - Category: Color  
- Format axis titles, legends, and labels.

---

### 10. Preview Dashboard
- Click Preview.
- Check:
  - Pie chart shows only Bike subcategories.
  - Column chart shows Sales vs Cost by Color.
- Save the report.

---
