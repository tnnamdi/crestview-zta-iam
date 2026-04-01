# CFG Regulatory Control Mapping

## Overview

This document maps CFG's ZTA controls to specific regulatory obligations under OSFI B-13, OSFI E-21, PIPEDA, FINTRAC, and PCI-DSS.

## OSFI Guideline B-13 — Technology and Cyber Risk Management (eff. Jan 1, 2024)

| B-13 Requirement | ZTA Control | Tool |
|---|---|---|
| Formal technology & cyber risk management framework | Pillar-based ZTA architecture with documented controls | All four tools |
| Governance and risk management — formal accountability | Access governance with ownership assignment | SailPoint |
| Continuous access verification | Per-session MFA + Conditional Access | Okta + Entra ID |
| 24-hour incident reporting capability | Session recording + SIEM integration | CyberArk + Entra ID |
| Third-party risk management | Vendor lifecycle + guest access policies | SailPoint + Entra ID |
| Cyber security response with escalation paths | Privileged session monitoring + alerting | CyberArk |
| Periodic testing and exercises | Access certification campaigns | SailPoint |

## OSFI Guideline E-21 — Operational Resilience (full adherence Sept 1, 2026)

| E-21 Requirement | ZTA Control | Tool |
|---|---|---|
| Identify critical operations | DAAS protect surface mapping | Framework (documented) |
| Set maximum downtime tolerances | Blast radius limitation via JIT and segmentation | CyberArk + SailPoint |
| Regular scenario-based testing | Access certification + privileged access review | SailPoint + CyberArk |
| Senior leadership accountability | Role-based governance with escalation paths | SailPoint |
| Business continuity for critical services | Device compliance reduces endpoint-borne disruption | Entra ID |

## PIPEDA — Personal Information Protection and Electronic Documents Act

| PIPEDA Obligation | ZTA Control | Tool |
|---|---|---|
| Access limited to those with demonstrated need | Least-privilege role definitions | SailPoint |
| Breach notification for significant harm | Risk detection + Identity Protection alerts | Entra ID |
| Privacy by design | Data-level access governance baked into role design | SailPoint |
| Accountability for personal information | Audit trails for all data access events | CyberArk + Okta |

## FINTRAC — Financial Transactions and Reports Analysis Centre of Canada

| FINTRAC Obligation | ZTA Control | Tool |
|---|---|---|
| AML record integrity | Privileged session controls prevent unauthorized modification | CyberArk |
| Transaction record auditability | Session recording provides tamper-evident audit trail | CyberArk |
| Access to AML data restricted | SoD policy explicitly excludes teller role from KYC/AML access | SailPoint |
| Suspicious transaction reporting integrity | Dual-approval workflow for privileged financial operations | CyberArk |

## PCI-DSS — Payment Card Industry Data Security Standard

| PCI-DSS Requirement | ZTA Control | Tool |
|---|---|---|
| Restrict access to cardholder data | Least-privilege roles + access certifications | SailPoint |
| Assign unique ID to each person with computer access | Identity governance + SSO | Entra ID + Okta |
| Restrict physical access | Device compliance policies | Entra ID |
| Track and monitor all access to network resources | Session recording + audit logs | CyberArk + Okta |
| Regularly test security systems | Access certification campaigns + penetration testing alignment | SailPoint |
| Maintain MFA for all admin access | Privileged role MFA enforcement | Entra ID CA-003 |
