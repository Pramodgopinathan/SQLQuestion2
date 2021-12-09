### Create some random tables as customer which have ownership%
```SQL
CREATE TABLE Customer (id INTEGER , name TEXT, product TEXT, 
OwnershipPercentage numeric(4,3) , Effective_date numeric);
INSERT INTO Customer VALUES (1, "BankA", "A01", 25, 20180223) ;
INSERT INTO Customer VALUES (1, "BankA","A02", 28, 20181224) ;
INSERT INTO Customer VALUES (2, "BankB", "B01", 89, 20190101) ;
INSERT INTO Customer VALUES (2, "BankB", "B02", 35, 20200101) ;
```

### COUNT 

```SQL
SELECT COUNT(*)
FROM Customer
```
Count(*): Returns total number of records .i.e 4 <br />
Count(product): Return number of Non Null values over the column salary. i.e 4. <br />
Count(Distinct name):  Return number of distinct Non Null values over the column name.i.e 4 <br />

### SUM

```SQL
SELECT SUM(OwnershipPercentage)
FROM Customer
```

sum(OwnershipPercentage):  Sum all Non Null values of Column salary i.e., 177 <br />
sum(Distinct OwnershipPercentage): Sum of all distinct Non-Null values i.e., 177

### AVG

```SQL
SELECT AVG(OwnershipPercentage)
FROM Customer
```


Avg(OwnershipPercentage) = Sum(OwnershipPercentage) / count(OwnershipPercentage) = 44.25 <br />
Avg(Distinct OwnershipPercentage) = sum(Distinct OwnershipPercentage) / Count(Distinct OwnershipPercentage) = 44.25 <br />

### MIN & MAX


```SQL
SELECT MIN(OwnershipPercentage)
FROM Customer

SELECT MAX(OwnershipPercentage)
FROM Customer

```

Min(salary): Minimum value in the salary column except NULL i.e., 25. <br />
Max(salary): Maximum value in the salary i.e., 86.


```SQL

CREATE TABLE customers
( customer_id int NOT NULL,
  last_name char(50) NOT NULL,
  first_name char(50) NOT NULL,
  favorite_website char(50),
  CONSTRAINT customers_pk PRIMARY KEY (customer_id)
);
  
CREATE TABLE orders
( order_id int NOT NULL,
  customer_id int,
  order_date date,
  CONSTRAINT orders_pk PRIMARY KEY (order_id)
);

```

```SQL
INSERT INTO customers
(customer_id, last_name, first_name, favorite_website)
VALUES
(4000, 'Jackson', 'Joe', 'techonthenet.com');

INSERT INTO customers
(customer_id, last_name, first_name, favorite_website)
VALUES
(5000, 'Smith', 'Jane', 'digminecraft.com');

INSERT INTO customers
(customer_id, last_name, first_name, favorite_website)
VALUES
(6000, 'Ferguson', 'Samantha', 'bigactivities.com');

INSERT INTO customers
(customer_id, last_name, first_name, favorite_website)
VALUES
(7000, 'Reynolds', 'Allen', 'checkyourmath.com');

INSERT INTO customers
(customer_id, last_name, first_name, favorite_website)
VALUES
(8000, 'Anderson', 'Paige', NULL);

INSERT INTO customers
(customer_id, last_name, first_name, favorite_website)
VALUES
(9000, 'Johnson', 'Derek', 'techonthenet.com');


INSERT INTO orders
(order_id, customer_id, order_date)
VALUES
(1,7000,'2016/04/18');

INSERT INTO orders
(order_id, customer_id, order_date)
VALUES
(2,5000,'2016/04/18');

INSERT INTO orders
(order_id, customer_id, order_date)
VALUES
(3,8000,'2016/04/19');

INSERT INTO orders
(order_id, customer_id, order_date)
VALUES
(4,4000,'2016/04/20');

INSERT INTO orders
(order_id, customer_id, order_date)
VALUES
(5,null,'2016/05/01');

```
### SQL INNER JOIN (simple join)

![](https://github.com/Pramodgopinathan/SQLQuestion2/blob/2a888bc967e6558e9d6635ef4f6f8450807eca46/inner_join.gif)

```SQL
SELECT customers.customer_id, orders.order_id, orders.order_date
FROM customers 
INNER JOIN orders
ON customers.customer_id = orders.customer_id
ORDER BY customers.customer_id;
```


### SQL LEFT OUTER JOIN

![](https://github.com/Pramodgopinathan/SQLQuestion2/blob/beb787840bd694bc1c1a5be539b495aded7974e8/left_outer_join.gif)

```SQL
SELECT customers.customer_id, orders.order_id, orders.order_date
FROM customers 
LEFT OUTER JOIN orders
ON customers.customer_id = orders.customer_id
ORDER BY customers.customer_id;
```
### SQL RIGHT OUTER JOIN

![](https://github.com/Pramodgopinathan/SQLQuestion2/blob/beb787840bd694bc1c1a5be539b495aded7974e8/right_outer_join.gif)

```SQL
SELECT customers.customer_id, orders.order_id, orders.order_date
FROM customers 
RIGHT OUTER JOIN orders
ON customers.customer_id = orders.customer_id
ORDER BY customers.customer_id;
```

### SQL FULL OUTER JOIN

![](https://github.com/Pramodgopinathan/SQLQuestion2/blob/beb787840bd694bc1c1a5be539b495aded7974e8/full_outer_join.gif)

```SQL
SELECT customers.customer_id, orders.order_id, orders.order_date
FROM customers 
FULL OUTER JOIN orders
ON customers.customer_id = orders.customer_id
ORDER BY customers.customer_id;
```
