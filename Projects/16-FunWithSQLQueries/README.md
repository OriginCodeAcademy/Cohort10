# Fun with SQL Queries

For this exercise, you will learn to install a SQL Server database using the restore method. Then, you will practice creating SQL statements using the query editor within SQL Server Management Studio, and complete a set of exercises covering basic SQL query syntax.

## Setup

### Download and install the Northwind sample database

* Navigate to:  https://northwinddatabase.codeplex.com/
* Download the Northwind database zip file:  Northwind.bak.zip
* Extract the contents of this zip file to `C:\Program Files\Microsoft SQL Server\MSSQL13.SQLEXPRESS\MSSQL\Backup`

* Open SQL Server Management Studio
* In the Object Explorer, right-click on Databases
* Select Restore Database...
* In the Restore Database UI, under Source, select Device and click the browse button (The button with the three period characters (`...`))
* At the Select Backup Device UI, select Add and navigate to Northwind.bak
* Click Ok, Ok, and Ok.

* You should see a message indicating the restore completed successfully. You should also see the Northwind database listed under `Databases`.
* Select the Northwind database in the Object Explorer and open the Tables folder to view the 13 tables of the database
* Create a query window by right clicking on the `NORTHWND` database and selecting New Query.
* Save this file locally as `sql-exercises.sql`.
* Create another query window and work your way through the exercises. As you complete each exercise, add and save the required SQL statement to sql-exercises.sql with a comment indicating which exercise it belongs to.
* When you've finished, create a new repository called `16-FunWithSqlQueries` and commit/push your completed `sql-exercises.sql` file.

### SQL Exercises

Create SQL statements to complete the following:

1.  Write a query to return all category names with their descriptions from the Categories table.
2.  Write a query to return the contact name, customer id, company name and city name of all Customers in London
3.  Write a query to return all available columns in the Suppliers tables for the marketing managers and sales representatives that have a FAX number
4.  Write a query to return a list of customer id's from the Orders table with required dates between Jan 1, 1997 and Dec 31, 1997 and with freight under 100 units.
5.  Write a query to return a list of company names and contact names of all customers from Mexico, Sweden and Germany.
6.  Write a query to return a count of the number of discontinued products in the Products table.
7.  Write a query to return a list of category names and descriptions of all categories beginning with 'Co' from the Categories table.
8.  Write a query to return all the company names, city, country and postal code from the Suppliers table with the word 'rue' in their address. The list should ordered alphabetically by company name.
9.  Write a query to return the product id and the quantity ordered for each product labelled as 'Quantity Purchased' in the Order Details table ordered by the Quantity Purchased in descending order.
10. Write a query to return the company name, address, city, postal code and country of all customers with orders that shipped using Speedy Express, along with the date that the order was made.
11. Write a query to return a list of Suppliers containing company name, contact name, contact title and region description.
12. Write a query to return all product names from the Products table that are condiments.
13. Write a query to return a list of customer names who have no orders in the Orders table.
14. Write a query to add a shipper named 'Amazon' to the Shippers table using SQL.
15. Write a query to change the company name from 'Amazon' to 'Amazon Prime Shipping' in the Shippers table using SQL.
16. Write a query to return a complete list of company names from the Shippers table. Include freight totals rounded to the nearest whole number for each shipper from the Orders table for those shippers with orders.
17. Write a query to return all employee first and last names from the Employees table by combining the 2 columns aliased as 'DisplayName'. The combined format should be 'LastName, FirstName'.
18. Write a query to add yourself to the Customers table with an order for 'Grandma's Boysenberry Spread'.
19. Write a query to remove yourself and your order from the database.
20. Write a query to return a list of products from the Products table along with the total units in stock for each product. Include only products with TotalUnits greater than 100.

## Turn In Instructions
* Push your changes to GitHub using `git push origin master`
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort7/issues/new?title=16-FunWithSqlQueries&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20What%20did%20you%20enjoy%20most%20about%20this%20project%3F%0A%0A3.%20What%20was%20the%20toughest%20part%3F%0A%0A)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
