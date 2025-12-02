# picoCTF 2022 – Includes (Writeup)

## 📌 Challenge Description
This challenge hints at file inclusion. After launching the instance, the website has a structure that allows accessing included files directly.

---

## 🛠️ Steps to Solve

### 1️⃣ Launch the instance
After starting the challenge, you are given a simple webpage.

### 2️⃣ Inspect the page
Open **View Page Source** or use **Developer Tools**.

Inside the HTML, you can notice that the website loads another file internally.

### 3️⃣ Try accessing the included file
If a page uses something like:

include("hidden.php")


### 4️⃣ Access the file
Go to the found file through the browser.

Once you open it, you will see the **picoCTF flag** displayed inside.

---

## 🏁 Flag
The flag is hidden due to CTF rules, but it follows this format:

picoCTF{...}


---

## 💡 Notes
- This is a classic example of **Local File Inclusion basics**.
- Great beginner-level web exploitation challenge.
