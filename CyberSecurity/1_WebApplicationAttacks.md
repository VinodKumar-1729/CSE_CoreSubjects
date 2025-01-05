

### **Web Application Attacks**

#### **1. Cross-Site Scripting (XSS)**
- **Definition**: XSS is a vulnerability that allows attackers to inject malicious scripts into web pages viewed by users.
- **Types**:
  - **Stored XSS**: Malicious script is permanently stored on the target server (e.g., in a database).
  - **Reflected XSS**: Malicious script is reflected off a web server, usually via URL parameters.
  - **DOM-Based XSS**: Script is executed due to client-side code, modifying the DOM.
- **How it works**:
  1. Attacker injects malicious JavaScript into a website.
  2. The script executes in the victim's browser, stealing cookies, session tokens, or performing actions as the user.
- **Mitigation**:
  - Sanitize and validate all inputs.
  - Use Content Security Policy (CSP).
  - Encode output (e.g., HTML, JavaScript).
  - Implement secure session handling.

---

#### **2. Cross-Site Request Forgery (CSRF)**
- **Definition**: CSRF exploits a user’s authenticated session to perform unwanted actions on their behalf.
- **How it works**:
  1. Victim is tricked into clicking a malicious link or visiting a page.
  2. The attack leverages the user’s credentials to perform unauthorized actions.
- **Impact**: Unauthorized fund transfers, password changes, or sensitive data exposure.
- **Mitigation**:
  - Use anti-CSRF tokens in forms.
  - Validate HTTP Referer headers.
  - Implement SameSite cookies.
  - Require re-authentication for critical actions.

---

#### **3. Injection Attacks**
- **Definition**: An attacker injects malicious input into a web application, altering its behavior.
- **Common Types**:
  - **SQL Injection**: Malicious SQL commands modify database queries.
  - **Command Injection**: Exploits system commands executed by the server.
  - **LDAP Injection**: Alters LDAP queries.
- **How it works**:
  - Attacker crafts input (e.g., `' OR '1'='1`) that manipulates queries or commands.
- **Impact**: Data theft, data manipulation, server compromise.
- **Mitigation**:
  - Use parameterized queries (e.g., Prepared Statements).
  - Validate and sanitize inputs.
  - Restrict database permissions.
  - Avoid concatenating user inputs with commands.

---

#### **4. Distributed Denial-of-Service (DDoS)**
- **Definition**: A DDoS attack overwhelms a web application or server with traffic, making it unavailable.
- **Types**:
  - **Volumetric Attacks**: Flood network bandwidth (e.g., UDP floods).
  - **Protocol Attacks**: Exploit server resources (e.g., SYN flood).
  - **Application Layer Attacks**: Target specific applications (e.g., HTTP GET/POST floods).
- **How it works**:
  - Botnets or multiple attackers send excessive requests to the target.
- **Impact**: Service downtime, reputation damage, revenue loss.
- **Mitigation**:
  - Use Web Application Firewalls (WAF).
  - Implement rate limiting and IP filtering.
  - Leverage Content Delivery Networks (CDNs).
  - Monitor and respond with DDoS mitigation services.

---

#### **5. Brute Force Attack**
- **Definition**: An attacker systematically tries all possible combinations of credentials to gain unauthorized access.
- **Types**:
  - **Traditional Brute Force**: Exhaustive attempts to guess passwords.
  - **Dictionary Attack**: Uses a precompiled list of possible passwords.
  - **Credential Stuffing**: Uses credentials obtained from other breaches.
- **How it works**:
  - Automated tools like Hydra or Burp Suite try credentials against login endpoints.
- **Impact**: Account compromise, unauthorized access.
- **Mitigation**:
  - Use strong passwords and enforce password policies.
  - Implement account lockout mechanisms.
  - Use CAPTCHA or multi-factor authentication (MFA).
  - Monitor and block IPs after repeated failed attempts.

---

### **General Security Best Practices**
1. **Keep software updated**: Patch known vulnerabilities.
2. **Use HTTPS**: Encrypt data in transit.
3. **Secure APIs**: Authenticate and validate requests.
4. **Educate developers**: Regular security training.
5. **Conduct regular security testing**: Vulnerability scans and penetration tests.

These notes provide a comprehensive understanding of the specified web application attacks and countermeasures.
