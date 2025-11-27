# 🕵️‍♂️ CTFlearn – Suspicious Message

## 🧩 Challenge Information
- **Category:** Cryptography  
- **Difficulty:** Easy  
- **Platform:** CTFlearn  

---

## 📝 Description
The challenge provides an encrypted text:

MQDzqdor{Ix4Oa41W_1F_B00h_m1YlqPpPP}


And an attached image containing a long string of letters.  
This suggests a **Playfair Cipher** with a custom key.

The image text decodes into the Playfair key:

qwertyuiopasdfghjklzxcvbnm


---

## 🛠️ Steps to Solve

### 1️⃣ Extract the Key  
The PNG file contains a sequence representing the Playfair key square.

### 2️⃣ Decode the Cipher
Tools used:
- Boxentriq → Playfair Cipher Decrypt

Steps:
1. Insert encrypted text  
2. Set key to the extracted string  
3. Choose “Decrypt”

The output is:

CTFLEARN{PL4YF41R_1S_C00L_C1PHERRRR}


---

## 🎯 Final Flag
CTFLEARN{PL4YF41R_1S_C00L_C1PHERRRR}


---

## 🧠 Takeaways
- Playfair uses **pairs of letters (digraphs)**  
- Keys can be hidden inside images or hints  
- Boxentriq is extremely helpful for classical ciphers  

