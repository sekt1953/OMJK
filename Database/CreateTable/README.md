# Create Table

## Kilde

* w3schools
  * [SQL Tutorial](https://www.w3schools.com/sql/default.asp)
  * [MySQL SQL](https://www.w3schools.com/mysql/mysql_sql.asp)

## Create help tables from DriftMateriale table with SQL

* Create Table for MatrialeType

```sql
CREATE TABLE "MatrialeType" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Type" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO MatrialeType (Type) SELECT DISTINCT Type FROM DriftMateriale WHERE "Type" IS NOT NULL;
```

* Create Table for Bane

```sql
CREATE TABLE "BaneType" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Bane" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO BaneType (Bane) SELECT DISTINCT Bane FROM DriftMateriale WHERE "Bane" IS NOT NULL;
```

* Create Table for Litra

```sql
CREATE TABLE "LitraType" (
"ID" INT NOT NULL AUTO_INCREMENT,
"Litra" VARCHAR(50),
"Beskrivelse" VARCHAR(50),
PRIMARY KEY (ID)
);

INSERT INTO LitraType (Litra) SELECT DISTINCT Litra FROM DriftMateriale WHERE "Litra" IS NOT NULL;
```

* Create Table for Hjemsted

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
