📝 Writeup: Information Disclosure on Debug Page (PortSwigger Lab)

(جاهز للنسخ واللصق في GitHub – README.md)

Summary

This lab demonstrates how sensitive information can be leaked through a publicly accessible debug page. The debug endpoint accidentally exposes internal environment variables, including a critical SECRET_KEY. Using this leaked value, the lab can be completed by submitting it to the designated endpoint.

Steps to Reproduce
1. Identify the debug page

While browsing the application, a URL parameter reveals a hidden debug endpoint.
Navigating to:

/cgi-bin/debug


(or whatever path is exposed in the lab)

shows a full debug dump containing environment variables and internal application metadata.

2. Look for sensitive information

The debug output includes a section such as:

Environment:
SECRET_KEY = 8c9f12df67a3e4fd…


This SECRET_KEY is intended to remain confidential, but the debug page has disclosed it publicly.

3. Submit the SECRET_KEY to solve the lab

The lab instructions specify submitting the leaked value.
Using Burp Repeater or your browser, send:

POST /submitSolution
secret_key=8c9f12df67a3e4fd...


The server validates the key and confirms the solution.

Impact

Exposing debug pages is extremely dangerous.
An attacker could:

Read environment variables

Extract SECRET_KEY, API keys, or credentials

Access internal server metadata

Potentially escalate into full application compromise

Debug endpoints often provide full visibility into the backend—exactly what attackers want.

Remediation

Never deploy debug functionality in production

Disable debug mode (DEBUG=False)

Restrict sensitive endpoints behind authentication

Avoid exposing environment variables in responses

Regularly audit routes for misconfigurations

Conclusion

The lab was solved by leveraging a leaked SECRET_KEY found on a debug page. This demonstrates how dangerous it is to expose debugging information in production environments.
