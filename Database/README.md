# DataBase Project

## Kilder:

* Link til Videoer
  * [ExplainingComputers](https://www.youtube.com/@ExplainingComputers)
    * [Introduction to Databases: LibreOffice Base Tutorial](https://youtu.be/lhRJFgDG-5o)
  * [Sean Johnson](https://www.youtube.com/@BusinessProgrammer)
    * [LibreOffice Base Database Tutorial](https://youtu.be/Du1WjROQBpE)
    * [LibreOffice Base Split Database Tutorial](https://youtu.be/BwrWoP0Wr7w)
  * [TheFrugalComputerGuy](https://www.youtube.com/@TheFrugalComputerGuy)
    * [LibreOffice Base](https://www.youtube.com/playlist?list=PLy7Kah3WzqrEerJ0VPNWVaR4CYHMr4wmV)
  * [Setting Up a Dedicated Database Server on Raspberry Pi](https://dzone.com/articles/set-up-a-dedicated-database-server-on-raspberry)
  * [Setup a Raspberry Pi MYSQL Database](https://pimylifeup.com/raspberry-pi-mysql/)
  * [How To Allow Remote Access to MySQL](https://www.digitalocean.com/community/tutorials/how-to-allow-remote-access-to-mysql)

## Regneark

* [Orginal regneark DriftMateriale.ods](./OrgData/DriftMateriale.ods)

##  DataBase Test

* [OMJK_001](./OMJK_001.odb)
* [SQL script](./sql.txt)

## LibreOffice-Base & Raspberry pi 4 med mariade SQL-server

### LibreOffice

Brug [LibreOffice 7.6.4](https://www.libreoffice.org/download/download-libreoffice/) eller nyere

### Raspberry pi OS

Brug Raspberry Pi OS Lite (64bit) eller Raspberry Pi OS Full (64bit), 

* Install med Raspberry Pi Imager
  * Select Raspberry Pi OS (other) 
    * Raspberry Pi OS Lite (64bit) eller Raspberry Pi OS Full (64bit)
  * Select Storage Device
  * Select Image customization options
    * set hostname: mysqlpc
    * Enable SSH
      * Use password authentication
    * Set Username and password
    * Configure wireless LAN
  * Save
  * WRITE

### Setup a Raspberry Pi  Mariadb Database

#### SSH to Database server

```code
SSH omjk@mysqlpc.local
```

```code
sudo apt update && sudo apt upgrade
```

```code
sudo apt install mariadb-server
```

```code
sudo mysql_secure_installation
```

```code
sudo mysql -u root -p
```

To exit MySQL type " quit;" or Press [CTRL] + [D]

### Creating a MySQL Database and User

```code
sudo mysql -u root -p
```

```code
CREATE DATABASE exampledb;
```

```code
CREATE USER 'exampleuser'@'localhost' IDENTIFIED BY 'pimylifeup';
```

```code
GRANT ALL PRIVILEGES ON exampledb.* TO 'exampleuser'@'localhost';
```

```code
FLUSH PRIVILEGES;
```

```code
```

To exit MySQL type " quit;" or Press [CTRL] + [D]

### Create Remote User

```code
sudo mysql -u root -p
```

```code
CREATE USER 'remoteuser'@'%' IDENTIFIED BY 'pimylifeup';
```

```code
GRANT ALL PRIVILEGES ON exampledb.* TO 'remoteuser'@'%';
```

```code
FLUSH PRIVILEGES;
```

To exit MySQL type " quit;" or Press [CTRL] + [D]

```code
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```

```code
bind-address=0.0.0.0
```

[CTRL]+[o], [ENTER] [CTRL]+[x]

```code
service mysql restart
```

### Test Remote User

#### Open terminal på Remote  PC

Install Mariadb client:

```code
  sudo apt install mariadb-client-core-10.6 
```

Test conection:

```code
mysql -u remoteuser -p -h 192.168.0.8 -P 3306
```

```code
SHOW DATABASES;
```

Svar se ud som dette:

```code
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| exampledb          |
| information_schema |
+--------------------+
2 rows in set (0,002 sec)
```

To exit MySQL type " quit;" or Press [CTRL] + [D]

### LibreOffice-Base

* Select database
  * Connect to an existing database
    * MySQL/MariaDB
  * [Next]
    * Connect directly (using MariaDB C connector)
  * [Next]
    * Database name: exampledb
    * Server: mysqlpc.local
    * Port: 3306
  * [Next]
    * User name: remoteuser
    * Password required
    * [Test Connection]
      * Password: pimylifeup
      * [OK]
      * If OK then [Next]
  * Save and proceed
    * Yes, register the database in LibreOffice
    * Open the database for editing
  * [Finish]
