# Module 05 – Exploiting Application based Vulnerabilities

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
- 


---

## Tools Introduced

- curl
- Nikto - website scanner
- 
  
---

## References

- https://www.w3schools.com/tags/ref_httpmessages.asp
- https://curl.haxx.se/docs/http2.html
- https://www.owasp.org/index.php/Authentication_Cheat_Sheet
- https://owasp.org/www-project-top-ten/
