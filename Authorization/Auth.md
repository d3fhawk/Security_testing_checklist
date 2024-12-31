# **Authorization Testing Guide**

Authorization testing aims to identify weaknesses in the mechanisms that manage and enforce access control policies. The objective is to ensure that users can only access resources they are authorized to view or modify.

---

## **Tests to Perform**

### **File Access**
- [ ] Check for Path Traversal/LFI: Attempt to access unauthorized files.
- [ ] Test for Remote File Inclusion (RFI).

### **Authorization Bypass**
- [ ] Bypassing Authorization Schema:
  - [ ] Forced browsing for configuration or sensitive files and directories.

### **Privilege Escalation**
- [ ] Check for Privilege Escalation:
  - [ ] Account takeover of non-admin users.
  - [ ] Cross-user identity compromise.
- [ ] Direct Access to Unauthorized Resources:
  - [ ] Unauthorized access to bulk or specific data.

### **Access Control**
- [ ] Check for gaps in Role-Based Access Control (RBAC).
- [ ] Test for Insecure Direct Object References (IDOR).
- [ ] Verify if one user can:
  - [ ] Read other users' resources.
  - [ ] Write to other users' resources.
- [ ] Direct access to unauthorized APIs/URLs.

### **Business Logic**
- [ ] Perform Business Logic Checks.

### **OAuth Testing**
- [ ] Open Redirection.
- [ ] Access token in URL.
- [ ] Access token over an insecure channel.
- [ ] Access token leaked from authorization server DB.
- [ ] Client secret over an insecure channel.
- [ ] Client secret leaked from authorization server DB.
- [ ] Guess client secret.
- [ ] Authorization code over an insecure channel.
- [ ] Authorization code leaked from authorization server DB.
- [ ] Client obtains scope without end-user authorization.
- [ ] Refresh token over an insecure channel.
- [ ] Refresh token leaked from authorization server DB.
- [ ] Replay attack.
- [ ] Information disclosure in logs or HTTP headers.

### **CSRF Testing**
- [ ] Check for CSRF bypass by changing the request method (GET).
- [ ] Replace attacker-generated token with victim token for POC.
- [ ] Remove the token from the header and test if bypass occurs.
- [ ] Check for the randomness of the token (possibly guessable).

### **JWT Testing**
- [ ] Weak Cryptographic Algorithm.
- [ ] Lack of Request Integrity Check.
- [ ] Session Token Tampering.
- [ ] Secret Key Brute Forcing.
- [ ] JWT KID Injection Attack.
- [ ] JWT KID Directory Traversal.
- [ ] JWT KID Tampering.
- [ ] JWT JKU Tampering.
- [ ] Publicly Exposed Keys in /.well-known/jwks.json.
- [ ] JWT Expiration Timeout Lacking.
- [ ] Set different parameters to null to test bypass.
- [ ] Algorithm Confusion Attack.
- [ ] Modify `cty` to attempt an XXE attack.

### **State Flaws**
- [ ] Missing State Parameter? (CSRF).
- [ ] Predictable State Parameter?
- [ ] Is State Parameter Being Verified?

### **Sensitive Operations**
- [ ] Create a list of user-account-specific features to test:
  - [ ] Change Email.
  - [ ] Change Password.
  - [ ] Update account details (e.g., Name, Number, Address).
- [ ] Test CSRF for these features.
- [ ] Change email ID and update it with an existing email ID:
  - [ ] Check if the validation occurs server-side.
  - [ ] Verify if the application sends a confirmation link to the new email.
  - [ ] Observe the behavior if the confirmation link is not used within a specific timeframe.
- [ ] Check account deletion options and validate through the "Forgot Password" feature.
- [ ] Change email ID, account ID, or user ID parameters and brute force other users' credentials.
- [ ] Identify user account ID parameters and tamper with them to:
  - [ ] Change another user's password.
  - [ ] Modify other users' account details.

### **Password Reset**
- [ ] Test if there is a UID in the reset password feature (cross-user testing).
- [ ] Verify if the reset password URL expires appropriately.

### **Other Checks**
- [ ] Validate proper implementation of revoking access or deactivating user accounts.
- [ ] Confirm appropriate data segregation based on user roles.
- [ ] Verify the correct configuration of security-related settings.

---

## **Best Practices**
- Always respect the scope and terms of the bug bounty program.
- Document findings with detailed steps to reproduce and mitigation recommendations.
- Report high-impact vulnerabilities promptly to the responsible party.

---

## **Resources**
- [OWASP Authorization Testing Guide](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/07-Authorization_Testing)
- [HackerOne OAuth Checklist](https://www.hackerone.com/education/oauth-checklist)

---
