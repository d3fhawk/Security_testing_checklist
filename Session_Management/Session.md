# **Session Management Bugs**

## **Checklist**

### **1. Sensitive Information Disclosure**
- [ ] Test for sensitive information passing through cookies.

### **2. Cookie Flags**
- [ ] Check for cookies without the `HttpOnly` flag.
- [ ] Check for cookies without the `Secure` flag set.
- [ ] Check for cookies without `Domain` or `SameSite` flags.

### **3. Insecure Session Timeout**
- [ ] Test for insecure session timeout configurations.

### **4. Session Variable Randomness**
- [ ] Verify randomness in session variables.

### **5. Critical Operation Check**
- [ ] Ensure session ID is required for all critical operations.

### **6. Fixed Session Cookie Value**
- [ ] Check for fixed session cookie values before and after authentication.

### **7. Session Reuse**
- [ ] Verify if a pool of cookies is used for session (cookie reuse).

### **8. Logout and Cookie Reusability**
- [ ] Check for cookie existence and reusability after logout.

### **9. Attack Vectors**
- [ ] Test for hash extension attacks.
- [ ] Test for byte padding attacks (oracle).
- [ ] Test for bit flipping attacks in cookies.

### **10. Active Session Handling**
- [ ] Verify if active sessions are destroyed upon changing the password or updating the email.

### **11. Session ID in URLs**
- [ ] Check if session IDs are exposed in URLs.

### **12. Session ID Consistency**
- [ ] Check if the session ID is the same before and after login.
