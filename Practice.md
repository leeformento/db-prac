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







