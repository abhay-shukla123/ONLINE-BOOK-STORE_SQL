# ONLINE-BOOK-STORE_SQL
## Project Overview
The Online Book Store project is a **SQL-based data analysis project** that focuses on managing, querying, and analyzing data for a fictional online bookstore. The project demonstrates **database creation, data manipulation, and generating insights** using SQL queries.

## Objective
- Design and manage a database for an online bookstore.  
- Analyze book sales, customer behavior, and order trends.  
- Write SQL queries to extract meaningful business insights.  
- Showcase skills in database management and reporting.  

## Tools Used
- **SQL Server / MySQL / PostgreSQL** – for database creation and queries  
- **SQL Queries** – SELECT, JOIN, GROUP BY, ORDER BY, Aggregate functions  
- **Excel / CSV** – for data input or reporting (if used)  

## Database Structure
- **Tables Included:**  
  - Customers: Customer details  
  - Books: Book details including title, author, genre, price  
  - Orders: Sales and order information  
  - Order_Details: Individual items in each order  
  - Categories: Book categories and genres  

- **Relationships:**  
  - One-to-Many between Customers and Orders  
  - One-to-Many between Orders and Order_Details  
  - One-to-Many between Categories and Books  

## Key Queries & Features
- Total sales per book, category, and author.  
- Top-selling books and categories.  
- Customer purchase behavior analysis.  
- Monthly sales trend analysis.  
- Average order value and quantity sold per order.  

## Sample SQL Queries
```sql
-- Total sales per category
SELECT c.CategoryName, SUM(od.Quantity * b.Price) AS TotalSales
FROM Order_Details od
JOIN Books b ON od.BookID = b.BookID
JOIN Categories c ON b.CategoryID = c.CategoryID
GROUP BY c.CategoryName;

-- Top-selling books
SELECT b.Title, SUM(od.Quantity) AS TotalSold
FROM Order_Details od
JOIN Books b ON od.BookID = b.BookID
GROUP BY b.Title
ORDER BY TotalSold DESC;
