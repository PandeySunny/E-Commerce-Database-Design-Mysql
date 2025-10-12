# 🛍️ Developed-and-optimized-a-comprehensive-E-Commerce-relational-database-system-using-MySQL
# E-Commerce Database Design (MySQL)

## 📘 Project Overview
This project focuses on designing and implementing a **relational E-Commerce database system** using **MySQL**. The goal was to model real-world e-commerce operations—managing customers, employees, products, orders, and payments—while ensuring data integrity, scalability, and performance.  

The database is structured to handle key business workflows such as **order management, inventory tracking, and payment processing**, providing a strong backend foundation for any e-commerce platform.

---

## 🎯 Objectives
- Develop a **normalized relational database** structure for an online retail system.  
- Create an **Entity-Relationship Diagram (ERD)** representing all business entities and their relationships.  
- Apply **primary and foreign key constraints** to ensure referential integrity.  
- Implement **SQL queries, joins, and indexing strategies** for efficient data operations.  
- Demonstrate database best practices including **schema design**, **normalization**, and **query optimization**.

---

## 🏗️ Database Design
### **Main Entities**
1. **Customers** – Stores customer information, sales representatives, and credit limits.  
2. **Employees** – Manages employee data and reporting structure.  
3. **Offices** – Contains office locations and contact details.  
4. **Orders & OrderDetails** – Tracks customer orders, product details, quantities, and prices.  
5. **Products & ProductLines** – Maintains product catalog, stock levels, and descriptions.  
6. **Payments** – Records customer payments and transaction dates.  

### **Relationships**
- One-to-Many between **Customers → Orders**  
- One-to-Many between **Orders → OrderDetails**  
- One-to-Many between **ProductLines → Products**  
- Many-to-One between **Employees → Offices**  
- One-to-Many between **Customers → Payments**

---

## 🧠 Key Features
- Designed an optimized **ER Model** for efficient relational mapping.  
- Applied **data normalization up to 3NF** to reduce redundancy.  
- Created **indexes** to improve query performance.  
- Implemented **complex joins and subqueries** for advanced reporting.  
- Enforced **referential integrity** using primary and foreign keys.  
- Supported **transaction consistency** and **data scalability**.

---

## ⚙️ Tools & Technologies
- **Database:** MySQL  
- **Design Tool:** MySQL Workbench  
- **Languages:** SQL  
- **Techniques:** ER Modeling, Normalization (1NF–3NF), Query Optimization  

---

## 💻 Example SQL Snippets

### Create Table – Customers
```sql
CREATE TABLE Customers (
  customerNumber INT PRIMARY KEY,
  customerName VARCHAR(50),
  contactLastName VARCHAR(50),
  contactFirstName VARCHAR(50),
  phone VARCHAR(20),
  addressLine1 VARCHAR(100),
  city VARCHAR(50),
  country VARCHAR(50),
  salesRepEmployeeNumber INT,
  creditLimit DECIMAL(10,2),
  FOREIGN KEY (salesRepEmployeeNumber) REFERENCES Employees(employeeNumber)
);
