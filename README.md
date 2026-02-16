# oracle_pdb_ass_II_29588_CELINE

Repository Link: [GitHub URL](https://github.com/umunyanaceline/oracle_pdb_ass_II_29588_CELINE)\
PDB Name Created: ce_pdb_29588\
Issues Encountered: No


ASSIGNMENT 2

This assignment is divided into three major components. First, it involves creating a permanent Pluggable Database (PDB). Second, it requires setting up a temporary PDB. Both of these tasks must be completed using Oracle SQL*Plus as the primary command-line tool. Finally, the assignment also includes using Oracle Enterprise Manager to perform database administration and management activities.


## System Environment Configuration

The following platforms and tools were used during the completion of this assignment:

| Component            | Specification / Version        |
|----------------------|---------------------------------|
| Operating System     | Windows 11 (64-bit)             |
| Database Software    | Oracle Database 21c             |
| Command-Line Tool    | Windows PowerShell              |
| Web Browser          | Firefox Developer Edition       |

These resources formed the technical environment required for creating, configuring, and managing the database system.

### Task 1: Establishing a New Pluggable Database  

In this section of the assignment, a permanent Pluggable Database (PDB) named **ob_pdb_29699** was successfully created. 

The SQL commands shown below were executed to accomplish the database creation process:
```sql
DATABASE ce_pdb_29588
 ADMIN CELINE\DOWNLOADS\ORAUSER celine_plsqlauca_29588 IDENTIFIED BY admin
FILE_NAME_CONVERT = (
    'C:\USERS\DATA\ORCL\pdbseed',
    'C:\USERS\CELINE\DOWNLOADS\ORA Create pluggable database
CREATE PLUGGABLEDATA\ORCL\ce_pdb_29588'
    );

-- Open pluggable database
ALTER PLUGGABLE DATABASE ce_pdb_29588 OPEN;

-- Save the pdb state
ALTER PLUGGABLE DATABASE ce_pdb_29588 SAVE STATE;
```

![T1](https://github.com/user-attachments/assets/d7a2fe90-ce04-4844-9e67-379ade8ea588)

```sql
-- Check pluggable database creation and status
SELECT pdb_name, status
FROM dba_pdbs;

```



![T1 VE](https://github.com/user-attachments/assets/3a2c5779-8808-4e65-87ea-679d8724124c)


### Task 2: Create and Drop a Pluggable Database  

In this task, a temporary Pluggable Database (PDB) named **ce_to_delete_pdb_29588** was created. After checking that it was created successfully, the database was deleted.  

The SQL commands below were used to complete these steps:

```sql
CREATE PLUGGABLE DATABASE ce_to_delete_pdb_29588
ADMIN USER celine_to_deleteplsqlauca_29588 IDENTIFIED BY admin
FILE_NAME_CONVERT = (
    'C:\USERS\CELINE\DOWNLOADS\ORADATA\ORCL\pdbseed',
    'C:\USERS\CELINE\DOWNLOADS\ORADATA\ORCL\ce_to_delete_pdb_29588'
    );

SELECT pdb_name
FROM dba_pdbs;

DROP PLUGGABLE DATABASE ce_to_delete_pdb_29588 INCLUDING DATAFILES;

SELECT pdb_name
FROM dba_pdbs
WHERE pdb_name = 'CE_TO_DELETE_PDB_29588';
```

![Q2 A](https://github.com/user-attachments/assets/8bdcaf99-659e-409f-9ae3-4bbafe61ef6d)


![Q2 B](https://github.com/user-attachments/assets/6da8a43f-7c1c-4a1a-a0dc-bb847f2d3715)


### Task 3: Oracle Enterprise Manager (OEM)

In this task, Oracle Enterprise Manager (OEM) was used to view and manage the pluggable databases through a graphical interface. The screenshots show the database activities and performance details that can be checked and monitored using OEM.


![Q3](https://github.com/user-attachments/assets/670e0311-8935-4e9d-95ca-a9ae83cadf4c)
![Q3 B](https://github.com/user-attachments/assets/39ffd656-7a5f-4bb5-911f-999248942aa7)
![Q3C](https://github.com/user-attachments/assets/050774ab-6511-44e8-8834-853cfc26c448)


### References  
- Pluggable Databases Guide  
- Oracle Enterprise Manager Guide  

### Academic Honesty  
All sources are properly cited.  
Work and analysis are fully my own.  
No AI content was copied; any help was rewritten in my own words.












