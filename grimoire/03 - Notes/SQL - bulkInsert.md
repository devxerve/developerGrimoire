---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Bulk Insert 


```sql cpp title:"enviromentalVariables"
SET SQL_SAFE_UPDATES = 0;
SHOW VARIABLES LIKE 'secure_file_priv';
```

```sql cpp title:"plaint_TextFile_insertion"
LOAD DATA INFILE "C:\\ProgramData\\MySQL\\MySQL Server 8.0\\Uploads\\students.txt"
REPLACE 
INTO TABLE student
FIELDS TERMINATED BY "\t"
IGNORE 2 LINES;
```

```sql title="XML_Insertion"
LOAD XML INFILE "C:\\ProgramData\\MySQL\\MySQL Server 8.0\\Uploads\\student.xml"
REPLACE 
INTO TABLE student
ROWS IDENTIFIED BY "<row>";
```
