## Experiment No. 8  
### Title: Cube Creation and OLAP Operations using SQL Server Analysis Services (SSAS)

---

## Step-by-Step Procedure

### 1. Create a New SSAS Project
- Open SQL Server Data Tools (SSDT).  
- Go to File → New → Project.  
- Select Business Intelligence → Analysis Services Project.  
- Name the project (e.g., AdventureWorksCube1).  
- Click OK.

---

### 2. Create a Data Source
- In Solution Explorer, right-click Data Sources → New Data Source.  
- Open Data Source Wizard → Next.  
- Click New Connection.  
- Select server name.  
- Select database: **AdventureWorksDW2012** / **AdventureWorksDW2014** (whichever is installed).  
- Choose authentication.  
- Test Connection → OK.  
- Impersonation: Use Service Account.  
- Finish.

---

### 3. Create a Data Source View (DSV)
- Right-click Data Source Views → New Data Source View.  
- Wizard → Next.  
- Select the data source created earlier.  
- From available tables, select **FactFinance**.  
- Click **Add Related Tables** (this auto-adds all required dimension tables).  
- Next → Name the view “Finance” → Finish.

---

### 4. Create a Cube using Cube Wizard
- Right-click Cubes → New Cube.  
- Cube Wizard → Next.  
- Select “Use existing tables” → Next.  
- Choose the **FactFinance** table as the measure group → Next.  
- Uncheck fields that are not measures (e.g., FinanceKey) → Next.  
- Keep all Dim tables selected as dimensions → Next.  
- Name the cube **FinanceCube** → Finish.

---

### 5. Define Dimension Attributes
For each dimension:

1. Double-click the dimension (example: DimDate).  
2. Add required attributes from the Data Source View by dragging columns into **Attributes** pane.

**DimDate Attributes to Add:**  
- CalendarYear  
- CalendarQuarter  
- MonthNumberOfYear  
- DayNumberOfWeek  
- DayNumberOfMonth  
- DayNumberOfYear  
- WeekNumberOfYear  
- FiscalQuarter  
- FiscalYear  

**Other Dimensions:**  
- **DimDepartmentGroup:** DepartmentGroupName  
- **DimAccount:** AccountDescription, AccountType  
- **DimScenario:** ScenarioName  
- **DimOrganization:** OrganizationName  

Save.

---

### 6. Add Time Intelligence (BI Wizard)
- Open FinanceCube.  
- Click Business Intelligence Wizard.  
- Select “Define Dimension Intelligence”.  
- Choose **DimDate**.  
- Set dimension type = Time.  
- Map fields (Year → CalendarYear, Quarter → CalendarQuarter, etc.).  
- Finish.

---

### 7. Create Hierarchies
For **DimDate**:

- Drag CalendarYear → Hierarchy pane.  
- Add CalendarQuarter → next level.  
- Add MonthNumberOfYear → next level.  
- Rename hierarchy to “Calendar”.

Create another hierarchy “Fiscal” with:  
- FiscalYear  
- FiscalQuarter  
- MonthNumberOfYear  

Save.

---

### 8. Deploy and Process the Cube
- Go to Project → Properties → Deployment.  
- Ensure Server Name = your SSAS server (Example: `PCNAME\MSSQLSERVER`).  
- OK.  
- Build → Deploy AdventureWorksCube1.  
- Wait until deployment and processing complete.

---

### 9. Browse the Cube
- Right-click the cube → Browse.  
- Expand Measures → FactFinance → drag **Amount** into Totals/Details.  
- Expand DimAccount → drag **AccountDescription** to Rows.  
- Expand DimDate → drag **Calendar** hierarchy to Columns.  
- Expand DimScenario → drag **ScenarioName** to Filters.  
- Filter only “Budget”.  
- Expand Year → Quarter → display monthly values.

---