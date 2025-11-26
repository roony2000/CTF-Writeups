# 🌐 picoCTF – WebDecode

## 🧩 Challenge Information
- **Event:** picoCTF 2024  
- **Category:** Web Exploitation  
- **Difficulty:** Easy  

---

## 📝 Summary
The challenge teaches the use of browser developer tools to uncover encoded data hidden in a webpage.

---

## 🛠️ Steps to Solve

### 1️⃣ Inspect the Page
The About section hints:  
> "Try to inspect the page."

### 2️⃣ Locate Hidden Data
You will find a Base64-encoded string:

cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9


### 3️⃣ Decode the String
Tools you can use:
- CyberChef (From Base64)
- Any online Base64 decoder

Decoded result reveals the flag in standard picoCTF format.

---

## 🎯 Key Notes
- Developer tools are essential for web exploitation
- Base64 is encoding, not encryption
- Always check:
  - HTML comments  
  - JS files  
  - Network requests  
