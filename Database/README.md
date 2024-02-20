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

## Regneark

* [Orginal regneark DriftMateriale.ods](./OrgData/DriftMateriale.ods)

## DataBase Test

* [OMJK_001](./OMJK_001.odb)
* [SQL script](./sql.txt)

## Raspberry Pi MYSQL Database

### Setup a Raspberry Pi MYSQL Database

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
quit;
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
quit;
```

### Create Remote User

```code
sudo mysql -u root -p
```

```code
CREATE USER 'remoteuser'@'%' IDENTIFIED BY 'pimylifeup';
```

```code
FLUSH PRIVILEGES;
```

```code
quit;
```

```code
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```

```code
bind-address=0.0.0.0
```

[CTRL]+[o], [ENTER] [CTRL]+[x]

### Test Remote User:

```code
mysql -u remoteuser -p -h 192.168.0.8 -P 3306
```
