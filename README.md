# Burpe-suite
Web Application Security: Cross-Site Scripting (XSS)
Identified a Reflected XSS vulnerability in a web application. Demonstrated how lack of input sanitization allows an attacker to execute arbitrary JavaScript in the user's browser context
Project Objective
The goal of this project was to identify and exploit a Reflected Cross-Site Scripting (XSS) vulnerability within a controlled lab environment (DVWA). I focused on bypassing front-end interfaces and manipulating HTTP requests directly using industry-standard tools.

## Toolset
Target: Metasploitable 2 (DVWA - Damn Vulnerable Web Application)
Platform: Kali Linux
Proxy Tool: Burp Suite Community Edition (Intercept, Repeater, and Render Engine)

## Execution Phases
1. Interception & Analysis
Using the Burp Suite Proxy, I intercepted the raw HTTP GET request sent by the browser. By analyzing the headers, I identified that the name parameter was being passed directly into the URL without proper sanitization.
2. Manual Manipulation (The "Modern" Method)
Instead of using the browser's input box, I moved the request to Burp Repeater. This allowed for:
Bypassing client-side length restrictions.
Rapid testing of different JavaScript payloads.
Direct manipulation of the URI parameters.
3. Payload Injection
I injected a JavaScript payload designed to trigger a browser alert

## Security Implications & Mitigation
The Risk: An attacker could use this vulnerability to steal session cookies (PHPSESSID), perform account takeovers, or redirect users to malicious phishing sites.
The Fix: Implement Input Validation and Output Encoding. Specifically, the application should use functions to escape HTML characters (e.g., converting < to &lt;) before rendering user input on the page.


images attached below
![burpesuite](https://github.com/user-attachments/assets/e0a54ef3-90b2-4ec9-a0f5-164e8580a01f)
