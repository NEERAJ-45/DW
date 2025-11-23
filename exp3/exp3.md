## Experiment No. 3  
### Title: Demonstration of Data Profiling using SQL Server Integration Services

---

## Step-by-Step Procedure

### 1. Create a New SSIS Package
- Open SSDT.  
- Create a new Integration Services Project.  
- Drag **Data Flow Task** into Control Flow (optional, but not required for profiling).  
- Drag **Data Profiling Task** into Control Flow.

---

### 2. Configure the Data Profiling Task
- Double-click the Data Profiling Task to open the editor.  
- Set:
  - Time-out (seconds) as needed  
  - OverwriteDestination = True (recommended)  
  - DestinationType = File Connection  

---

### 3. Configure Destination File
- Click **Destination** → choose **<New Connection>**.  
- In File Connection Manager:
  - Choose “Create File”  
  - Browse and create an XML file (e.g., `ProfileOutput.xml`)  
- Confirm the connection.

---

### 4. Open Quick Profile Wizard
- Go to the **General** tab.  
- Click **Quick Profile**.

---

### 5. Select Source Connection
- Click **New** to create ADO.NET connection.  
- Select:
  - Provider  
  - Server Name  
  - Database Name (e.g., AdventureWorksDW)  
- Choose the table to profile (e.g., **DimProduct**).  
- Click OK.

---

### 6. Select Profiling Options
Choose the profiles to generate:
- Candidate Key Profile  
- Column Length Distribution  
- Column Null Ratio  
- Column Pattern Profile  
- Column Statistics  
- Column Value Distribution  
- Functional Dependency  
- Value Inclusion Profile  

Select all options.

---

### 7. Review Profile Requests
- After clicking OK, go to **Profile Requests** tab.  
- Verify that all profiling requests are listed.  
- Click OK to close the editor.

---

### 8. Execute the Package
- Click **Start / F5** to run the SSIS package.  
- Package generates the XML profiling output in the destination path.

---

### 9. Open Data Profile Viewer
- After execution, open **Data Profile Viewer**.  
  - (Via Start Menu → Data Profile Viewer)  
- Click **Open** → select the generated XML file.

---

### 10. Analyze Profiling Results
- View each profile:
  - Candidate Key Profile  
  - Length Distribution  
  - Null Ratio  
  - Column Statistics  
  - Value Distribution  
  - Functional Dependency  
- Interpret data quality issues from the visual output.

---

