// SELECT

# Insert the missing statement to get all the columns from the Customers table.
SELECT * FROM Customers;

# Write a statement that will select the City column from the Customers table.
SELECT City FROM Customers;

# Select all the different values from the Country column in the Customers table.
SELECT DISTINCT Country FROM Customers;

// WHERE

# Select all records where the City column has the value "Berlin".
SELECT * FROM Customers 
WHERE City = 'Berlin' ;

# Select all records where the City column is NOT the value "Berlin".
SELECT * FROM Customers 
WHERE City <> ' Berlin ';

# Select all records where the CustomerID column has the value 32.
SELECT * FROM Customers 
WHERE CustomerID = 32 ;

# Select all records where the City column has the value 'Berlin' and the PostalCode column has the value 12209.
SELECT * FROM Customers 
WHERE City = 'Berlin' 
AND PostalCode = 12209;

# Select all records where the City column has the value 'Berlin', and also the records where the City column has the value 'London'.
SELECT * FROM Customers 
WHERE City = 'Berlin' 
OR City = ' London ';

// ORDER BY

# Select all records from the Customers table, sort the result alphabetically by the column City.
SELECT * FROM Customers ORDER BY City ;

# Select all records from the Customers table, sort the result reversed alphabetically by the column City.
SELECT * FROM Customers ORDER BY City DESC ;

# Select all records from the Customers table, sort the result alphabetically, first by the column Country, then, by the column City.
SELECT * ORDER 
BY Customers ORDER BY Country, City ;

// INSERT

# Insert a new record in the Customers table.

INSERT INTO Customers (
CustomerName, 
Address, 
City, 
PostalCode,
Country)
VALUES(
'Hekkan Burger',
'Gateveien 15',
'Sandnes',
'4306',
'Norway');

// NULL 
# Select all records from the Customers where the PostalCode column is empty.
SELECT * FROM Customers 
WHERE PostalCode IS NULL ;

#Select all records from the Customers where the PostalCode column is NOT empty.
SELECT * FROM Customers WHERE PostalCode IS NOT NULL ;

// UPDATE
# Update the City column of all records in the Customers table.
UPDATE Customers 
SET City = 'Oslo';

# Set the value of the City columns to 'Oslo', but only the ones where the Country column has the value "Norway".

UPDATE Customers 
SET City = 'Oslo'
WHERE Country = 'Norway';

# Update the City value and the Country value.

UPDATE Customers
SET
 City = 'Oslo',
Country = 'Norway'
WHERE CustomerID = 32;

// DELETE
# Update the City value and the Country value.
DELETE FROM Customers
WHERE Country = 'Norway';

# Delete all the records from the Customers table.
DELETE FROM Customers;

// SQL FUNCTIONS
# Use the MIN function to select the record with the smallest value of the Price column.
SELECT MIN(Price) FROM Products;

# Use an SQL function to select the record with the highest value of the Price column.
SELECT MAX(Price) FROM Products;

# Use the correct function to return the numbers of records that have the Price value set to 18.
SELECT COUNT (*) FROM Products 
WHERE Price = 18;

# Use an SQL function to calculate the average price of all products.
SELECT AVG(Price) FROM Products;

# Use an SQL function to calculate the sum of all the Price column values in the Products table.
SELECT SUM(Price) FROM Products;

// SQL LIKE
# Select all records where the value of the City column starts with the letter "a".
SELECT * FROM Customers 
WHERE City LIKE 'a%' ;


# Select all records where the value of the City column ends with the letter "a".
SELECT * FROM Customers WHERE City LIKE '%a' ;

# Select all records where the value of the City column contains the letter "a".
SELECT * FROM Customers WHERE City LIKE '%a%' ;

# Select all records where the value of the City column starts with letter "a" and ends with the letter "b".
SELECT * FROM Customers WHERE City LIKE 'a%b' ;

# Select all records where the value of the City column does NOT start with the letter "a".
SELECT * FROM Customers
WHERE City NOT LIKE 'a%';

// WILDCARDS

# Select all records where the second letter of the City is an "a".
SELECT * FROM Customers
WHERE City LIKE '_a%';

# Select all records where the first letter of the City is an "a" or a "b" or a "c".
SELECT * FROM Customers 
WHERE City LIKE ' [abc] %';

# Select all records where the first letter of the City starts with anything from an "a" to an "f".
SELECT * FROM Customers
WHERE City LIKE '[a-f]%';

