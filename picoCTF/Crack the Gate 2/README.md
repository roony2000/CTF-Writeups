🛡️ picoCTF – Local Authority (Web Exploitation) Write-up
📌 Challenge Description

The challenge provides a login page and asks whether we can obtain the flag by investigating the website.
We are given a valid username (email), but no password, and the login form enforces a long delay after each failed attempt. This makes brute-forcing slow unless we find a way around the lockout system.

🎯 Goal

Bypass the login rate-limit and discover the correct password from a provided wordlist in order to retrieve the flag.

🧠 Approach Overview

The website blocks repeated login attempts by enforcing a 20-minute delay after each incorrect password.
To bypass this, we can spoof different client IP addresses using the HTTP header:

X-Forwarded-For: <IP>

Each request coming from a different IP will not be subject to the delay, allowing fast brute-forcing.

The challenge also provides a password wordlist, so we can automate testing each candidate.

To perform the attack efficiently, we use Burp Suite Intruder with a Pitchfork attack type to iterate over two payload lists simultaneously:

1.List A – Multiple spoofed IP addresses

2.List B – The password wordlist provided with the challenge

🔧 Tools Used

* Burp Suite Community/Professional

* Pitchfork Intruder Attack

* X-Forwarded-For Header Injection

* Wordlists:

* ips.txt — 20 different IP addresses (generated separately)

* passwords.txt — provided by the challenge

🚀 Step-by-Step Exploitation
1. Configure Burp Proxy

Start Burp Suite → enable the browser → navigate to the challenge login page.

2. Capture a login request

Enter the provided email and any dummy password.
Send the request to Intruder.

3. Choose Attack Type

Intruder → Attack Type → Pitchfork

This allows two payload lists to be processed in parallel:

* Position 1 → IP addresses

* Position 2 → Passwords

4. Add Positions

Modify the request headers:

Add the spoof header:
X-Forwarded-For: §IP§


Mark IP as a payload position.

Then mark the password field value as the second payload position.

5. Load Payload Lists

Payload Set 1 → load ips.txt
Payload Set 2 → load passwords.txt

6. Launch the Attack

Start the Intruder attack.

Look for any request with a noticeably different response length or status code, which indicates a successful login.

7. Retrieve the Flag

Open the successful response; it will contain the picoCTF flag.
🏁 Final Flag

The flag discovered through the attack:
picoCTF{}

