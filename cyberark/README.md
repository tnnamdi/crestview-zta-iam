# CyberArk PAM — Networks Pillar Configuration

## Overview

This folder contains simulated CyberArk Privileged Access Manager (PAM) configurations for Crestview Financial Group (CFG). CyberArk does not offer a free tier — these configurations document how CyberArk PAM would be deployed in a CFG ZTA environment.

## ZTA Pillar Alignment

**Primary Pillar:** Networks  
**Protect Surface:** Services layer (SWIFT payment network, core banking API gateway) + Assets layer (on-premises servers, HSMs)

## Why CyberArk is the Highest-Impact Control for CFG

The most catastrophic breach scenario for a financial institution is not a stolen customer record — it is a compromised privileged credential used to execute fraudulent transactions. The 2016 Bangladesh Bank heist demonstrated this precisely: attackers compromised SWIFT operator credentials and transferred $81 million USD before the fraud was detected.

CyberArk PAM eliminates standing privileged credentials entirely:

| Capability | What it does | CFG Application |
|---|---|---|
| **Credential Vaulting** | No operator holds a privileged password directly | SWIFT operators, DB admins, cloud admins |
| **Session Isolation** | Privileged sessions proxied — credentials never touch the endpoint | All admin sessions to CFG servers and HSMs |
| **Just-in-Time Access** | Access must be requested and approved before session starts | SWIFT operations, production DB access |
| **Session Recording** | Full tamper-evident audit trail of every privileged session | OSFI B-13 audit evidence |
| **Dual Approval** | SWIFT operations require a second authorized approver | Directly addresses Bangladesh Bank attack vector |

## Simulated Configurations

- `safe-policy.yaml` — SWIFT operator credential vault policy
- `jit-access-policy.yaml` — Just-in-time access workflow for database administrators

## Regulatory Alignment

- **OSFI B-13:** Session recording provides the audit capability and escalation evidence required by Sections 2.7.1 and 3.4
- **OSFI E-21:** JIT access limits the blast radius of any single compromised credential — reducing the likelihood a breach becomes a critical service disruption
- **FINTRAC:** Privileged session controls prevent unauthorized modification of AML transaction records without a reviewable audit trail
