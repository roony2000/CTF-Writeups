# 🔐 CTFlearn – HyperStream Test #2

## 🧩 Challenge Information
- **Category:** Cryptography  
- **Difficulty:** Easy  
- **Platform:** CTFlearn  

---

## 📝 Description
The challenge provides a long sequence of **A** and **B** characters.  
This pattern strongly suggests a **Baconian Cipher**, a classical encoding technique where each group of 5 letters represents a character.

The text given was:

ABAAAABBAABBABBBABBBAABAAABAAAAAAAABBAAABABBABBAAAAAABBBAABBABABBAABBAABBABBAABABABABBABB


This cipher typically maps:

- **A = 0**  
- **B = 1**  

Then each 5-bit group → converts to a letter.

---

## 🛠️ Steps to Solve

### 1️⃣ Identify the Cipher  
The repeating pattern of A's and B's clearly points to **Bacon's Cipher**.

### 2️⃣ Decode Using CyberChef  
Tools used:  
- **CyberChef → “From Baconian”**

Steps:
1. Open CyberChef  
2. Add operation **“From Baconian”**  
3. Paste the encoded A/B text  
4. Run the recipe  

### 3️⃣ Get the Flag  
The decoded output reveals:
CTFlearn{h4ck3d}


---

## 🧠 Takeaways
- A/B sequences (especially in groups of 5) usually indicate **Bacon’s Cipher**  
- CyberChef is extremely useful for classical cipher decoding  
- Recognizing patterns saves a lot of time in CTFs  

