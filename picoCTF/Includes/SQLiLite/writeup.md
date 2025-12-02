# picoCTF 2022 – SQLiLite (Web Exploitation)

## 🎯 Challenge Description
This challenge presents a login page that is vulnerable to a basic SQL Injection attack.  
The goal is to bypass authentication and reveal the flag stored in the backend.

---

## 🛠️ Steps to Solve

### **1. Launch the instance**
After starting the challenge, a login page appears with two fields:
- **Username**
- **Password**

There is no additional information—clear sign to test for SQL Injection.

---

### **2. Test for SQL Injection**
A common first payload is:

' OR '1'='1


If the site does not sanitize input properly, this will always evaluate to TRUE.

---

### **3. Working payload**
Trying different variations, this payload bypassed the login:

' OR 1=1--


Explanation:
- `'` closes the original query's string  
- `OR 1=1` makes condition always true  
- `--` comments out the rest of the SQL query  

---

### **4. Login bypass successful**
Submitting the payload grants access and reveals the flag.

---

## 🏁 Flag
Flag hidden due to CTF rules.  
Format:

picoCTF{...}


---

## 💡 Notes
- Classic SQL Injection (Authentication Bypass).  
- Highlights importance of sanitizing user inputs.
