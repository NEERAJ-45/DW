## Experiment No. 11  
### Title: Human Resources Analytics

---

## Step-by-Step Procedure

### 1. Load Dataset into Power BI
- Open Power BI Desktop.  
- Click Get Data → Excel / CSV.  
- Select the HR dataset (employee demographics, performance, attrition info).  
- Load the table into Power BI.

---

### 2. Clean and Prepare the Data
- Open Power Query Editor.  
- Remove duplicates and blanks.  
- Check data types for columns like Age, Salary, Performance Rating.  
- Create calculated columns if needed (e.g., Tenure = Today − Hire Date).  
- Close & Apply.

---

### 3. Create Turnover (Attrition) Dashboard
- Insert a Card visual → show Total Employees.  
- Insert another Card → show Attrition Count.  
- Insert another Card → show Attrition Rate (measure).  
- Add a Bar Chart → Attrition by Department.  
- Add a Column Chart → Attrition by Job Role.

---

### 4. Create Performance Analysis Visuals
- Add a Line Chart → Performance Rating over Tenure or Years.  
- Add a Bar/Column Chart → Average Performance by Department.  
- Add a Combo Chart → Salary vs Performance Rating.  

---

### 5. Create Employee Demographics Visuals
- Add a Pie / Donut Chart → Gender distribution.  
- Add a Column Chart → Age Group vs Employee Count.  
- Add a Tree Map → Employees by Department.

---

### 6. Add Hiring and Recruitment Analysis
- Add a Line Chart → Number of Hires by Year.  
- Add a Bar Chart → Hiring Source vs Employee Count (if available).  
- Add a Column Chart → New Joiners by Department.

---

### 7. Add Maps (if dataset has location)
- Insert Map visual.  
- Add Location column (City/State/Country).  
- Add Employee Count as Size.

---

### 8. Add Slicers for Interactivity
- Insert Slicer → Gender  
- Insert Slicer → Department  
- Insert Slicer → Job Role  
- Insert Slicer → Performance Rating  
- Insert Slicer → Attrition (Yes/No)

Users can now filter the entire dashboard.

---

### 9. Create Measures (DAX)
Add DAX formulas for:
- Attrition Rate  
- Average Salary  
- Average Performance  
- Total Employees  

---

### 10. Format the Dashboard
- Adjust colors and fonts for clarity.  
- Add titles to all visuals.  
- Align visuals properly using Format → Align → Distribute.

---

### 11. Publish the Report
- Save the PBIX file.  
- Click Publish → Select Workspace.  
- Upload report to Power BI Service (if required).

---