# Select all records where the first letter of the City is NOT an "a" or a "b" or a "c".

SELECT * FROM Customers 
WHERE City LIKE ' [!abc] %';

// SQL IN
# Use the IN operator to select all the records where Country is either "Norway" or "France".
SELECT * FROM Customers 
WHERE Country IN ('Norway', 'France' ) ;

# Use the IN operator to select all the records where Country is NOT "Norway" and NOT "France".
SELECT * FROM Customers 
WHERE Country NOT IN ('Norway', 'France');

# SQL BETWEEN
#Use the BETWEEN operator to select all the records where the value of the Price column is between 10 and 20.
SELECT * FROM Products 
WHERE Price BETWEEN 10 AND 20 ;

# Use the BETWEEN operator to select all the records where the value of the Price column is NOT between 10 and 20.
SELECT * FROM Products 
WHERE Price NOT BETWEEN 10 AND 20 ;

# Use the BETWEEN operator to select all the records where the value of the ProductName column is alphabetically between 'Geitost' and 'Pavlova'.
SELECT * FROM Products 
WHERE ProductName BETWEEN 'Geitost' AND 'Pavlova' ;

// SQL ALIAS
# When displaying the Customers table, make an ALIAS of the PostalCode column, the column should be called Pno instead.
SELECT CustomerName, 
Address, 
PostalCode AS Pno 
FROM Customers;

# When displaying the Customers table, refer to the table as Consumers instead of Customers.
SELECT *FROM Customers 
AS Consumers;


// JOIN
# Insert the missing parts in the JOIN clause to join the two tables Orders and Customers, using the CustomerID field in both tables as the relationship between the two tables.

SELECT * FROM Orders 
LEFT JOIN Customers ON 
Orders.CustomerID = Customers.CustomerID ;

#Choose the correct JOIN clause to select all records from the two tables where there is a match in both tables.
SELECT *
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID=Customers.CustomerID;

# Choose the correct JOIN clause to select all the records from the Customers table plus all the matches in the Orders table.
SELECT *
FROM Orders
RIGHT JOIN Customers
ON Orders.CustomerID=Customers.CustomerID;

// GROUP BY
# List the number of customers in each country.
SELECT COUNT (CustomerID),
Country
FROM Customers
GROUP BY Country;

# List the number of customers in each country, ordered by the country with the most customers first.
    SELECT COUNT (CustomerID),
    Country 
    FROM Customers
    GROUP BY Country 
    ORDER BY COUNT(CustomerID) DESC ;

// SQL DB
# Write the correct SQL statement to create a new database called testDB.
CREATE DATABASE testDB

# Write the correct SQL statement to delete a database named testDB.
DROP DATABASE testDB


// IMPORTING SQL LAB QUERIES SO I CAN VIEW ALL EXAMPLES IN ONE DOC:

# Database Queries

## find all customers that live in London. Returns 6 records.
SELECT * FROM Customers
WHERE City = 'London';

## find all customers with postal code 1010. Returns 3 customers.
SELECT * FROM Customers
WHERE PostalCode = 1010;

## find the phone number for the supplier with the id 11. Should be (010) 9984510.
SELECT * FROM Suppliers
WHERE SupplierID = 11;

## list orders descending by the order date. The order with date 1997-02-12 should be at the top.
SELECT * FROM Orders
ORDER BY OrderDate DESC;

## find all suppliers who have names longer than 20 characters. You can use `length(SupplierName)` to get the length of the name. Returns 11 records.
SELECT * FROM Suppliers
WHERE length(SupplierName) > 20;

## find all customers that include the word "market" in the name. Should return 4 records.
SELECT * FROM Customers
WHERE CustomerName LIKE '%market%';

## add a customer record for _"The Shire"_, the contact name is _"Bilbo Baggins"_ the address is _"1 Hobbit-Hole"_ in _"Bag End"_, postal code _"111"_ and the country is _"Middle Earth"_.
INSERT INTO Customers (
    CustomerName,
    ContactName,
    Address,
    City,
    PostalCode,
    Country)
VALUES(
    'The Shire',
    'Bilbo Baggins',
    '1 Hobbit Hole',
    'Bag End',
    '111',
    'Middle Earth');

## update _Bilbo Baggins_ record so that the postal code changes to _"11122"_.
UPDATE Customers
SET PostalCode='11122'
WHERE PostalCode='111';




Link: https://www.w3schools.com/Sql/tryit.asp?filename=trysql_select_top