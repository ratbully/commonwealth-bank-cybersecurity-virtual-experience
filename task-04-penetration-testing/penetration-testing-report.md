
# Web Application Penetration Testing Report

**Commonwealth Bank Cybersecurity Virtual Experience**

| Project Detail | Description |
|---|---|
| Task | Task 04 – Penetration Testing |
| Training Platform | PortSwigger Web Security Academy |
| Assessment Type | Beginner-Level Web Application Security Testing |
| Labs Completed | 11 |
| Testing Environment | Authorised Educational Training Environment |

---

## 1. Executive Summary

This report documents a web application security testing exercise completed using **PortSwigger Web Security Academy** as part of the Commonwealth Bank Cybersecurity Virtual Experience.

The objective was to develop practical knowledge of common web application vulnerabilities, understand how they can affect application security, and identify appropriate mitigation strategies.

The exercise covered 11 beginner-level security labs involving:

- SQL Injection
- Cross-Site Scripting (XSS)
- Broken Access Control
- Authentication Weaknesses
- Username Enumeration
- Two-Factor Authentication Bypass
- File Path Traversal
- OS Command Injection

The exercises demonstrated how weaknesses in input handling, authentication, authorisation, and server-side functionality can potentially expose applications to unauthorised access, sensitive information disclosure, and unintended application behaviour.

Recommendations are provided to explain how organisations can prevent or reduce the impact of these vulnerabilities.

**Assessment Limitation:** This was an educational exercise conducted within PortSwigger Web Security Academy. It was not a penetration test of Commonwealth Bank's production systems.

---

## 2. Overview of the Testing Environment

PortSwigger Web Security Academy is an educational platform that provides practical web application security training through controlled vulnerability labs.

The platform enables learners to understand common security weaknesses, explore their potential impact, and study appropriate prevention techniques.

For this assessment, 11 beginner-level labs were completed across several web application vulnerability categories.

The purpose was to develop practical penetration testing knowledge and understand how similar vulnerabilities can be identified and prevented in real-world applications.

---

## 3. Scope of Testing

Testing was restricted to the selected PortSwigger Web Security Academy labs.

### 3.1 In-Scope Vulnerabilities

1. SQL Injection – Login Bypass
2. SQL Injection – Hidden Data Exposure
3. Reflected Cross-Site Scripting
4. Stored Cross-Site Scripting
5. DOM-Based Cross-Site Scripting
6. Unprotected Administrative Functionality
7. Hidden Administrative Functionality
8. Username Enumeration
9. Two-Factor Authentication Bypass
10. File Path Traversal
11. OS Command Injection

### 3.2 Out of Scope

- Real-world banking systems.
- Third-party websites and applications.
- External networks and systems.
- Any application outside the authorised training environment.

---

## 4. Vulnerability Findings and Recommendations

### Finding 1: SQL Injection – Login Bypass

**Vulnerability:** SQL Injection

**Description:**

SQL injection occurs when an application incorporates untrusted user input into database queries without appropriate safeguards.

In authentication functionality, this weakness may allow an attacker to manipulate database queries and interfere with normal login processes.

**Potential Impact:**

- Unauthorised account access.
- Authentication bypass.
- Exposure of sensitive information.

**Recommendations:**

- Implement parameterised queries and prepared statements.
- Avoid constructing SQL queries directly from user input.
- Apply server-side input validation.
- Restrict database account privileges.
- Monitor unusual authentication activity.

### Finding 2: SQL Injection – Hidden Data Exposure

**Vulnerability:** SQL Injection

**Description:**

Applications that process user-controlled input in database queries without proper protection may expose information that should remain restricted.

**Potential Impact:**

- Unauthorised access to database records.
- Exposure of confidential information.
- Compromise of data confidentiality.

**Recommendations:**

- Use prepared statements.
- Apply server-side input validation.
- Restrict database account privileges.
- Implement secure error handling.
- Conduct regular database security reviews.

### Finding 3: Reflected Cross-Site Scripting

**Vulnerability:** Reflected XSS

**Description:**

