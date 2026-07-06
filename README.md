# FUTURE_CS_01 — Vulnerability Assessment Report for a Live Website

**Internship:** Future Interns – Cyber Security Track
**Task:** Task 1 – Vulnerability Assessment Report for a Live Website
**Intern:** Abinash Reddy

---

## 📌 Project Overview

This repository documents a **passive, read-only vulnerability assessment** conducted on publicly authorized test targets as part of the Future Interns Cyber Security internship. The goal was to identify common web application security weaknesses, classify their risk, and present findings in a clear, business-friendly report — the same way a junior security analyst would communicate results to a client.

## 🎯 Scope

| Item | Detail |
|---|---|
| Web Target | `http://zero.webappsecurity.com` (public demo banking app, authorized for security testing) |
| Network Target | `scanme.nmap.org` (Nmap's official permitted scanning target) |
| Testing Type | Passive / read-only only — **no exploitation, no login bypass, no active attack payloads** |
| Tools Used | Nmap · OWASP ZAP (passive scan) · Browser DevTools |

## 🛠️ Methodology

1. **Network Reconnaissance** — Nmap service/version scan to identify open ports and software versions.
2. **Passive Web Application Scan** — OWASP ZAP (Manual Explore mode) to passively record and analyze requests/responses while browsing the site.
3. **Manual Header & Cookie Review** — Browser DevTools used to independently verify HTTP response headers and cookie security attributes.

## 🔍 Key Findings

| # | Finding | Risk |
|---|---|---|
| 1 | Outdated JavaScript Library (jQuery 1.6.4 / 1.7.2 / 1.8.2) | Medium |
| 2 | Missing Content Security Policy (CSP) Header | Medium |
| 3 | Missing Anti-Clickjacking Header (X-Frame-Options) | Medium |
| 4 | Absence of Anti-CSRF Tokens | Medium |
| 5 | Unencrypted Transport (HTTP instead of HTTPS) | Medium |
| 6 | Server Version Disclosure | Low |
| 7 | Session Cookie Missing Secure & SameSite Attributes | Low |
| 8 | Missing X-Content-Type-Options Header | Low |

**Full details, business impact, and remediation steps** for each finding are in the report: [`report/Task-1 Assessment Report.pdf`](./report/Task-1%20Assessment%20Report.pdf)

## 📂 Repository Structure

```
FUTURE_CS_01/
├── README.md
├── report/
│   └── Task-1 Assessment Report.pdf      → Full vulnerability assessment report
├── evidence/
│   ├── nmap_scan.png                     → Nmap scan output
│   ├── zap_alerts_overview.png           → ZAP alerts summary
│   ├── zap_vulnerable_js.png             → ZAP finding detail
│   ├── zap_csp_header.png                → ZAP finding detail
│   ├── zap_clickjacking.png              → ZAP finding detail
│   ├── zap_csrf.png                      → ZAP finding detail
│   ├── zap_server_version_leak.png       → ZAP finding detail
│   ├── zap_cookie_samesite.png           → ZAP finding detail
│   ├── zap_content_type_options.png      → ZAP finding detail
│   ├── devtools_headers.png              → Browser DevTools header check
│   └── devtools_cookies.png              → Browser DevTools cookie check
└── scan-output/
    └── nmap_output.txt                   → Raw Nmap scan output
```

## ⚠️ Disclaimer

All testing in this repository was conducted **strictly within a passive, read-only scope** against **publicly designated, authorized test domains**. No exploitation, credential attacks, or active scanning was performed at any point. This work was completed solely for educational purposes as part of the Future Interns Cyber Security internship program.

## 🔗 Internship Program

[Future Interns](https://www.linkedin.com/company/future-interns/) — Cyber Security Track
