**Penetration Testing Report**

**Commonwealth Bank Cybersecurity Virtual Experience**

**Task: 04 – Penetration Testing**

**Testing Platform: PortSwigger Web Security Academy**

**Assessment Type: Beginner-Level Web Application Security Testing**

**1. Executive Summary**

This report documents a penetration testing training exercise conducted using PortSwigger Web Security Academy.

The objective of this exercise is to identify and understand common web application vulnerabilities within a safe, legal, and controlled training environment.

The assessment covers 11 beginner-level web security labs across several vulnerability categories, including SQL injection, cross-site scripting, access control weaknesses, authentication vulnerabilities, path traversal, and OS command injection.

These vulnerabilities represent common security weaknesses that can affect real-world web applications when user input, authentication, authorisation, and server-side functionality are not implemented securely.

The findings demonstrate how security weaknesses may allow unauthorised access, exposure of sensitive information, manipulation of application behaviour, or execution of unintended actions.

Recommendations are included to explain how organisations can reduce the likelihood and impact of similar vulnerabilities.

**2. Overview of the Web Application Tested**

PortSwigger Web Security Academy is an online learning platform that provides free educational resources and practical web security labs.

The platform allows learners to understand common web application vulnerabilities and practise identifying them within authorised training environments.

For this assessment, 11 beginner-level labs were selected to explore different categories of web application security weaknesses.

The purpose of the exercise is to understand the vulnerabilities, their potential impact, and the security controls that can prevent them.

**3. Scope of Testing**

The scope of this assessment is limited to the selected PortSwigger Web Security Academy training labs.

All testing activities must remain within the authorised training environment.

Vulnerabilities included in scope
SQL Injection
Reflected Cross-Site Scripting
Stored Cross-Site Scripting
DOM-Based Cross-Site Scripting
Access Control Vulnerabilities
Authentication Vulnerabilities
Username Enumeration
Two-Factor Authentication Weaknesses
Path Traversal
OS Command Injection
Out of scope
Real-world banking systems.
Third-party websites and applications.
Systems outside the authorised training environment.
Unauthorised access to external networks or accounts.

**4. Vulnerability Findings and Recommendations**

The following sections document the 11 vulnerability areas selected for this exercise.

Important: Findings should be updated to reflect the actual results and evidence from each completed lab.

**Lab 1: SQL Injection – Login Bypass**

**Vulnerability: SQL Injection**

**Description:**

SQL injection occurs when an application incorporates untrusted user input into database queries without appropriate safeguards.

In a login function, this weakness may allow an attacker to manipulate authentication-related database queries.

**Potential Impact:**

Unauthorised account access.
Authentication bypass.
Exposure of sensitive information.

**Recommendations:**

Use parameterised queries and prepared statements.
Avoid constructing SQL queries directly from user input.
Apply appropriate server-side input validation.
Use database accounts with limited privileges.
Monitor suspicious authentication activity.

**Lab 2: SQL Injection – Hidden Data Exposure**

**Vulnerability: SQL Injection**

**Description:**

Applications that process user-controlled input in database queries without proper protection may expose information that should remain restricted.

**Potential Impact:**

Unauthorised access to database records.
Exposure of confidential information.
Compromise of data confidentiality.

**Recommendations:**

Implement prepared statements.
Apply server-side input validation.
Restrict database account privileges.
Use secure error handling.
Conduct regular database security reviews.

**Lab 3: Reflected Cross-Site Scripting**

**Vulnerability: Reflected XSS**

**Description:**

Reflected cross-site scripting occurs when an application includes untrusted user input in a webpage response without appropriate output encoding.

This may allow malicious scripts to execute in another user's browser.

**Potential Impact:**

Unauthorised actions within a user's session.
Exposure of sensitive browser-accessible information.
Manipulation of webpage content.

**Recommendations:**

Apply context-aware output encoding.
Validate user input.
Avoid unsafe handling of untrusted content.
Implement an appropriate Content Security Policy.
Use secure cookie attributes.

**Lab 4: Stored Cross-Site Scripting**

**Vulnerability: Stored XSS**

**Description:**

Stored cross-site scripting occurs when an application saves untrusted user content and later displays it to other users without appropriate protection.

**Potential Impact:**

Malicious script execution in users' browsers.
Exposure of sensitive information.
Compromise of user sessions.

**Recommendations:**

Apply context-aware output encoding.
Validate submitted content.
Sanitise permitted HTML using trusted libraries.
Use a suitable Content Security Policy.
Review user-generated content handling.
Lab 5: DOM-Based Cross-Site Scripting

**Vulnerability: DOM-Based XSS**

**Description:**

DOM-based cross-site scripting occurs when client-side JavaScript processes untrusted data using unsafe browser APIs.

This demonstrates that security controls must cover both front-end and back-end application functionality.

**Potential Impact:**

Unintended JavaScript execution.
Manipulation of webpage content.
Exposure of information accessible to the browser.

**Recommendations:**

Use safe DOM APIs.
Avoid unsafe insertion of untrusted data into webpages.
Apply appropriate output encoding.
Validate data before processing it.
Review client-side JavaScript for insecure coding practices.

**Lab 6: Unprotected Admin Functionality**

**Vulnerability: Broken Access Control**

**Description:**

Administrative functionality may be exposed when an application does not properly verify whether a user has permission to access privileged features.

**Potential Impact:**

Unauthorised administrative access.
Unintended changes to application settings.
Exposure or modification of sensitive information.

**Recommendations:**

Enforce server-side authorisation checks.
Apply role-based access control.
Follow the principle of least privilege.
Protect administrative functions with appropriate authentication.
Log and monitor privileged activities.

**Lab 7: Hidden Admin Functionality**

