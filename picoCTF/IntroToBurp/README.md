Description

This challenge provides a link along with a hint indicating the need to “distort the request.”
This suggests that the server may reveal the flag if it receives a malformed or altered HTTP request.

The intended solution is to use Burp Suite to intercept and modify the request before it reaches the server.

Steps to Solve
1. Intercept the request using Burp Suite

Open Burp Suite.

Configure your browser to use Burp as a proxy server.

Visit the challenge link while Intercept mode is enabled.

The HTTP request will appear inside Burp Suite.

2. Modify (distort) the request

Inside the intercepted request, locate the "OTP" field.
Before forwarding the request to the server, delete the entire OTP parameter, then click Forward.

Once the malformed request is forwarded, the server responds by revealing the flag.

Final Flag
picoCTF{#0TP_Bypvss_SuCc3s$_2e80f1fd}
