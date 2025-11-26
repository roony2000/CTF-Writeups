# 🧠 Flag Hunters – Reverse Engineering Challenge

## 🧩 Challenge Description
This challenge hides the flag inside JavaScript code that runs in the browser.  
The objective is to inspect the JavaScript logic and extract the hidden flag.

---

## 🛠️ Steps to Solve

### 1️⃣ Open Developer Tools  
Press **F12** or right-click → Inspect.

### 2️⃣ Check JavaScript Code  
Navigate to:
- **Sources** → to view JS files  
- **Elements** → to inspect inline scripts

### 3️⃣ Analyze the Logic  
Read the script carefully and look for:
- Hardcoded strings  
- Functions generating the flag  
- Hidden or obfuscated variables  

Often in beginner RE challenges, the flag is stored directly in the script.

---

## 🎯 Notes & Takeaways

- JavaScript is commonly used to hide flags in entry-level RE challenges  
- No advanced tools (Ghidra / IDA) are needed  
- Always check:
  - Inline scripts
 

  - Minified but readable JS  
  - Comments with clues  
