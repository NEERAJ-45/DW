## Experiment No. 7  
### Title: Demonstration of Slowly Changing Dimension (SCD) using SSIS

---

## Step-by-Step Procedure

### 1. Create Source & Destination Tables in SQL Server
- Open SQL Server Management Studio (SSMS).  
- Create **staging table** (Test_Stage):  
  - Emp_Id, Emp_Name, Country  
- Create **dimension table** (Test):  
  - Emp_Id, Emp_Name, Country, Start_Date, End_Date  
- Insert sample data into Test_Stage.

---

### 2. Create a New SSIS Project
- Open SQL Server Data Tools (SSDT).  
- File → New → Project → Integration Services Project.  
- Name it appropriately → OK.

---

### 3. Add a Data Flow Task
- Drag **Data Flow Task** to Control Flow.  
- Double-click to open Data Flow pane.

---

### 4. Configure OLE DB Source
- Drag **OLE DB Source** into Data Flow.  
- Edit → Create new connection to SQL Server.  
- Select **Test_Stage** table as the source.  
- Select Columns → OK.

---

### 5. Add Slowly Changing Dimension (SCD) Transformation
- Drag **Slowly Changing Dimension** component.  
- Connect OLE DB Source → SCD.

---

### 6. Configure SCD Wizard
1. Right-click SCD → Edit.
2. Select **Test** table as the Dimension table.
3. Set **Business Key** = Emp_Id.

---

### 7. Configure Column Change Behavior
- For **Emp_Name** → mark as **Changing Attribute**.  
  (updates existing record, no history tracked)  
- For **Country** → mark as **Historical Attribute**.  
  (creates a new row when value changes)

---

### 8. Set Start/End Date Tracking
- Choose: **Use StartDate and EndDate to identify current and expired records**.  
- Map:
  - Start_Date → StartDate  
  - End_Date → EndDate

---

### 9. Finish the Wizard
- Leave default options for update/insert components.  
- Click **Finish**.  
- SSIS automatically creates:
  - Insert path  
  - Update path  
  - Historical insert path

---

### 10. Run the Package (First Load)
- Click Run.  
- SSIS loads **all new records** into Test table.  
- Verify data in Test:
  - Start_Date = current date  
  - End_Date = NULL

---

### 11. Update Staging Table (Simulate Change)
- Example update in SQL:
  ```
  update test_stage set Country='USA' where Emp_Id=1;
  ```
- Run package again.

---

### 12. Observe Type-2 Behavior
- SSIS detects change in Country → inserts **new row**.  
- Old row gets **End_Date updated**.  
- New row gets **Start_Date = current date**, End_Date = NULL.

---

### 13. Verify Results in SQL
- Run SELECT on Test table.  
- You should see:
  - Old record (expired)  
  - New record (current)

---
 