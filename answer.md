# Database Relationships in E-Commerce

## 1. Definition of Database Relationship

A **database relationship** is a connection between two or more tables in a database that shows how data in one table is related to data in another. These relationships help maintain data consistency, reduce duplication, and improve data organization.

In an e-commerce system, relationships connect tables such as customers, orders, products, and payments.

---

## 2. Types of Database Relationships

There are three main types of database relationships:

1. One-to-One (1:1)
2. One-to-Many (1:M)
3. Many-to-Many (M:N)

---

## 3. One-to-One Relationship (1:1)

### Definition

In a **one-to-one** relationship, one record in Table A is related to only one record in Table B, and vice versa.

### E-Commerce Example

**User ↔ User Profile**

* Each user has only one profile.
* Each profile belongs to only one user.

### Example Tables

**Users Table**

| user_id | name  |
| ------- | ----- |
| 1       | Rahul |
| 2       | Neha  |

**Profiles Table**

| profile_id | user_id | address |
| ---------- | ------- | ------- |
| 101        | 1       | Delhi   |
| 102        | 2       | Mumbai  |

### Diagram

```
User (1) ────── (1) Profile
```

### Usage

Used when detailed information is separated for security or performance.

---

## 4. One-to-Many Relationship (1:M)

### Definition

In a **one-to-many** relationship, one record in Table A can be related to many records in Table B, but each record in Table B belongs to only one record in Table A.

### E-Commerce Example

**Customer ↔ Orders**

* One customer can place many orders.
* Each order belongs to only one customer.

### Example Tables

**Customers Table**

| customer_id | name  |
| ----------- | ----- |
| 1           | Ravi  |
| 2           | Anita |

**Orders Table**

| order_id | customer_id | total |
| -------- | ----------- | ----- |
| 201      | 1           | 2000  |
| 202      | 1           | 1500  |
| 203      | 2           | 3000  |

### Diagram

```
Customer (1) ────── (M) Orders
```

### Usage

Most common relationship in e-commerce systems.

---

## 5. Many-to-Many Relationship (M:N)

### Definition

In a **many-to-many** relationship, many records in Table A can be related to many records in Table B.

This relationship is implemented using a **junction (bridge) table**.

### E-Commerce Example

**Orders ↔ Products**

* One order can contain many products.
* One product can appear in many orders.

### Example Tables

**Orders Table**

| order_id |
| -------- |
| 301      |
| 302      |

**Products Table**

| product_id | name   |
| ---------- | ------ |
| 1          | Mobile |
| 2          | Laptop |

**Order_Items Table (Junction Table)**

| order_id | product_id | quantity |
| -------- | ---------- | -------- |
| 301      | 1          | 2        |
| 301      | 2          | 1        |
| 302      | 1          | 3        |

### Diagram

```
Orders (M) ── Order_Items ── (M) Products
```

### Usage

Used when multiple records can be linked with multiple records.

---

## 6. Importance of Database Relationships

Database relationships are important because they:

* Reduce data redundancy
* Maintain data accuracy
* Improve data organization
* Support complex queries
* Ensure referential integrity

---

## 7. Summary Table

| Relationship Type | Description                    | E-Commerce Example |
| ----------------- | ------------------------------ | ------------------ |
| One-to-One        | One record links to one record | User ↔ Profile     |
| One-to-Many       | One record links to many       | Customer ↔ Orders  |
| Many-to-Many      | Many records link to many      | Orders ↔ Products  |

---

## 8. Conclusion

Database relationships are the foundation of any relational database system. In e-commerce applications, they connect customers, orders, products, and payments efficiently. Understanding these relationships helps in designing scalable, secure, and high-performance systems.

Proper use of one-to-one, one-to-many, and many-to-many relationships ensures smooth data management and reliable application behavior.