Reflected cross-site scripting occurs when an application includes untrusted user input in a webpage response without appropriate output encoding.

This may allow malicious scripts to execute in another user's browser.

**Potential Impact:**

- Unauthorised actions within a user's session.
- Exposure of browser-accessible information.
- Manipulation of webpage content.

**Recommendations:**

- Apply context-aware output encoding.
- Validate user input.
- Avoid unsafe handling of untrusted content.
- Implement an appropriate Content Security Policy.
- Use secure cookie attributes.

### Finding 4: Stored Cross-Site Scripting

**Vulnerability:** Stored XSS

**Description:**

Stored cross-site scripting occurs when an application saves untrusted user content and later displays it to other users without appropriate protection.

**Potential Impact:**

- Malicious script execution in users' browsers.
- Exposure of sensitive information.
- Compromise of user sessions.

**Recommendations:**

- Apply context-aware output encoding.
- Validate submitted content.
- Sanitise permitted HTML using trusted libraries.
- Implement a suitable Content Security Policy.
- Review user-generated content handling.

### Finding 5: DOM-Based Cross-Site Scripting

**Vulnerability:** DOM-Based XSS

**Description:**

DOM-based cross-site scripting occurs when client-side JavaScript processes untrusted data using unsafe browser APIs.

This demonstrates that security controls must cover both front-end and back-end application functionality.

**Potential Impact:**

- Unintended JavaScript execution.
- Manipulation of webpage content.
- Exposure of information accessible to the browser.

**Recommendations:**

- Use safe DOM APIs.
- Avoid inserting untrusted data into webpages through unsafe methods.
- Apply appropriate output encoding.
- Validate data before processing it.
- Review client-side JavaScript for insecure coding practices.

### Finding 6: Unprotected Administrative Functionality

**Vulnerability:** Broken Access Control

**Description:**

Administrative functionality may be exposed when an application does not properly verify whether a user has permission to access privileged features.

**Potential Impact:**

- Unauthorised administrative access.
- Unintended changes to application settings.
- Exposure or modification of sensitive information.

**Recommendations:**

- Enforce server-side authorisation checks.
- Apply role-based access control.
- Follow the principle of least privilege.
- Protect administrative functions with appropriate authentication.
- Log and monitor privileged activities.

### Finding 7: Hidden Administrative Functionality

**Vulnerability:** Improper Access Control

**Description:**

Sensitive administrative functionality may be discoverable through application information or navigation clues.

Hiding a sensitive URL does not provide effective security if the application fails to enforce authorisation.

**Potential Impact:**

- Unauthorised access to administrative features.
- Exposure of sensitive application functionality.
- Potential misuse of privileged operations.

**Recommendations:**

- Enforce server-side access controls on sensitive routes.
- Require appropriate authentication and authorisation.
- Avoid relying on hidden URLs as a security measure.
- Regularly review access permissions.
- Test administrative functionality for access control weaknesses.

### Finding 8: Username Enumeration

**Vulnerability:** Authentication Information Disclosure

**Description:**

Username enumeration occurs when an application provides different responses depending on whether a submitted username exists.

This may help attackers identify valid accounts.

**Potential Impact:**

- Identification of valid user accounts.
- Increased risk of targeted password attacks.
- Greater exposure to credential-based attacks.

**Recommendations:**

- Use consistent authentication error messages.
- Implement rate limiting.
- Monitor repeated authentication failures.
- Apply appropriate account protection measures.
- Use multi-factor authentication.

### Finding 9: Two-Factor Authentication Bypass

**Vulnerability:** Authentication Workflow Weakness

**Description:**

An authentication process may contain weaknesses if it does not correctly enforce the second authentication factor before granting access.

**Potential Impact:**

- Unauthorised account access.
- Reduced effectiveness of multi-factor authentication.
- Compromise of sensitive account information.

**Recommendations:**

- Enforce MFA verification on the server side.
- Validate every authentication stage.
- Prevent access before all required checks are completed.
- Protect authentication tokens and sessions.
- Monitor suspicious authentication activity.

### Finding 10: File Path Traversal

**Vulnerability:** Path Traversal

