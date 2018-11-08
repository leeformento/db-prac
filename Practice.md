# Insert the missing statement to get all the columns from the Customers table.
SELECT * FROM Customers;

# Write a statement that will select the City column from the Customers table.
SELECT City FROM Customers;

# Select all the different values from the Country column in the Customers table.
SELECT DISTINCT Country FROM Customers;

# Select all records where the City column has the value "Berlin".
SELECT * FROM Customers WHERE City = 'Berlin' ;

# Select all records where the City column is NOT the value "Berlin".
SELECT * FROM Customers WHERE City <> ' Berlin ';

# Select all records where the CustomerID column has the value 32.
SELECT * FROM Customers WHERE CustomerID = 32 ;

# Select all records where the City column has the value 'Berlin' and the PostalCode column has the value 12209.
SELECT * FROM Customers WHERE City = 'Berlin' AND PostalCode = 12209;

# Select all records where the City column has the value 'Berlin', and also the records where the City column has the value 'London'.
SELECT * FROM Customers WHERE City = 'Berlin' OR City = ' London ';

# Select all records from the Customers table, sort the result alphabetically by the column City.
SELECT * FROM Customers ORDER BY City ;

# Select all records from the Customers table, sort the result reversed alphabetically by the column City.
SELECT * FROM Customers ORDER BY City DESC ;

# Select all records from the Customers table, sort the result alphabetically, first by the column Country, then, by the column City.
SELECT * FROM Customers ORDER BY Country, City ;






