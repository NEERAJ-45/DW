## Experiment No. 5  
### Title: Demonstration of Simple Transformation in ETL using SSIS

---

## Step-by-Step Procedure

### 1. Prepare Source Excel File
- Create an Excel file with columns:  
  CustomerCode, CustomerName, ProductPurchase, Quantity, Amount, CustomerVisitedDate.

---

### 2. Create a New SSIS Project
- Open SSDT → New Integration Services Project.  
- Drag **Data Flow Task** to Control Flow.  
- Double-click to enter the Data Flow pane.

---

### 3. Configure Excel Source (Extraction)
- Drag **Excel Source** into Data Flow.  
- Edit → choose the Excel file → New connection.  
- Check “First row has column names”.  
- Set Data Access Mode = Table or View.  
- Select the correct worksheet.

---

### 4. Add Derived Column to Convert Amount to USD
- Drag **Derived Column**.  
- Connect Excel Source (blue arrow) → Derived Column.  
- Edit Derived Column:
  - Derived Column Name: **USDAmount**  
  - Derived Column Type: Add New Column  
  - Expression: Amount / 60  
  - Data Type: float

---

### 5. Add Second Derived Column to Convert Product Name to Uppercase
- Drag another **Derived Column**.  
- Connect previous Derived Column → this one.  
- Edit:
  - Derived Column Name: ProductPurchase  
  - Replace existing column  
  - Expression: UPPER(ProductPurchase)

---

### 6. Create Destination Table in SQL Server
- In SQL Server, create a table with the same fields as the Excel file plus USDAmount.  
  (Table must match the transformed columns.)

---

### 7. Configure ADO.NET Destination (Loading)
- Drag **ADO.NET Destination** into Data Flow.  
- Connect second Derived Column → Destination.  
- Edit:
  - Create new ADO.NET connection to SQL Server.  
  - Select database → Select destination table.  
  - Map all columns.

---

### 8. Execute the ETL Package
- Go to Debug → Start (or press F5).  
- Verify:
  - Data is read from Excel.
  - Amount is converted to USD.
  - Product Name is uppercase.
  - Final records are loaded into SQL Server.

---

## Self-Study
- Perform the same ETL process using **Talend ETL Tool**.

