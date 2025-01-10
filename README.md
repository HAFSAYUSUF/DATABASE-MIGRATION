Name: HAFSA Y COMPANY:CODETECH IT SOLUTIONS DOMAIN:SQL DURATION:DECEMBER TO JANUARY
# DATABASE-MIGRATION

Here’s a **README.md** file tailored for GitHub submission:

---

### **README.md**

```markdown
# **MySQL to PostgreSQL Data Migration**

This project demonstrates the process of migrating data from a MySQL database to a PostgreSQL database while ensuring data integrity. The deliverables include migration scripts and a detailed summary report.

---

## **Deliverables**

1. **Migration Scripts**:  
   Contains SQL scripts for both MySQL and PostgreSQL databases.
   
2. **Summary Report**:  
   A detailed explanation of the migration process, including steps, challenges, and results.

---

## **Project Overview**

### **1. MySQL Script**

The MySQL script contains table creation and data insertion commands for the initial MySQL database.

### **2. PostgreSQL Script**

The PostgreSQL script is a modified version of the MySQL script, ensuring compatibility with PostgreSQL syntax and features.

### **3. Summary Report**

The summary report explains the following:
- Steps taken to export the MySQL database.
- Modifications made to ensure PostgreSQL compatibility.
- Steps to import the modified script into PostgreSQL.
- Verification of data integrity.

---

## **Steps to Run the Migration**

### **Prerequisites**

Ensure you have the following installed on your system:
- **MySQL Server** and **MySQL Client**
- **PostgreSQL Server** and **psql Client**
- Command-line tools: `mysqldump`, `psql`

### **Step 1: Export MySQL Database**

Run the following command to export your MySQL database:

mysqldump -u [username] -p sample_db > sample_db.sql


### **Step 2: Modify SQL Script for PostgreSQL**

Make the following changes to the exported SQL file:
- Replace `AUTO_INCREMENT` with `SERIAL`.
- Change data types where necessary (e.g., `VARCHAR`, `TEXT`, `INT`).
- Remove backticks (`) and use double quotes for identifiers.

Save the modified script as `migrate.sql`.

### **Step 3: Import into PostgreSQL**

1. Create a new database in PostgreSQL:
   ```sql
   CREATE DATABASE sample_db_pg;
   ```

2. Import the modified script:
  
   psql -U [username] -d sample_db_pg -f migrate.sql


### **Step 4: Verify the Migration**

1. Query the PostgreSQL database to ensure that the data was migrated correctly:
 
   SELECT * FROM users;

2. Check the row count and structure of the tables.

---

## **Files in This Repository**

1. **`mysql_script.sql`**  
   SQL script for creating and populating the MySQL database.

2. **`migrate.sql`**  
   Modified SQL script compatible with PostgreSQL.

3. **`SUMMARY_REPORT.md`**  
   Detailed summary report of the migration process.

4. **`README.md`**  
   This file, providing an overview of the project and instructions for running the migration.

---

## **Results**

- Data was successfully migrated from MySQL to PostgreSQL.
- All integrity checks were performed, ensuring no loss or corruption of data.
- See the `SUMMARY_REPORT.md` for more details on the process and results.

