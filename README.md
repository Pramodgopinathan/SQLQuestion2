### Create some random tables as customer which have ownership%
```SQL
CREATE TABLE Customer (id INTEGER , name TEXT, product TEXT, 
OwnershipPercentage numeric(4,3) , Effective_date numeric);
INSERT INTO Customer VALUES (1, "BankA", "A01", 25, 20180223) ;
INSERT INTO Customer VALUES (1, "BankA","A02", 28, 20181224) ;
INSERT INTO Customer VALUES (2, "BankB", "B01", 89, 20190101) ;
INSERT INTO Customer VALUES (2, "BankB", "B02", 35, 20200101) ;
```

```SQL
SELECT COUNT(*)
FROM Customer
```
Count(*): Returns total number of records .i.e 4 <br />
Count(product): Return number of Non Null values over the column salary. i.e 4. <br />
Count(Distinct name):  Return number of distinct Non Null values over the column name.i.e 4 <br />

