# **Authentication Testing Guide**

Authentication vulnerabilities can compromise the security of an application by allowing unauthorized access or exposing sensitive data. Use this checklist to thoroughly test authentication mechanisms.

---

## **Checklist**

### **1. Username Enumeration**
- [ ] Test for username enumeration in login, registration, and password reset flows.

### **2. Two-Factor Authentication (2FA) Misconfiguration**
- [ ] Check for 2FA code leakage in responses.
- [ ] Test response manipulation (e.g., status code changes).
- [ ] Verify 2FA code integrity validation.

### **3. Response Manipulation**
- [ ] Analyze HTTP status codes and responses.

### **4. Password Management**
- [ ] Check for lack of password confirmation during sensitive actions:
  - Change email address.
  - Change password.
  - Manage 2FA.
- [ ] Test for usage of weak OTPs.
- [ ] Verify account lockout policy.
- [ ] Confirm rate limiting on OTP and password brute force attempts.

### **5. CAPTCHA Validation**
- [ ] Test for CAPTCHA bypass by overriding hidden client-side DOM elements or validation tokens.

### **6. Secure Transmission and Storage**
- [ ] Ensure user credentials are not stored in browser memory in clear text.
- [ ] Verify that user credentials are transmitted over SSL.

### **7. Weak Login Functions**
- [ ] Ensure only HTTPS is available (disable HTTP).
- [ ] Check password reset implementation for:
  - Reset token sent over HTTP.
  - Token invalidation after use.
  - Reset link expiration.
- [ ] Test password reset uniqueness.

### **8. Hardcoded Credentials**
- [ ] Identify and report any code flaws related to hardcoded credentials.

### **9. Redirect URI Validation**
- [ ] Validate redirect URIs for potential vulnerabilities:
  - [ ] Open redirection: `?redirect_uri=https://attacker.com`
  - [ ] Subdomain allowance: `?redirect_uri=https://sub.example.com`
  - [ ] Path validation issues: `?redirect_uri=https://example.com/callback?redirectUrl=https://evil.com`
  - [ ] Referer leakage via external content.

### **10. Session Management**
- [ ] Test for back-refresh attacks.
- [ ] Verify session invalidation on logout or password reset.
- [ ] Check reset link/code expiration policies.

### **11. Password Reset Flaws**
- [ ] Token should be invalidated after use.
- [ ] Test for link reactivation by altering parameters like date/time.
- [ ] Validate proper handling of blank or invalid passwords.
- [ ] Check for confirm password field bypass vulnerabilities.
- [ ] Test multiple reset requests to identify sequential tokens.

### **12. Rate Limiting Bypass**
- [ ] Use alternate user agents (e.g., mobile, anonymous).
- [ ] Test with null bytes or other bypass techniques.

### **13. Security Questions**
- [ ] Check for brute force attempts on security questions.
- [ ] Verify lockout policy after multiple failed guesses.

### **14. Login Methods**
- [ ] Assess weak password policies.
- [ ] Test for authentication bypass using vulnerabilities like SQLi.
- [ ] Verify TLS authentication.
- [ ] Test basic authentication.
- [ ] Check advanced protocols:
  - [ ] OAuth/JWT
  - [ ] SAML
- [ ] Ensure client_secret is validated.

### **15. Pre-ATO Checks**
- [ ] Verify email validation mechanisms.

### **16. Access Control**
- [ ] Check for unauthenticated access to confidential pages.
- [ ] Test multi-factor authentication (MFA) implementation.

### **17. Vulnerability Tests**
- [ ] Host-header injection.
- [ ] Usage of weak OTP.
- [ ] Improper session handling.

---

## **Best Practices**
- Test in a staging or authorized environment.
- Document all findings with steps to reproduce.
- Collaborate with developers for mitigation strategies.

---

## **Resources**
- [OWASP Authentication Cheat Sheet](https://owasp.org/www-project-cheat-sheets/cheatsheets/Authentication_Cheat_Sheet.html)
- [HackerOne Authentication Testing Resources](https://www.hackerone.com/education/authentication)
