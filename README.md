# GRC Compliance Automation Tool

> **ISO 27001 & NIST CSF gap analysis in 6 hours instead of 40 — 85% time reduction · Validated against 2 mock audit scenarios**

![Python](https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python)
![ISO 27001](https://img.shields.io/badge/ISO-27001-blue?style=flat-square)
![NIST CSF](https://img.shields.io/badge/NIST-CSF-navy?style=flat-square)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green?style=flat-square&logo=pandas)
![Excel](https://img.shields.io/badge/Excel-Report%20Output-brightgreen?style=flat-square)

---

## What It Does

A Python-based compliance tracking tool that automatically maps organisational security controls to ISO 27001 and NIST CSF requirements. Generates gap analysis reports with risk-prioritised remediation roadmaps — replacing a 40-hour manual audit process with a 6-hour automated workflow.

Built from real experience leading ISO 27001 gap analyses for 2 client organisations at Coincent, identifying 28 compliance gaps across 150+ endpoints.

---

## Impact

| Metric | Result |
|--------|--------|
| Gap analysis time | Reduced from 40 hours → 6 hours **(85% reduction)** |
| Frameworks supported | ISO 27001, NIST CSF |
| Clients validated against | 2 mock audit scenarios |
| Compliance gaps identified | 28 gaps across 150+ endpoints (real engagement) |
| Remediation items tracked | 100% on-time SLA reporting (Jira integration) |

---

## Features

- **Automated control mapping** — input your existing controls, tool maps them to ISO 27001 Annex A and NIST CSF subcategories automatically
- **Gap analysis report** — identifies missing controls, partial implementations, and non-conformities
- **Risk scoring** — quantitative and qualitative scoring using CVSS-style criticality + business impact
- **Remediation roadmap** — prioritised action plan with effort estimates and owner assignment
- **Excel & PDF output** — executive dashboard + detailed findings report
- **Jira integration** — auto-creates remediation tickets with SLA tracking
- **Policy templates** — starter templates for information security policy, risk treatment plan, vendor assessment questionnaire

---

## Architecture

```
Input: Control Inventory (CSV/Excel)
           │
           ▼
┌─────────────────────────────┐
│   Control Mapping Engine    │
│                             │
│  ISO 27001 Annex A          │
│  NIST CSF (5 Functions)     │
│  CIS Controls (optional)    │
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Gap Analysis Engine       │
│                             │
│  • Missing controls         │
│  • Partial implementations  │
│  • Non-conformities         │
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│   Risk Scoring Module       │
│                             │
│  • Quantitative risk score  │
│  • Business impact weight   │
│  • Remediation priority     │
└────────────┬────────────────┘
             │
             ▼
Output: Gap Report (PDF) + Remediation Tracker (Excel) + Jira Tickets
```

---

## Quick Start

```bash
git clone https://github.com/chythrabandaru/grc-compliance-tool
cd grc-compliance-tool
pip install -r requirements.txt

# Run gap analysis against ISO 27001
python main.py --input controls/my-controls.csv --framework iso27001 --output reports/

# Run against NIST CSF
python main.py --input controls/my-controls.csv --framework nist-csf --output reports/

# Run against both frameworks
python main.py --input controls/my-controls.csv --framework all --output reports/
```

### Input Format

Prepare your control inventory as a CSV:

```csv
control_id,control_name,description,status,owner,last_reviewed
AC-001,Access Control Policy,Documented policy for access management,Implemented,CISO,2024-10-01
AC-002,Privileged Access Management,MFA enforced for all admin accounts,Partial,IT Team,2024-09-15
```

---

## Sample Output

### Gap Analysis Summary

```
Framework: ISO 27001:2022
Organisation: [Your Org]
Assessment Date: 2024-11-01

Total Controls Required: 93
Controls Implemented:     65 (70%)
Controls Partial:         14 (15%)
Controls Missing:         14 (15%)

Risk Score: HIGH (62/100)
Priority Remediation Items: 8
```

### Remediation Roadmap (excerpt)

| Control | Gap | Risk | Priority | Effort | Owner |
|---------|-----|------|----------|--------|-------|
| A.8.2 Information Classification | Missing policy | Critical | P1 | 3 days | CISO |
| A.9.4 System Access Control | No MFA on critical systems | High | P1 | 5 days | IT |
| A.12.6 Technical Vulnerability Mgmt | No vuln scan process | High | P2 | 7 days | SecOps |

---

## Policy Templates

`/templates/` includes starter documents aligned to ISO 27001 and NIST CSF:

- `information-security-policy.docx` — master IS policy template
- `risk-treatment-plan.xlsx` — risk register and treatment tracker
- `vendor-assessment-questionnaire.xlsx` — third-party risk assessment
- `acceptable-use-policy.docx` — AUP template
- `incident-response-policy.docx` — IR policy framework

---

## Professional Context

Developed from experience as GRC & Vulnerability Management Intern at Coincent, where I:
- Led ISO 27001 gap analysis for 2 client organisations, identifying 28 compliance gaps
- Conducted vulnerability assessments across 150+ endpoints using Nessus and OpenVAS
- Drafted security policy documentation aligned to NIST CSF and ISO 27001
- Maintained vulnerability tracking in Jira with 100% on-time SLA reporting

---

## Author

**Chythra Bandaru** — GRC Analyst | Cybersecurity Professional  
[LinkedIn](https://linkedin.com/in/chythrabandaru) · [GitHub](https://github.com/chythrabandaru)
