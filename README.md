# Vulnerability Assessment Report: OWASP Juice Shop
## 📌 Project Overview
This repository contains a formal Vulnerability Assessment Report conducted on the OWASP Juice Shop, a purposefully insecure web application. The audit was performed as part of a professional development track to simulate a real-world security consulting engagement.
The primary goal was to identify security gaps, misconfigurations, and information leakages that could be leveraged by an adversary, while providing actionable remediation steps for the business owner.

## 🎯 Assessment Scope & Methodology
To ensure high service availability and adhere to ethical standards, this audit followed a Passive, Read-Only scope.
- Mode: Non-intrusive (No exploitation, no destructive actions).
- Focus: Infrastructure fingerprinting, Header analysis, and API Metadata exposure.

## Scope & Limitations Matrix
| CATEGORY       | IN-SCOPE                    | LIMITATIONS                  |
|----------------|-----------------------------------------|-------------------------------------------|
| Testing Depth  | Passive Reconnaissance & Observation    | Active Exploitation (SQLi, XSS payloads)  |
| Access Level   | Unauthenticated (Public view)           | Authenticated (User/Admin testing)        |
| Impact         | 100% Uptime Guaranteed                  | Intrusive scans or DoS simulations        |

## 🛠️ Tools Used
Industry-standard tools were utilized to gather intelligence and validate findings:
- Nmap: Used for network mapping, port identification, and banner grabbing.
- OWASP ZAP: Utilized in "Safe Mode" for passive traffic analysis and automated header auditing.
- Browser DevTools: Employed for manual inspection of client-side logs, security headers, and WebSocket handshakes.

## 🛡️ Key Findings Summary
A total of 6 security findings were documented, ranging from Informational to High Risk:
1. Exposed Administrative API Configuration (High): Unauthorized access to /rest/admin/application-configuration.
2. Missing Security Headers (Medium): Absence of HSTS and Content Security Policy (CSP).
3. Permissive CORS Policy (Medium): Wildcard * access-control-allow-origin header.
4. Information Leakage (Low): Infrastructure fingerprinting (Heroku/Amazon) and verbose console logs.

## 📜 Professional Disclaimer
*This project was conducted for educational purposes. All testing was performed under a strict passive scope to ensure no disruption to the target environment. No data was modified or compromised during this assessment.*
