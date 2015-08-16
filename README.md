# slick-for-production

This is sbt project. You need to install [sbt](http://www.scala-sbt.org/) if you dont have.

Clone project

```$ git clone https://github.com/satendrakumar06/slick-for-production.git```

```$ cd slick-for-production```

```$ sbt clean compile```

Run unit test:

``` $ sbt test ```

Unit tests have used h2 database.If you want run demo app so you need to create database in MySQL.

Follow these steps:

login into mysql server then:

```mysql> create database bank_db;```

```mysql> use bank_db;```

```mysql> CREATE TABLE bank(id int PRIMARY KEY auto_increment,name varchar(200));```

```mysql>CREATE TABLE bankinfo(id int PRIMARY KEY auto_increment,owner varchar(200),bank_id int references bank(id),branches int );```

```mysql> CREATE TABLE bankproduct(id int PRIMARY KEY auto_increment,name varchar(200),bank_id int references bank(id));```

Now you can run app:

```$ sbt run ```
you will see this outut

```info] Running com.knol.db.Demo 
[INFO] - [2015-08-16 18:42:25,070] - [com.zaxxer.hikari.HikariDataSource]  HikariCP pool mysql is starting.
List((Bank(ICICI bank,Some(1)),Some(BankInfo(Goverment,1000,1,Some(1)))), (Bank(SBI Bank,Some(2)),None))
List((Bank(ICICI bank,Some(1)),Some(BankProduct(car loan,1,Some(1)))), (Bank(SBI Bank,Some(2)),None))```
