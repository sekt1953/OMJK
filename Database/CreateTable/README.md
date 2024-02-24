# Create Table

## Create new tables with SQL interface

* Create Table for MatrialeType
  * click: Tools->SQL

```sql
CREATE TABLE "MatrialeType" (
"ID" INT PRIMARY KEY,
"Type" VARCHAR(50),
"Beskrivelse" VARCHAR(50)
);
```

* Run SQL
  * Check: Run SQL command directly
  * Check: Show output of "select" statements
  * Click: [Execute]
* Refresh Table
  * Click: View->Refresh Tables
* Edit Table ID Field
  * Right-Click: Table (MatrialeType)
    * Select: Edit
    * Set: ID Field Properties to
      * AutoValue: Yes
      * Length: 10
    * Save  
* Insert Data from DriftMateriale :

```sql
INSERT INTO MatrialeType (Type) SELECT DISTINCT Type FROM DriftMateriale WHERE "Type" IS NOT NULL;
```

* Create Table for Bane

```sql
CREATE TABLE "BaneType" (
"ID" INT PRIMARY KEY,
"Bane" VARCHAR(50),
"Beskrivelse" VARCHAR(50)
);
```

```sql
INSERT INTO BaneType (Bane) SELECT DISTINCT Bane FROM DriftMateriale WHERE "Bane" IS NOT NULL;
```

* Create Table for Litra

```sql
CREATE TABLE "LitraType" (
"ID" INT PRIMARY KEY,
"Litra" VARCHAR(50),
"Beskrivelse" VARCHAR(50)
);
```

```sql
INSERT INTO LitraType (Litra) SELECT DISTINCT Litra FROM DriftMateriale WHERE "Litra" IS NOT NULL;
```

* Create Table for Hjemsted

```sql
CREATE TABLE "Hjemsted" (
"ID" INT PRIMARY KEY,
"Hjemsted" VARCHAR(50),
"Beskrivelse" VARCHAR(50)
);
```

```sql
INSERT INTO Hjemsted (Hjemsted) SELECT DISTINCT Hjemsted FROM DriftMateriale WHERE "Hjemsted" IS NOT NULL;
```

```sql

```
