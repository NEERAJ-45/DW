## Experiment No. 10  
### Title: Movie Sales Visualization using Power BI

---

## Step-by-Step Procedure

### 1. Import the Movie Dataset
- Open Power BI Desktop.  
- Click Get Data → Excel / CSV.  
- Select the IMDb Movie dataset (2006–2016).  
- Load the table into Power BI.

---

### 2. Clean and Prepare the Data
- Open Power Query Editor.  
- Remove missing or null values in Budget, Gross, Genre, and Scores.  
- Convert Budget, Gross, and IMDb Score to correct data types.  
- Create calculated columns if needed (e.g., Profit = Gross – Budget).  
- Close & Apply.

---

### 3. Perform Univariate Analysis
- Create a Histogram → IMDb Score distribution.  
- Create a Column Chart → Budget distribution.  
- Create a Column Chart → Gross earnings distribution.

---

### 4. Perform Bivariate Analysis
- Scatter Plot → Budget vs Gross (to check correlation).  
- Bar Chart → Average Gross by Genre.  
- Line Chart → IMDb Score trend over the years.  

---

### 5. Create Radial Bar Chart (Genre Analysis)
- Insert Radial Bar visual (from marketplace if needed).  
- Set:
  - Category: Genre  
  - Value: Average Gross / Average IMDb Score  
- Format labels and colors.

---

### 6. Create KDE Plot (Score Density)
- Insert custom KDE visual (Gaussian Kernel Density Estimation).  
- Set:
  - Value: IMDb Score  
  - Category: Genre  
- Adjust smoothing parameter for clarity.

---

### 7. Create Area Chart (Revenue Trend)
- Insert Area Chart.  
- Axis: Year  
- Value: Total Gross  
- Legend: Genre  
- This shows cumulative revenue growth over time.

---

### 8. Add Interactive Slicers
Add slicers for:
- Genre  
- Country  
- Score Range (use numeric range slicer)  
- Year  

This allows dynamic filtering of the entire dashboard.

---

### 9. Create DAX Measures
Add the following measures:
- Total Movies  
- Average IMDb Score  
- Total Gross  
- Total Budget  
- Profit = SUM(Gross) – SUM(Budget)

Use these in Cards for summary statistics.

---

### 10. Dashboard Formatting
- Align all visuals using Format → Align → Distribute.  
- Add proper titles to each chart.  
- Use consistent color themes for Genre and Score visuals.  
- Add a page title: Movie Sales and IMDb Score Analysis (2006–2016).

---

### 11. Generate Insights
- Observe which genres earn the highest Gross.  
- Check whether higher IMDb scores lead to higher revenue.  
- Identify profitable years and declining trends.  
- Use slicers to study country-wise or genre-wise performance.

---

### 12. Publish the Report
- Save the PBIX file.  
- Click Publish and upload the dashboard to Power BI Service (if required by college).

---

