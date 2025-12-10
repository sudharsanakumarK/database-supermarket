# 🛒 Supermarket Database Management System  
A complete SQL-based database solution designed to manage and optimize supermarket operations.

---

## 📖 Overview  
The **Supermarket Database Management System (SDMS)** is a comprehensive relational database designed to handle core supermarket activities such as product inventory, customer records, supplier details, staff management, sales processing, and reporting.  
This project uses industry-standard database design practices including **ER Modeling**, **3NF Normalization**, **Primary & Foreign Keys**, and **Optimized SQL Queries**.

---

## 🎯 Objectives  
- Design a well-structured supermarket database using SQL  
- Maintain accurate product inventory and supplier linkage  
- Support customer billing and receipt generation  
- Track sales and employee performance  
- Provide analytics for business insights  
- Ensure data integrity through constraints and relational links  

---

## 🗂️ System Architecture  

### **Core Entities**
- Categories  
- Products  
- Suppliers  
- Customers  
- Employees  
- Sales  
- Sales_Items  
- Inventory  

### **ER Diagram Structure (Text Format)**. 

---

## 🏗️ Database Schema (Key Tables)

### **Categories**
- category_id (PK)  
- category_name  

### **Products**
- product_id (PK)  
- name  
- category_id (FK)  
- supplier_id (FK)  
- price  
- stock  

### **Suppliers**
- supplier_id (PK)  
- supplier_name  
- contact  
- address  

### **Customers**
- customer_id (PK)  
- customer_name  
- phone  
- email  

### **Employees**
- employee_id (PK)  
- employee_name  
- role  

### **Sales**
- sale_id (PK)  
- customer_id (FK)  
- employee_id (FK)  
- sale_date  
- total_amount  

### **Sales_Items**
- sale_item_id (PK)  
- sale_id (FK)  
- product_id (FK)  
- quantity  
- subtotal  

---

## 💻 SQL Implementation  

### **Create Table Example: Products**
```sql
CREATE TABLE Products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    category_id INT,
    supplier_id INT,
    price DECIMAL(10,2) NOT NULL,
    stock INT DEFAULT 0,
    FOREIGN KEY (category_id) REFERENCES Categories(category_id),
    FOREIGN KEY (supplier_id) REFERENCES Suppliers(supplier_id)
);