# 1️⃣ Introduction

**Tester(s):**  
- Name: Toni Hautamäki 

**Purpose:**  
- Identify vulnerabilities in user registration flow.

**Scope:**  
- Tested components:  User registration
- Exclusions:  -
- Test approach: White-box

**Test environment & dates:**  
- Start:  18.11.2025
- End:  18.11.2025
- Test environment details: Windows 11 pro, Docker desktop, PostgreSQL, Google chrome

**Assumptions & constraints:**  
- Must be performed in self hosted environment

---

# 2️⃣ Executive Summary

**Short summary:**  
I ran baseline scan with ZAP to the given application which run in docker environment.

**Overall risk level:** High

**Top 5 immediate actions:**  
1.  Resolve path traversal vulnerabilities
2.  Resolve SQL injection vulnerabilities
3.  Deploy Anti-CSRF tokens
4.  Set Content Security Policy header
5.  Set Anti-clickjacking headers

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings

| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High | Path traversal possible | /register in url return `` | View ZAP report |
| F-02 | 🔴 High | SQL injection in registration | Input allows `'` and `AND 1=1`| View ZAP report |
| F-03 | 🟠 Medium | Anti-CSRF tokens missing | Registering doesn't use tokens | View ZAP report |
| F-04 | 🟠 Medium | CSP header not set | CSP headers missing | View ZAP report |
| F-05 | 🟠 Medium | Anti-clickjacking header missing | Anti-clickjacking headers missing | View ZAP report |


---

# 5️⃣ OWASP ZAP Test Report (Attachment)

**Purpose:**  
- [You can view round 1 ZAP report here](../zap_report_round1.md) and [round 2 ZAP report here](../zap_report_round2.md)

---
