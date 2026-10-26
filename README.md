# Internal Network & Web Application Penetration Testing

**Cybersecurity Capstone Project | Vertex Digital Systems**

![Domain](https://img.shields.io/badge/Domain-Cybersecurity-blue)
![Focus](https://img.shields.io/badge/Focus-Penetration%20Testing-red)
![Environment](https://img.shields.io/badge/Environment-Controlled%20Lab-green)
![Status](https://img.shields.io/badge/Project-Educational-orange)

## 📌 Project Overview

This repository documents my cybersecurity capstone project focused on internal network and web application penetration testing in a controlled laboratory environment.

The project involved examining potential security weaknesses, performing reconnaissance, analysing vulnerable services, exploring selected web application vulnerabilities, assessing potential business impact, and developing practical remediation recommendations.

The assessment used intentionally vulnerable lab systems, including **Metasploitable 2** and **DVWA (Damn Vulnerable Web Application)**, to explore common attack scenarios and defensive security practices.

The objective was to understand how vulnerabilities can be identified, validated through authorised testing, prioritised according to risk, and addressed through effective remediation.

## 🎯 Project Objectives

- Perform internal network reconnaissance and service enumeration.
- Identify potential vulnerabilities in exposed network services.
- Assess selected web application security weaknesses.
- Explore authentication weaknesses, SQL injection, and Cross-Site Request Forgery (CSRF).
- Understand the potential impact of successful exploitation.
- Develop risk-based remediation recommendations.
- Document a structured penetration testing methodology.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Security testing environment |
| Nmap | Network discovery, port scanning, and service enumeration |
| Nessus | Vulnerability assessment during the earlier assessment phase |
| Burp Suite | HTTP request inspection and web application testing |
| Nikto | Web server security checks |
| Dirb | Web directory and endpoint discovery |
| WhatWeb | Web technology fingerprinting |
| DVWA | Intentionally vulnerable web application |
| Metasploitable 2 | Vulnerable target system for laboratory testing |

## 🧪 Laboratory Environment

The project used an isolated, controlled environment for educational security testing.

**Assessment machine:** Kali Linux

**Network target:** Metasploitable 2 virtual machine

**Web application target:** DVWA hosted in the laboratory environment

**Testing scope:**
- Network reconnaissance and service enumeration
- Selected network vulnerability validation
- Web application vulnerability testing
- Risk analysis and remediation planning

All testing should be performed only against systems for which explicit authorisation has been granted.

## 🔍 Assessment Methodology

The project followed a structured assessment workflow.

### 1. Planning and Scope Definition

- Identify the authorised laboratory targets.
- Establish testing boundaries and objectives.
- Confirm the laboratory network configuration.
- Define evidence-handling and safety requirements.

### 2. Reconnaissance and Enumeration

Network reconnaissance and service enumeration were performed using Nmap to identify reachable services and understand the target's potential attack surface.

Web application reconnaissance included technology fingerprinting, directory discovery, and web server checks using tools such as WhatWeb, Dirb, and Nikto.

### 3. Vulnerability Assessment

Nessus was used during the earlier vulnerability assessment phase to identify potential vulnerabilities and configuration weaknesses.

The previous assessment reported:

| Severity | Reported Findings |
|---|---:|
| Critical | 11 |
| High | 7 |
| Medium | 23 |
| Low | 9 |
| Informational | 130 |
| **Total recorded items** | **180** |

*These figures are from the earlier vulnerability assessment. They are scanner-reported findings, not a count of independently exploited vulnerabilities.*

### 4. Controlled Exploitation and Validation

The capstone explored selected network and web application weaknesses in the authorised laboratory environment.

Network-level scenarios documented in the project's analytical notes included:

- VSFTPD 2.3.4 backdoor
- UnrealIRCd backdoor

The notes record root-level access for these two scenarios.

The web application testing scope included:

- Authentication weaknesses and brute-force testing
- SQL injection
- Cross-Site Request Forgery (CSRF)

The specific success status and impact of each web application test should be reported only where supported by practical evidence.

### 5. Risk Analysis and Reporting

The final stage focused on translating technical observations into actionable security recommendations.

This included prioritising higher-risk findings, considering potential confidentiality and integrity impacts, recommending corrective controls, and defining retesting criteria.

## 🌐 Web Application Testing Areas

### Authentication Weaknesses

**Objective:** Examine authentication controls and the risks associated with repeated login attempts.

**Security considerations:**
- Password strength and reuse
- Login rate limiting
- Account lockout or risk-based controls
- Multi-factor authentication
- Monitoring of repeated authentication failures

**Recommended mitigation:** Implement appropriate rate limiting, strong unique passwords, multi-factor authentication for privileged accounts, and authentication monitoring.

### SQL Injection

**Objective:** Examine how unsafe handling of application input may affect database query behaviour.

**Potential impact:** Depending on the vulnerability and database permissions, SQL injection can expose records or permit unauthorised database operations.

**Recommended mitigation:**
- Use parameterised queries and prepared statements.
- Apply server-side input validation.
- Restrict database account permissions.
- Avoid exposing detailed database errors to users.

### Cross-Site Request Forgery (CSRF)

**Objective:** Explore the risk of unauthorised state-changing requests made through an authenticated user's browser.

**Recommended mitigation:**
- Implement unpredictable anti-CSRF tokens.
- Validate tokens on the server.
- Apply appropriate cookie protections, including SameSite settings.
- Validate request context where appropriate.

## 🖧 Internal Network Security

Internal network penetration testing examined the security implications of exposed services and selected vulnerable network components.

The project notes identify VSFTPD 2.3.4 and UnrealIRCd backdoor scenarios associated with root-level access in the laboratory.

These scenarios demonstrate the importance of:
- Removing unsupported or vulnerable services.
- Applying vendor security updates.
- Disabling unnecessary network services.
- Restricting access with host and network firewalls.
- Enforcing least privilege.
- Monitoring suspicious service and authentication activity.

The presence of a potentially vulnerable service should not automatically be treated as proof of successful exploitation. Findings should be linked to evidence from the relevant test.

## ⚠️ Risk Prioritisation

The earlier vulnerability assessment recommended the following response priorities:

| Severity | Recommended Response |
|---|---|
| Critical | Immediate review and remediation |
| High | Remediation within one week |
| Medium | Prioritise based on exposure and business context |
| Low | Address through planned maintenance |
| Informational | Review for relevant security or configuration insights |

Critical and High findings should be validated against the affected asset and available evidence before remediation decisions are finalised.

## 🛡️ Key Remediation Recommendations

The project identified several areas for improving security posture:

1. **Patch management:** Upgrade vulnerable and unsupported software.
2. **Network hardening:** Disable unnecessary services and restrict exposed ports.
3. **Authentication security:** Use strong passwords, rate limiting, and MFA where supported.
4. **Secure development:** Use parameterised database queries and appropriate CSRF protections.
5. **Least privilege:** Limit permissions assigned to user, service, and database accounts.
6. **Security monitoring:** Centralise logs and monitor suspicious authentication and administrative activity.
7. **Retesting:** Repeat relevant checks after remediation to verify that the original weakness is no longer reproducible.

## 📚 Key Learning Outcomes

Through this project, I developed and reinforced my understanding of:

- Network reconnaissance and service enumeration
- Vulnerability assessment and finding prioritisation
- Internal network and web application security testing
- Common authentication and input-handling weaknesses
- Privilege escalation risk in vulnerable laboratory services
- Business impact analysis and remediation planning
- Evidence-based reporting and post-remediation validation

One of the key lessons was the importance of distinguishing automated scanner output from vulnerabilities that have been successfully validated.

## 🔮 Future Improvements

Potential improvements to this project include:

- Adding sanitised terminal screenshots and test evidence.
- Documenting each validated finding with its impact and remediation.
- Mapping applicable findings to OWASP categories and relevant CWE references.
- Including a clear risk matrix based on documented evidence.
- Adding a remediation validation checklist.
- Recording retest outcomes for resolved findings.

## ⚖️ Disclaimer

This repository documents an educational cybersecurity capstone project conducted in a controlled laboratory environment.

Metasploitable 2 and DVWA are intentionally vulnerable systems intended for security training. Testing should only be performed in an isolated lab or against systems with explicit authorisation.

The findings and risk scenarios described here relate to the project environment and should not be interpreted as evidence of a real-world security incident at an organisation.

## 👩‍💻 Author

**Waheedah Olayiwola**

Cybersecurity | Penetration Testing | Network Security | Web Application Security

This project reflects my continued learning and practical development in cybersecurity.

