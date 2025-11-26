# 🔐 CTFlearn – Hextroadinary

## 🧩 Challenge Information
- **Category:** Cryptography  
- **Difficulty:** Easy  
- **Platform:** CTFlearn  

---

## 📝 Description
The challenge provides two hex values and hints that something was done to generate a “secret code”.  
This usually means a bitwise operation — the most common being XOR.

We are given:

0xc4115 0x4cf8


---

## 🛠️ Steps to Solve

### 1️⃣ Identify Possible Operation (XOR)
When two hex values are given without further context, XOR is a strong possibility.

### 2️⃣ Apply XOR  
Using an online XOR calculator:

Input A: `c4115`  
Input B: `4cf8`  

You get:

c0ded


This is a valid-looking output (and a fun word-play: “coded”).

---

## 🎯 Final Flag
0xc0ded


---

## 🧠 Takeaways
- XOR is one of the most common operations in beginner cryptography challenges  
- If you’re given two hex numbers → try XOR first  
- Tools like CyberChef, XOR calculators, or Python one-liners are very useful  


