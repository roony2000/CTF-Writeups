# picoCTF 2022 – SQLiLite (Writeup)

## 📌 Challenge Description
This challenge presents a login form that is vulnerable to **SQL Injection**.  
The goal is to bypass the login and reveal the hidden flag.

---

## 🛠️ Steps to Solve

### 1️⃣ Launch the instance
You are shown a simple login page:

- Username  
- Password  

No additional hints — a strong sign to test for SQL Injection.

---

### 2️⃣ Test for SQL Injection
Try entering a classic SQLi payload in the username or password fields:

' OR '1'='1


If the site does not sanitize input, the condition becomes TRUE.

---

### 3️⃣ Working Bypass Payload
This payload successfully bypassed the login:

' OR 1=1--


Explanation:
- `'` closes the string
- `OR 1=1` always evaluates to TRUE
- `--` comments out the rest of the SQL query

The backend query becomes something like:


SELECT * FROM users WHERE username='' OR 1=1--' AND password='test'


Which logs you in without knowing any real credentials.

---

### 4️⃣ Flag Appears
Once logged in, the challenge reveals the picoCTF flag.

---

## 🏁 Flag
Flag is hidden due to CTF rules.  
Format:


picoCTF{...}


---

## 💡 Notes
- Classic **SQL Injection – Authentication Bypass**.
- Shows why developers must sanitize inputs.
- Great foundation for more advanced SQLi challenges.

