# Module 06 – Exploiting Application based Vulnerabilities

## Overview

- Explain common webapplication attacks
- Use tools to conduct injection attacks, authorization and authentication-based attacks, cross-scripting vulnerabilities
- Explain clickjacking
- Explain how to exploit insecure code
---

## Key Learnings:

### Overview of web application based attacks and OWASP top 10
- In most cases, HTTP is categorized as a stateless protocol that does not rely on a persistent connection for communication logic
- HTTP proxies act as both servers and clients. Proxies make requests to web servers on behalf of other clients. They enable HTTP transfers across firewalls and can also provide support for caching of HTTP messages
- Proxies can perform other roles in complex environments, including Network Address Translation (NAT) and filtering of HTTP requests
- The HTTP status code messages can be in the following ranges:

Messages in the 100 range are informational.
Messages in the 200 range are related to successful transactions.
Messages in the 300 range are related to HTTP redirections.
Messages in the 400 range are related to client errors.
Messages in the 500 range are related to server errors.
- REST APIs are used to build and integrate multiple-application software. In short, if you want to interact with a web service to retrieve information or add, delete, or modify data, an API helps you communicate with such a system in order to fulfill the request
- A web session is a sequence of HTTP request and response transactions between a web client and a server
- These transactions include pre-authentication tasks, the authentication process, session management, access control, and session finalization
- After an authenticated session has been established, the session ID (or token) is temporarily equivalent to the strongest authentication method used by the application, such as usernames and passwords, one-time passwords, and client-based digital certificates
- The use of an encrypted communication channel also protects the session against some session fixation attacks, in which the attacker is able to intercept and manipulate the web traffic to inject (or fix) the session ID on the victim’s web browser
- If a cookie has a Max-Age or Expires attribute, it is considered a persistent cookie and is stored on a disk by the web browser until the expiration time
- Modern applications typically track users after authentication by using non-persistent cookies. This forces the session information to be deleted from the client if the current web browser instance is closed

### Injection Based Vulnerabilities

-SQL INJECTION
   - SQL injection (SQLi) vulnerabilities can be catastrophic because they can allow an attacker to view, insert, delete, or modify records in a database
   - When the string Smith' or '1'='1 is entered in the web form, it causes the application to display all records in the database table to the attacker. This is an example of a Boolean SQL injection attack.
   - As a penetration tester, you can start by adding a single quote (‘) or a semicolon ( ; ) to the field or parameter in a web form. The single quote is used in SQL as a string terminator. If the application does not filter it correctly, you may be able to retrieve records or additional information that can help enhance your query or statement
   - In-band SQL injection: With this type of injection, the attacker obtains the data by using the same channel that is used to inject the SQL code. where the data is dumped directly in a web application (or web page)
   - Out-of-band SQL injection: With this type of injection, the attacker retrieves data using a different channel. For example, an email, a text, or an instant message could be sent to the attacker with the results of the query
   - Blind (or inferential) SQL injection: With this type of injection, the attacker does not make the application display or transfer any data; rather, the attacker is able to reconstruct the information by sending specific statements
   - purpose of performing database fingerprinting is to understand the back end database that the appliction uses

- Command Injection Vulnerabilities
   - A command injection is an attack in which an attacker tries to execute commands that he or she is not supposed to be able to execute on a system via a vulnerable application
   - Command injection attacks are possible when an application does not validate data supplied by the user (for example, data entered in web forms, cookies, HTTP headers, and other elements)
   - With command injection, an attacker tries to send operating system commands so that the application can execute them with the privileges of the vulnerable application
   - EX: 198.51.100.5;cat /etc/passwd

- Lightweight Directory Access Protocol (LDAP) Injection Vulnerabilities
    - LDAP injection vulnerabilities are input validation vulnerabilities that an attacker uses to inject and execute queries to LDAP servers
    -  A successful LDAP injection attack can allow an attacker to obtain valuable information for further attacks on databases and internal applications.
    - There are two general types of LDAP injection attacks:

Authentication bypass: The most basic LDAP injection attacks are launched to bypass password and credential checking.
Information disclosure: An attacker could inject crafted LDAP packets to list all resources in an organization’s directory and perform reconnaissance.

### Authentication-Based Vulnerabilities

- Session Hijacking
   - Once an authenticated session has been established, the session ID (or token) is temporarily equivalent to the strongest authentication method used by the application.
   - It is possible to easily fingerprint these development frameworks and languages by using the following session ID names:
PHP: PHPSESSID
J2EE: JSESSIONID
ColdFusion: CFID and CFTOKEN
ASP.NET: ASP.NET_SessionId
   
   - Sometimes developers set it to just a few bits, but the session ID must be at least 128 bits (16 bytes). Also, the session ID must be unique and unpredictable
   - It’s a good idea to use a cryptographically secure pseudorandom number generator (PRNG) because the session ID value must provide at least 256 bits of entropy
   - Configuring a cookie with the HTTPOnly flag forces the web browser to have this cookie processed only by the server, and any attempt to access the cookie from client-based code or scripts is strictly forbidden
   - It is important to use non-persistent cookies so the session ID does not remain in the web client cache for long periods of time
   - There are several ways an attacker can perform session hijacking and several ways a session token may be compromised:
 - Predicting session tokens: This is why it is important to use non-predictable tokens, as previously discussed in this section.
- Session sniffing: This can occur through collecting packets of unencrypted web sessions.
- On-path attack (formerly known as man-in-the-middle attack): With this type of attack, the attacker sits in the path between the client and the web server. In addition, a browser (or an extension or a plugin) can be compromised and used to intercept and manipulate web sessions between the user and the web server. This browser-based attack was previously known as a man-in-the-browser attack

- Redirect Attacks
   -  The attacker can exploit such vulnerabilities when a web server accepts untrusted input that could cause the web application to redirect the request to a URL contained within untrusted input
   - The attacker can modify the untrusted URL input and redirect the user to a malicious site to either install malware or steal sensitive information
 
- Default Credentials
   - Attackers can easily identify and access systems that use shared default passwords
   - Passwords can be found in product documentation and compiled lists available on the Internet. An example is http://www.defaultpassword.com, but there are dozens of other sites that contain default passwords and configurations on the Internet

- Kerberos Vulnerabilities
   - Kerberos implementations is the use of unconstrained Kerberos delegation, a feature that allows an application to reuse the end-user credentials to access resources hosted on a different server














---

## Tools Introduced

- curl
- Nikto - website scanner
- 
  
---

## References

- https://www.w3schools.com/tags/ref_httpmessages.asp
- https://www.geeksforgeeks.org/sql-ddl-dml-tcl-dcl
- https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all
- https://curl.haxx.se/docs/http2.html
- https://www.owasp.org/index.php/Authentication_Cheat_Sheet
- https://owasp.org/www-project-top-ten/
- https://www.owasp.org/index.php/Command_Injection
- https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html
- http://www.defaultpassword.com/
- https://www.shodan.io/
