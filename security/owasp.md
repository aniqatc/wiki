## [🪴 View In My Digital Garden: Open Web Application Security Project (OWASP)](https://www.aniqa.io/wiki/security/owasp)

The OWASP 10 online document that provides developers access to information regarding the top ten security risks for web applications along with possible solutions.


---

[**Open Web Application Security Project (OWASP)**](https://owasp.org/) - online, open-source community of web security experts from across the world that creates technologies, documentation & tools to improve and maintain web and software security.

[**OWASP 10**](https://owasp.org/Top10/) = an online document that provides a ranking of the top **ten most critical and frequent web security risks and a solution** for each.

- Factors that are considered when deciding which security risks make it to the OWASP 10:
   - frequency of the security risks
   - severity of vulnerabilities
   - magnitude of impact

**Purpose** - inform web developers about security risks so that they can minimize vulnerabilities to such attacks or issues to their websites and applications

---

## 2021 Risks Explained: 
1. **Broken Access Control**
    - access controls enforce restrictions so that users cannot act outside of their intended permissions on the specified website
    - unauthorized information disclosure, modification, or destruction of all or some data 
    - performing a function outside the user's limits 
2. **Cryptographic Failures**
    - involves protecting data in transit and at rest
    - includes sensitive data: *passwords, credit card numbers, health records, personal information, and business secrets that require extra protection*
3. **Injection** *(including Cross-Site Scripting - XSS)*
    - at risk when user-supplied data is not validated, filtered, or sanitized by the application
    - dynamic queries or non-parameterized calls without context-aware escaping are used directly in the interpreter
    - hostile data is used within object-relational mapping (ORM) search parameters to extract additional, sensitive records
    - when hostile data is directly used or attached to existing data
4. **Insecure Design**
    - risks related to design and layout flaws
5. **Security Misconfigurations** *(including former category: XML External Entities - XXE)*
    - missing security hardening across any part of the application stack
    - improperly configured permissions on cloud services
    - unnecessary features that are enabled or installed
    - unchanged default accounts or passwords
6. **Vulnerable and Outdated Components**
    - any software that is vulnerable, unsupported, or out of date
7. **Identification and Authentication Failures**
    - user’s identity, authentication, or session management is not properly handled; allowing attackers to exploit passwords, keys, session tokens, or implementation flaws to assume users’ identities temporarily or permanently
8. **Software and Data Integrity Failures** *(including Insecure Deserialization)*
    - code and infrastructure that fails to protect against integrity violations (implemented without verification):
       - software updates
       - critical data
       - CI/CD pipelines
    - applications with auto-update functionality without sufficient integrity verification
9. **Security Logging and Monitoring Failures**
    - errors in detecting, escalating, and responding to active breaches
    - insufficient logging, detection, and monitoring 
    - not logging auditable events like logins or failed logins, warnings and errors that generate inadequate or unclear log messages, or logs that are only stored locally
10. **Server-Side Request Forgery (SSRF)**
    - when a web application fetches a remote resource without validating the user-supplied URL

---

### 2017 vs. 2021 Vulnerabilities:

![](https://www.aniqa.io/static/12358d77ab0c7953795af91fe189667a/14e2f/owasp.png)
