# 🏛️ CTFlearn – Modern Gaius Julius Caesar

## 🧩 Challenge Information
- **Category:** Cryptography  
- **Difficulty:** Easy  
- **Platform:** CTFlearn  

---

## 📝 Description
The challenge gives an encrypted text:

BUH'tdy,!Bim5y~Bdt76yQ


The name hints at a **Caesar Cipher**, but the challenge description says:  
> “Nobody uses Alphabet nowadays, right? Why should you when you have your keyboard?”

This implies a **keyboard shift cipher** — Caesar shift but applied to keyboard layout instead of alphabet.

---

## 🛠️ Steps to Solve

### 1️⃣ Identify the Cipher Type  
Based on the hint, this is a **QWERTY Keyboard Shift Cipher**.

### 2️⃣ Use a Keyboard Caesar Decoder  
Using CyberChef:  
- “Keyboard Shift (QWERTY)”  
- Try standard shifts (left/right)

After shifting correctly, the decrypted text reveals the flag.

---

## 🎯 Final Flag
CTFlearn{h4ck3d}


---

## 🧠 Takeaways
- Some Caesar-style challenges use **keyboard layout** instead of alphabet  
- CyberChef includes a ready tool for keyboard-shift decoding  