**Vulnerability: Improper Access Control**

**Description:**

Sensitive administrative functionality may be discoverable through application information or navigation clues.

Hiding a sensitive URL does not provide effective security if the application fails to enforce authorisation.

**Potential Impact:**

Unauthorised access to administrative features.
Exposure of sensitive application functionality.
Potential misuse of privileged operations.

**Recommendations:**

Enforce server-side access control on every sensitive route.
Require appropriate authentication and authorisation.
Avoid relying on hidden URLs as a security measure.
Regularly review access permissions.
Test administrative functionality for access control weaknesses.

**Lab 8: Username Enumeration**

Vulnerability: Authentication Information Disclosure

**Description:**

Username enumeration occurs when an application provides different responses depending on whether a submitted username exists.

This may help attackers identify valid accounts.

**Potential Impact:**

Identification of valid user accounts.
Increased risk of targeted password attacks.
Greater exposure to credential-based attacks.

**Recommendations:**

Use consistent authentication error messages.
Implement rate limiting.
Monitor repeated authentication failures.
Apply appropriate account protection measures.
Use multi-factor authentication.

**Lab 9: Two-Factor Authentication Bypass**

Vulnerability: Authentication Workflow Weakness

**Description:**

An authentication process may contain weaknesses if it does not correctly enforce the second authentication factor before granting access.

**Potential Impact:**

Unauthorised account access.
Reduced effectiveness of MFA.
Compromise of sensitive account information.

**Recommendations:**

Enforce MFA verification on the server side.
Validate every authentication stage.
Prevent access before all required checks are completed.
Protect authentication tokens and sessions.
Monitor suspicious authentication activity.
Lab 10: File Path Traversal

**Vulnerability: Path Traversal**

**Description:**

Path traversal occurs when an application uses user-controlled input to access files without properly restricting access to approved directories.

**Potential Impact:**

Exposure of sensitive files.
Unauthorised access to application resources.
Disclosure of configuration information.

**Recommendations:**

Restrict file access to approved directories.
Use allowlists for permitted files.
Avoid passing raw user input directly into file system operations.
Validate and normalise file paths.
Apply appropriate file system permissions.
Lab 11: OS Command Injection

**Vulnerability: OS Command Injection**

**Description:**

OS command injection occurs when an application passes untrusted user input into operating system commands without appropriate safeguards.

**Potential Impact:**

Unauthorised command execution.
Compromise of application server security.
Exposure or modification of sensitive information.
Potential disruption of services.

**Recommendations:**

Avoid executing operating system commands when safer alternatives exist.
Use secure application-level functions.
Strictly validate any required inputs.
Apply allowlists for permitted values.
Run application processes with minimum privileges.
Monitor suspicious application and server activity.

**5. Overall Analysis**

The selected vulnerability categories demonstrate several important principles of web application security.

**5.1 User Input Validation**

Applications must treat user input as untrusted. SQL injection, cross-site scripting, path traversal, and command injection demonstrate the risks associated with insecure input processing.

**5.2 Authentication and Authorisation**

Authentication verifies a user's identity, while authorisation determines what that user is permitted to access.

Both must be enforced correctly on the server side.

**5.3 Secure Coding Practices**

Developers should use secure programming techniques, appropriate input validation, output encoding, parameterised queries, and safe application interfaces.

**5.4 Continuous Security Testing**

Regular penetration testing, vulnerability assessments, and secure code reviews can help identify weaknesses before they are exploited.

**5.5 Security Monitoring**

Organisations should monitor application activity, authentication events, and unusual access patterns to identify potential security incidents.

**6. General Security Recommendations**

Based on the vulnerability categories covered in this exercise, the following security measures are recommended:

Implement secure coding standards.
Use prepared statements for database queries.
Apply context-aware output encoding.
Enforce server-side authentication and authorisation.
Implement multi-factor authentication.
Apply least-privilege access controls.
Validate and restrict file access.
Avoid unsafe operating system command execution.
Conduct regular penetration testing.
Monitor application logs and suspicious activity.
Provide secure coding training for developers.
Maintain an effective vulnerability management process.

**7. Conclusion**

This penetration testing training exercise explores common web application vulnerabilities, including SQL injection, cross-site scripting, access control weaknesses, authentication flaws, path traversal, and OS command injection.

These vulnerabilities demonstrate how insecure application design and implementation can expose organisations to unauthorised access, information disclosure, and other security risks.

The most important security measures include proper input handling, secure authentication, server-side access control, safe database queries, and secure application development practices.

Regular penetration testing and security reviews can help organisations identify and address weaknesses before they are exploited.

The knowledge gained through this exercise contributes to developing foundational penetration testing skills and a stronger understanding of web application security.

**8. Appendix – Evidence of Lab Completion**

Screenshots should be added as evidence after successfully completing each PortSwigger training lab.

**Appendix	Lab	Evidence**
A	SQL Injection – Login Bypass	Screenshot pending
B	SQL Injection – Hidden Data Exposure	Screenshot pending
C	Reflected Cross-Site Scripting	Screenshot pending
D	Stored Cross-Site Scripting	Screenshot pending
E	DOM-Based Cross-Site Scripting	Screenshot pending
F	Unprotected Admin Functionality	Screenshot pending
G	Hidden Admin Functionality	Screenshot pending
H	Username Enumeration	Screenshot pending
I	Two-Factor Authentication Bypass	Screenshot pending
J	File Path Traversal	Screenshot pending
K	OS Command Injection	Screenshot pending

Evidence location: evidence/

Project: Commonwealth Bank Cybersecurity Virtual Experience

Task: 04 – Penetration Testing

Platform: PortSwigger Web Security Academy

Report Type: Web Application Penetration Testing Training Report
