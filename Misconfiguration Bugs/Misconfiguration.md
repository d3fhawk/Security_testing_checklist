# **Misconfiguration Bugs**

## **Checklist**

### **1. Component Enumeration**
- [ ] Use Wappalyzer to enumerate components and identify vulnerabilities.

### **2. Information Disclosure**
- [ ] Check for information disclosure vulnerabilities.

### **3. Direct Reference to Resources**
- [ ] Verify no direct reference to sensitive resources.

### **4. Debug Mode**
- [ ] Ensure debug mode is disabled in production environments.

### **5. Common URLs**
- [ ] Test for commonly used application and administrative URLs.

### **6. Old and Backup Files**
- [ ] Check for old, backup, and unreferenced files.

### **7. HTTP Methods and Cross Site Tracing (XST)**
- [ ] Test supported HTTP methods.
- [ ] Check for Cross Site Tracing (XST) vulnerabilities.

### **8. File Extensions Handling**
- [ ] Verify secure handling of file extensions.

### **9. Security HTTP Headers**
- [ ] Test for missing or misconfigured HTTP headers (e.g., CSP, X-Frame-Options, HSTS).

### **10. Policy Testing**
- [ ] Test for policy misconfigurations (e.g., Flash, Silverlight, robots).

### **11. Non-Production Data**
- [ ] Check for non-production data in live environments and vice-versa.

### **12. Client-Side Sensitive Data**
- [ ] Check for sensitive data in client-side code (e.g., API keys, credentials).

### **13. SSL/TLS Configurations**
- [ ] Verify SSL version, algorithms, and key length.
- [ ] Check digital certificate validity (duration, signature, and CN).
- [ ] Ensure credentials are only delivered over HTTPS.

### **14. Login and Session Security**
- [ ] Verify the login form is delivered over HTTPS.
- [ ] Ensure session tokens are only delivered over HTTPS.
- [ ] Check if HTTP Strict Transport Security (HSTS) is in use.
- [ ] Test for password reset URLs delivered over insecure protocols.

### **15. CORS Misconfigurations**
- [ ] Check for misconfigured CORS policies (Origin, ACAO, ACAC headers).

### **16. Cross-Domain Script Inclusion**
- [ ] Test for cross-domain script inclusion vulnerabilities.

### **17. Email/Username Spoofing**
- [ ] Verify resistance against email/username spoofing via case sensitivity.

### **18. Internal IP Disclosure**
- [ ] Check for leaking internal IP addresses.

### **19. File Metadata Disclosure**
- [ ] Test for disclosure of sensitive metadata in files.
