# **Reconnaissance Guide**

Reconnaissance (Recon) is the first and most critical phase in the bug bounty process. It involves gathering as much information as possible about the target to identify potential vulnerabilities and attack vectors.

---

## **Objectives**
- Map out the target's assets.
- Identify potential entry points.
- Gather publicly available information to aid in testing.

---

## **Techniques**

### **1. Passive Recon**
   - Use open-source intelligence (OSINT) tools to gather data without interacting directly with the target.
   - Example tools:
     - [Google Dorking](https://www.exploit-db.com/google-hacking-database)
     - [Shodan](https://www.shodan.io/)
     - [Censys](https://censys.io/)

### **2. Active Recon**
   - Directly interact with the target system to collect information.
   - Example tools:
     - [Nmap](https://nmap.org/) - Network scanning.
     - [Sublist3r](https://github.com/aboul3la/Sublist3r) - Subdomain enumeration.
     - [WhatWeb](https://github.com/urbanadventurer/WhatWeb) - Web application fingerprinting.

### **3. Subdomain Enumeration**
   - Find subdomains to expand the attack surface.
   - Recommended tools:
     - [Amass](https://github.com/OWASP/Amass)
     - [Subfinder](https://github.com/projectdiscovery/subfinder)
     - [Assetfinder](https://github.com/tomnomnom/assetfinder)

### **4. Technology Stack Identification**
   - Identify the technologies and frameworks used by the target.
   - Tools:
     - [Wappalyzer](https://www.wappalyzer.com/)
     - [BuiltWith](https://builtwith.com/)

### **5. DNS Reconnaissance**
   - Collect DNS records for deeper insights.
   - Tools:
     - [Dig](https://linux.die.net/man/1/dig)
     - [DNSRecon](https://github.com/darkoperator/dnsrecon)

---

## **Tests to Perform**

- [ ] Debug Pages: Check for server-specific errors (e.g., SQL, PHP).
- [ ] Default Banners:
  - [ ] Analyze default banners using tools like Nmap.
  - [ ] Test using Netcat and Telnet.
- [ ] Technology Identification: Use Wappalyzer to understand components.
- [ ] Robots.txt: Analyze possible paths and directory listings.
- [ ] RSS Feeds: Explore for potential information leaks.
- [ ] Wayback Machine: Retrieve archived URLs for insights.
- [ ] Favicon Enumeration: Use fingerprint-based detection.
- [ ] Whois Lookup: Perform Whois enumeration for domain details.
- [ ] Shodan: Gather target-specific information.
- [ ] Subdomain Enumeration: Use tools like Sublist3r and Amass.
- [ ] Error Analysis: Check for directory names and file paths.
- [ ] Google Dorking: Discover exposed information.
- [ ] DNS Reverse Lookup: Map IPs back to domain names.
- [ ] Social Media Enumeration: Gather intelligence from public profiles.
- [ ] Admin Panel Analysis:
  - [ ] Use fuzzing to discover admin panels.
  - [ ] Check for username enumeration.
  - [ ] Perform parameter fuzzing.
  - [ ] Attempt forced navigation to admin pages.
- [ ] Directory Listing: Use brute-forcing tools to find hidden directories.
- [ ] Broken Link Hijacking: Identify and exploit orphaned links.
- [ ] TRACE/TRACK Methods: Check for hidden server headers.
- [ ] Exposed .git Directory: Test for GitHub enumeration.
- [ ] DNS Records Enumeration: Collect DNS records for detailed insights.
- [ ] Public Repositories: Look for exposed code repositories.
- [ ] Server Details: Identify server-specific configurations.
- [ ] Bucket Enumeration: Search for exposed cloud storage buckets.
- [ ] Known CVEs: Search for vulnerabilities associated with the target's technology.
- [ ] HTTP Methods: Analyze HTTP methods used by different APIs.
- [ ] Request/Response Headers: Review headers for sensitive information.
- [ ] Proxy/Firewall Detection: Check if any proxy or firewall is in place.
- [ ] JS File Analysis: Examine JavaScript files for sensitive information.

---

## **Best Practices**
- Always document findings meticulously for reference during later phases.
- Respect the scope and terms of the bug bounty program.
- Avoid overloading the target's infrastructure during active recon.

---

## **Resources**
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [HackerOne Recon Resources](https://www.hackerone.com/education/recon)

---
