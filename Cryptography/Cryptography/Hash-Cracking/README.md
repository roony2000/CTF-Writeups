# 🔐 Hash Cracking – Cryptography Challenge

## 🧩 Challenge Description
The challenge provides a hash value such as:

916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745


Your task is to determine the hash type and attempt to crack it.

---

## 🛠️ Approach

### 1️⃣ Identify the Hash Type  
The easiest way is to use **CrackStation**, which automatically detects the hash type.

1. Go to **https://crackstation.net/**
2. Paste the given hash
3. CrackStation will:
   - Identify the hash algorithm  
   - Compare it with its database (rainbow table)  
   - Return the plaintext (if available)

---

## 🎯 Notes & Takeaways

- CrackStation works only on hashes that exist in its database  
- If a hash is **salted**, **custom-made**, or too new → it may not crack  
- Tools like `hashid`, `hashcat`, and `john` can help identify types manually  
