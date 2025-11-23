## Experiment No. 6  
### Title: Demonstration of Lookup Data Transformation in SSIS

---

## Step-by-Step Procedure

### 1. Create Source and Destination Tables
- Create **dbo.books** table with BookID, Book Title, Book Price.  
- Insert initial 6 records.  
- Create **dbo.bookshistory** table with same structure (empty).

---

## Condition 1: Insert All Records (Initial Load)

### 2. Create New SSIS Package
- Open SSDT → New Integration Services Project.  
- Drag **Data Flow Task** to Control Flow.  
- Rename it “SSIS Lookup Transformation”.  
- Open Data Flow pane.

### 3. Configure OLE DB Source
- Drag **OLE DB Source** → configure connection to books table.  
- Select books as source.  
- Rename to **SourceData**.

### 4. Add Lookup Transformation
- Drag **Lookup** → connect SourceData to Lookup.  
- Edit Lookup Transformation:  
  - Connection: same database  
  - Set **“Redirect rows to no match output”**

### 5. Configure Lookup Mapping
- Set destination table = bookshistory.  
- In Columns tab → map BookID (source → destination).

### 6. Configure OLE DB Destination
- Drag **OLE DB Destination**.  
- Connect Lookup → select **Lookup No Match Output**.  
- Map all fields.  
- Run the package → inserts all 6 rows.

---

## Condition 2: Insert Only New Records

### 7. Add New Record in Source
- Insert a new record (BookID 7) into books table.

### 8. Re-run Package
- Lookup compares source vs destination.  
- Only unmatched record (BookID 7) is inserted.  
- No duplicates created.

---

## Condition 3: Update Changed Records

### 9. Modify Source Record
- Update Book Price for BookID 1 in books table.

### 10. Add OLE DB Command for Updates
- Drag **OLE DB Command**.  
- Connect **Lookup Match Output** to this task.  
- Create stored procedure to update bookshistory.  
- In OLE DB Command:
  - SQL Command: `EXEC Update_bookshistory ?,?,?`  
  - Map parameters (BookID, Book Title, Book Price)

### 11. Run Package
- SSIS updates BookID 1 in bookshistory.  
- Only the modified row is updated.

---

## Condition 3 (Improved): Update Only Relevant Rows

### 12. Add Second Lookup Component
- Drag another **Lookup** component.  
- Connect from Lookup Match Output.  
- Set again: **Redirect rows to no match output**

### 13. Configure Second Lookup
- Destination table: bookshistory  
- Map BookID, Book Title, Book Price  
- This Lookup detects *changed rows only*.

### 14. Connect to OLE DB Command
- Connect Lookup2 **No Match Output** → OLE DB Command.  
- This ensures only changed rows flow to update.

### 15. Run Package
- Only the changed BookID is updated.  
- No extra rows processed.

---

## Final Test (Insert + Update Together)

### 16. Update & Insert in Source
- Update BookID 2.  
- Insert BookID 8.

### 17. Run Package
- Lookup identifies:  
  - One new row (8) → inserted  
  - One changed row (2) → updated  
- Validate results in bookshistory.

---

