## Experiment No. 4  
### Title: Study and Analyze Dimensional Models for Different Application Domains

---

## Step-by-Step Procedure

### 1. Select an Application Domain
- Open the PDF **“Dimensional_Modelling_by_Example”**.  
- Choose a domain (e.g., Sales, Banking, Retail, Healthcare, Telecom, Insurance).

---

### 2. Identify the Business Process
- Read the ER model / case description from the PDF.  
- Determine the core business event the system is tracking  
  (example: Sales Transaction, Claims Processing, Order Shipment, Patient Visit).

---

### 3. Identify the Grain
- Define the lowest level of detail to be stored in the fact table.  
- Examples:
  - Sales: one row per product per transaction  
  - Healthcare: one row per patient visit  
  - Telecom: one row per call per customer  

---

### 4. Identify All Dimensions
- List all nouns from the model such as:
  - Date  
  - Customer  
  - Product  
  - Store / Branch / Location  
  - Employee  
  - Channel  
- For each dimension:
  - Identify attributes  
  - Identify hierarchies (City → State → Country, Year → Quarter → Month → Day)

---

### 5. Identify the Fact Table
- Determine the numeric measurements required for analysis.
- Examples:
  - Sales Amount  
  - Quantity  
  - Discount  
  - Premium Amount  
  - Claim Cost  
  - Duration / Call Minutes  
- Specify foreign keys connecting to all dimensions.  

---

### 6. Identify the Type of Fact Table
Use the definitions to classify:
- **Additive Facts** → can be summed across all dimensions (Sales, Quantity)  
- **Semi-Additive Facts** → can be summed only across some dimensions (Account Balance)  
- **Non-Additive Facts** → cannot be summed (Ratios, Percentages)

---

### 7. Identify the Type of Dimensions
From the dimension list, classify each as:
- **Conformed Dimension** (shared across multiple fact tables)  
- **Role-Playing Dimension** (same table used in multiple roles — e.g., Order Date, Ship Date)  
- **Degenerate Dimension** (no attributes — invoice number, transaction ID)  
- **Junk Dimension** (codes, flags combined into one table)  
- **Shrunken Dimension** (subset for aggregated tables)  
- **Outrigger Dimension** (dimension referencing another dimension)

---

### 8. Draw the Dimensional Model (Star Schema)
- Place the Fact Table in the center.  
- Connect all Dimension Tables around it using foreign keys.  
- Ensure all dimensions are denormalized.

---

### 9. Validate the Model
Check that:
- Grain is consistent across all facts.  
- Each fact is linked to all required dimensions.  
- Dimensions contain complete hierarchies.  
- No unnecessary normalization exists.

---

### 10. Document Final Output
For the selected application domain, write:
- Business Process  
- Grain  
- Fact Table + type of facts  
- Dimension Tables + type of each dimension  
- Star Schema diagram (hand-drawn or digital)

