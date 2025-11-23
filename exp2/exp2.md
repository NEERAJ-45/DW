## Experiment No. 2  
### Title: Install and Configure SQL Server Business Intelligence Edition

---

## Step-by-Step Procedure

### 1. Download Installation Package
- Download SQL Server (BI-supported version) from the official Microsoft download page.
- Extract the installation media.

---

### 2. Run Setup
- Right-click `setup.exe` → Run as Administrator.
- The SQL Server Installation Center opens.

---

### 3. Navigate to Installation Section
- Click **Installation** on the left panel.
- Select **New SQL Server stand-alone installation**.

---

### 4. Setup Support Rules
- Setup auto-checks prerequisites.  
- Ensure all checks show **Passed**.  
- Click **OK**.

---

### 5. Enter Product Key
- Choose the edition or enter product key.
- Click **Next**.

---

### 6. Accept License Terms
- Tick **I accept the license terms**.
- Click **Next**.

---

### 7. Install Product Updates
- Setup checks for updates.  
- Click **Install** if updates are found.

---

### 8. Second Support Rules Check
- After updates install, setup verifies again.  
- Click **Next** when all checks are passed.

---

### 9. Select Installation Type
- Choose **SQL Server Feature Installation**.
- Click **Next**.

---

### 10. Select BI Components
Select the following features:
- **Database Engine Services**  
- **Analysis Services (SSAS)**  
- **Reporting Services (SSRS)**  
- **Integration Services (SSIS)**  
- **SQL Server Data Tools (BI Tools)**  
- **Management Tools (SSMS)**  

Click **Next**.

---

### 11. Installation Rules
- Setup checks system compatibility.  
- Click **Next** once all rules pass.

---

### 12. Instance Configuration
Choose:
- **Default Instance** (if no SQL Server is installed)  
or  
- **Named Instance** (e.g., MSSQLSERVER2)

Click **Next**.

---

### 13. Disk Space Summary
- Review required disk space.  
- Click **Next**.

---

### 14. Server Configuration
- For each service (SQL Engine, SSIS, SSAS, SSRS):
  - Startup Type: **Automatic**
- Keep default service accounts or enter specific ones if required.
- Click **Next**.

---

### 15. Database Engine Configuration
- Choose **Mixed Mode Authentication (SQL + Windows)**.  
- Set **sa password**.  
- Add current user as SQL Administrator.
- Specify directories if needed.
- Click **Next**.

---

### 16. Analysis Services Configuration
- Choose **Multidimensional and Data Mining Mode**.
- Add current user as Administrator.
- Verify data directories.
- Click **Next**.

---

### 17. Reporting Services Configuration
- Select **Install and configure**.
- Click **Next**.

---

### 18. Distributed Replay Setup (if features selected)
- Add users for controller access.
- Configure client working and result directories.
- Click **Next**.

---

### 19. Error Reporting
- Choose whether to send error reports.
- Click **Next**.

---

### 20. Final Installation Rules Check
- Setup validates everything.  
- Click **Next** when all checks pass.

---

### 21. Review Installation Summary
- Confirm selected features and configurations.
- Click **Install**.

---

### 22. Installation Progress
- Monitor progress until all components show **Succeeded**.

---

### 23. Complete Installation
- View summary.  
- Close setup.

---

### 24. Verification
- Open **SQL Server Management Studio (SSMS)**.  
- Connect to the SQL instance.  
- Verify availability of:
  - Database Engine  
  - SSIS  
  - SSAS  
  - SSRS  
  - SQL Server Data Tools  

---

