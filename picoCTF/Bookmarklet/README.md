📘 picoCTF – Bookmarklet
🏷️ Challenge Information

Category: Web Exploitation

Difficulty Level: Easy

Platform: picoCTF 2024

📝 Description

The challenge provides a webpage containing obfuscated JavaScript code that activates when a specific bookmark is clicked.

Instead of manually searching the webpage, we can extract the JavaScript code and execute it directly in the browser console to reveal the bookmark.

🛠️ Steps to Solve
1️⃣ Open the challenge link

Click "here" in the challenge description to visit the provided webpage.

You will find a button or link containing obfuscated JavaScript code that resembles a bookmark.

2️⃣ Extract the JavaScript Bookmark

Right-click on the bookmark → Copy the URL
(Or view the page source and copy the JavaScript code).

This will look like this:

javascript:(function(){ ... })()

3️⃣ Run JavaScript in the browser console

Open Developer Tools → Press F12

Go to the console tab

Paste the copied bookmark text, or if that doesn't work, go to the eye icon and paste it there.

Press Enter

4️⃣ Flag Appearance

Once the bookmark text is executed, the flag is printed directly in the console.

📌 Example of the result:

picoCTF{p@g3_turn3r_6bbf8953}

🏁 Final flag
picoCTF{p@g3_turn3r_6bbf8953}

🎯 Summary

Bookmarks often contain obfuscated JavaScript.

You can reveal the flags by running the bookmark directly in the browser console.

Always check JavaScript-based challenges using developer tools.
