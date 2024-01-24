# Employee-Management-System---Stored-XSS


Title: Multiple Stored XSS

Affected Component: /employee_akpoly/Employee/edit-profile.php

CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')

CVSS 3.1 Score: 3.3

Impact: Cross-Site Scripting (XSS) vulnerabilities pose significant risks to web applications and users. These vulnerabilities can lead to unauthorized access, data manipulation, session hijacking, phishing attacks, malicious redirection, defacement, and client-side attacks. Attackers exploit XSS to inject and execute malicious scripts in the context of users' browsers, enabling a range of malicious activities. Impact severity varies, but the potential consequences include unauthorized access to sensitive information, reputation damage, and client-side exploitation. Mitigation strategies involve implementing secure coding practices like input validation, output encoding, and Content Security Policy (CSP). Regular security assessments, code reviews, and user awareness are crucial for effective XSS prevention.

Proof of Concept (POC): To simulate this attack, initiate by logging in as an employee and accessing the employee profile editing page. On this page, various input fields, such as fullname, phone, date of birth, address, and date of appointment, are found to be susceptible to stored Cross-Site Scripting (XSS). Exploit this vulnerability by injecting the payload "><script>alert("xss")</script>// into these input fields. Consequently, visiting any page displaying the information from these fields, including the admin panel, triggers an alert prompt with the message "xss."

https://github.com/jomskiller/Employee-Management-System---Stored-XSS/blob/main/image.png


Remediation: To remediate Cross-Site Scripting (XSS) vulnerabilities, adhere to secure coding practices. Implement thorough input validation on both the client and server sides, and use output encoding to prevent the execution of malicious scripts. Employ a robust Content Security Policy (CSP) to restrict unauthorized script execution. Ensure cookies have the "HttpOnly" and "Secure" flags. Apply context-specific output encoding based on data usage contexts. Enhance browser security with security headers like "X-Content-Type-Options" and "X-Frame-Options." Regularly update software components to patch known vulnerabilities. These measures collectively bolster the defense against XSS threats, securing web applications from potential exploits.
