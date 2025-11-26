# 💉 CTFlearn – Basic Injection

## 🧩 Challenge Information
- **Category:** Web  
- **Difficulty:** Easy  

---

## 📝 Description
The challenge asks the user to leak the entire database using basic SQL injection techniques.

The webpage displays the following debug message:


Original Query:
SELECT * FROM webfour.webfour WHERE name = '$input'


This indicates that the input is directly placed into the SQL query → vulnerable to SQL Injection.

---

## 🛠️ Steps to Solve

### 1️⃣ Identify the Vulnerability  
Since user input is inserted directly into the SQL query, a Boolean-based SQL injection is possible.

### 2️⃣ Inject a Always-True Condition  
Payload used:

' OR '1'='1


This makes the WHERE condition always evaluate to **true**.

### 3️⃣ Result  
The database returns all rows, including the one containing the flag.

---

## 🎯 Takeaways
- Classic SQL injection using OR '1'='1'  
- No input filtering or sanitization  
- Basic Boolean-based SQLi  
