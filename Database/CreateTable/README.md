# Create Table

## Kilde

* Video
  * [ExplainingComputers](https://www.youtube.com/@ExplainingComputers)
    * [Introduction to Databases: LibreOffice Base Tutorial](https://youtu.be/lhRJFgDG-5o)
  * [Sean Johnson](https://www.youtube.com/@BusinessProgrammer)
    * [LibreOffice Base Database Tutorial](https://youtu.be/Du1WjROQBpE)
    * [LibreOffice Base Split Database Tutorial](https://youtu.be/BwrWoP0Wr7w)
  * [TheFrugalComputerGuy](https://www.youtube.com/@TheFrugalComputerGuy)
    * [LibreOffice Base](https://www.youtube.com/playlist?list=PLy7Kah3WzqrEerJ0VPNWVaR4CYHMr4wmV)
* [w3schools](https://www.w3schools.com)
  * [SQL Tutorial](https://www.w3schools.com/sql/default.asp)
  * [MySQL SQL (MariaDB )](https://www.w3schools.com/mysql/mysql_sql.asp)

## Orginale Data

* Regneark:
  * [Orginal regneark DriftMateriale.ods](../OrgData/DriftMateriale.ods)
* Foto:
* Hjulby:
  * [Klemrække](../OrgData/Hjulby/)
    * [Hjulby_Klemrække_A.pdf](../OrgData/Hjulby/Hjulby_Klemrække_A.pdf)
    * [Hjulby_Klemrække_B.pdf](../OrgData/Hjulby/Hjulby_Klemrække_B.pdf)
    * [Hjulby_Klemrække_C.pdf](../OrgData/Hjulby/Hjulby_Klemrække_C.pdf)
    * [Hjulby_Klemrække_D.pdf](../OrgData/Hjulby/Hjulby_Klemrække_D.pdf)
    * [Hjulby_Klemrække_E.pdf](../OrgData/Hjulby/Hjulby_Klemrække_E.pdf)
  * [Regneark]
    * [Pult_Hjulby_Klemrække_A.ods](../OrgData/Hjulby/Pult_Hjulby_Klemrække_A.ods)
  * [Sporplan](../OrgData/Hjulby/)
    * [Hjulby_Sporplan_1af3.pdf](../OrgData/Hjulby/Hjulby_Sporplan_1af3.pdf)
    * [Hjulby_Sporplan_2af3.pdf](../OrgData/Hjulby/Hjulby_Sporplan_2af3.pdf)
    * [Hjulby_Sporplan_3af3.pdf](../OrgData/Hjulby/Hjulby_Sporplan_3af3.pdf)

## Create Member List from Google Contact

### 1. Create Member CSV file from Google Contact

* Åben Google contact
  * Select Etikette du ønsker at Eksportèr
  * Click Eksportèr
    * Eksportér kontakter som: Google CSV
    * Save File

### 2. Open CSV-file with LibreOffice Calc

* Åben contacts.csv LibreOffice Calc
  * Brug default settings
  * Click [OK]
  * Select kolonner du ønsker at bruge:
    * Given Name, Family Name
  * Højre klik og select Copy

### 3. Create members table

* Åben DataBase
  * Select Table
    * Højre klik i Tables
    * Vælg Paste
    * Copy Table:
      * Table name: exampledb.Medlemmer
      * Options:
        * Definition and data
        * Use first line as column names
        * Create new fiels as primary key
          * Name: ID
      * Klik [Next]
      * Select Columns:
        * Given Name, Family Name
      * Klik [Next]
      * Klik [Create]
      * Save

## Create DriftMateriale from spreadsheet

### 1. Open CSV-file with LibreOffice Calc

* Åben DriftMateriale.csv LibreOffice Calc
  * Brug default settings
  * Click [OK]
  * Select kolonner:
    * A til M
  * Højre klik og select Copy

### 2. Create DriftMateriale table

* Åben DataBase
  * Select Table
    * Højre klik i Tables
    * Vælg Paste
    * Copy Table:
      * Table name: exampledb.DriftMateriale
      * Options:
        * Definition and data
        * Use first line as column names
        * Create new fiels as primary key
          * Name: ID
      * Klik [Next]
      * Select Columns: Alle
      * Klik [Next]
      * Klik [Create]
      * Save

## Create help tables from DriftMateriale table with SQL

### Create Table for MatrialeType

```sql
CREATE TABLE "MatrialeType" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Type" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO MatrialeType (Type) SELECT DISTINCT Type FROM DriftMateriale WHERE "Type" IS NOT NULL;
```

### Create Table for Bane

```sql
CREATE TABLE "BaneType" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Bane" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO BaneType (Bane) SELECT DISTINCT Bane FROM DriftMateriale WHERE "Bane" IS NOT NULL;
```

### Create Table for Litra

```sql
CREATE TABLE "LitraType" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Litra" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO LitraType (Litra) SELECT DISTINCT Litra FROM DriftMateriale WHERE "Litra" IS NOT NULL;
```

### Create Table for Hjemsted

```sql
CREATE TABLE "Hjemsted" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Hjemsted" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO Hjemsted (Hjemsted) SELECT DISTINCT Hjemsted FROM DriftMateriale WHERE "Hjemsted" IS NOT NULL;
```

```sql

```