**Description:**

Path traversal occurs when an application uses user-controlled input to access files without properly restricting access to approved directories.

**Potential Impact:**

- Exposure of sensitive files.
- Unauthorised access to application resources.
- Disclosure of configuration information.

**Recommendations:**

- Restrict file access to approved directories.
- Use allowlists for permitted files.
- Avoid passing raw user input directly into file system operations.
- Validate and normalise file paths.
- Apply appropriate file system permissions.

### Finding 11: OS Command Injection

**Vulnerability:** OS Command Injection

**Description:**

OS command injection occurs when an application passes untrusted user input into operating system commands without appropriate safeguards.

**Potential Impact:**

- Unauthorised command execution.
- Compromise of application server security.
- Exposure or modification of sensitive information.
- Potential disruption of services.

**Recommendations:**

- Avoid executing operating system commands when safer alternatives exist.
- Use secure application-level functions.
- Strictly validate required inputs.
- Apply allowlists for permitted values.
- Run application processes with minimum privileges.
- Monitor suspicious application and server activity.

---

## 5. Overall Security Analysis

The selected labs demonstrate several important principles of web application security.

### 5.1 Secure Input Handling

Applications must treat user input as untrusted. SQL injection, cross-site scripting, path traversal, and command injection demonstrate the risks associated with insecure input processing.

### 5.2 Authentication and Authorisation

Authentication verifies a user's identity, while authorisation determines what that user is permitted to access.

Both must be correctly enforced on the server side.

### 5.3 Secure Coding Practices

Developers should implement secure programming techniques, appropriate input validation, output encoding, parameterised queries, and safe application interfaces.

### 5.4 Continuous Security Testing

Regular penetration testing, vulnerability assessments, and secure code reviews can help identify weaknesses before they are exploited.

### 5.5 Security Monitoring

Organisations should monitor application activity, authentication events, and unusual access patterns to identify potential security incidents.

---

## 6. General Security Recommendations

Based on the vulnerability categories covered in this exercise, the following security measures are recommended:

1. Implement secure coding standards.
2. Use prepared statements for database queries.
3. Apply context-aware output encoding.
4. Enforce server-side authentication and authorisation.
5. Implement multi-factor authentication.
6. Apply least-privilege access controls.
7. Validate and restrict file access.
8. Avoid unsafe operating system command execution.
9. Conduct regular penetration testing.
10. Monitor application logs and suspicious activity.
11. Provide secure coding training for developers.
12. Maintain an effective vulnerability management process.

---

## 7. Skills and Knowledge Developed

This exercise helped develop foundational knowledge in:

- Identifying common web application vulnerabilities.
- Understanding SQL injection and database security.
- Recognising reflected, stored, and DOM-based XSS.
- Understanding authentication and access control weaknesses.
- Recognising path traversal and command injection risks.
- Evaluating potential security impacts.
- Developing practical remediation recommendations.
- Documenting technical findings in a structured security report.

---

## 8. Conclusion

This penetration testing training exercise explored 11 beginner-level web application security labs covering SQL injection, cross-site scripting, access control weaknesses, authentication flaws, path traversal, and OS command injection.

The exercises demonstrated how insecure application design and implementation can expose organisations to unauthorised access, information disclosure, and other security risks.

The most important security measures include proper input handling, secure authentication, server-side access control, safe database queries, and secure application development practices.

Regular penetration testing and security reviews can help organisations identify and address weaknesses before they are exploited.

The knowledge gained through this exercise contributes to developing foundational penetration testing skills and a stronger understanding of web application security.

---

## 9. Assessment Evidence and References

**Practical Training Platform:** PortSwigger Web Security Academy

**Training Resource:** https://portswigger.net/web-security

The practical exercises were completed within the authorised PortSwigger educational environment.

This report documents the vulnerability concepts explored, their potential security impacts, and recommended remediation measures.

**Evidence Note:** Screenshots were not captured for this submission.

**Project:** Commonwealth Bank Cybersecurity Virtual Experience

**Task:** 04 – Penetration Testing

**Report Type:** Web Application Penetration Testing Training Report
