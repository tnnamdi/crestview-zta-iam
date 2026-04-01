# SailPoint IdentityNow — Data & Applications Pillar Configuration

## Overview

This folder contains simulated SailPoint IdentityNow configurations for Crestview Financial Group (CFG). SailPoint does not offer a meaningful free tier for hands-on demonstration — these configurations document how IdentityNow would be deployed in a CFG ZTA environment, written to reflect real enterprise configuration logic based on SailPoint's documentation and industry practice.

## ZTA Pillar Alignment

**Primary Pillar:** Data  
**Secondary Pillar:** Applications & Workloads  
**Protect Surface:** Data layer (customer PII, KYC/AML, transaction data) + Applications layer (all three CFG applications)

## Why SailPoint for CFG

In a regulated financial institution, the most dangerous long-term risk is not an external attacker — it is privilege accumulation. Over time, employees change roles, take on temporary projects, and acquire access entitlements that are never revoked. A long-tenured CFG employee may accumulate access to customer PII, transaction modification capabilities, and SWIFT reporting functions simultaneously — creating an insider threat profile that bypasses all perimeter controls.

SailPoint IdentityNow addresses this through:

| Capability | What it does | CFG Application |
|---|---|---|
| **Joiner-Mover-Leaver** | Automated provisioning on hire, role change, and termination | All CFG employees and vendors |
| **Access Certifications** | Periodic review requiring business owner confirmation of each entitlement | Quarterly for all privileged roles |
| **Separation of Duties** | Policy preventing dangerous entitlement combinations | Prevents any user from approving + executing transactions |
| **Least-Privilege Roles** | Role definitions scoped to minimum required access | See `role-definition.yaml` |
| **Access Request** | Self-service access requests with approval workflows | Replaces informal email-based access requests |

## Simulated Configurations

- `role-definition.yaml` — Least-privilege role definition for a CFG bank teller
- `access-certification.yaml` — Quarterly access certification campaign configuration

## Regulatory Alignment

- **OSFI B-13:** SailPoint's access governance framework directly satisfies B-13's requirement for formal processes to identify, assess, and manage technology access risks
- **PIPEDA:** Role-based data access ensures customer PII is accessible only through policy-enforced, audited paths
- **FINTRAC:** Access certifications create an auditable record of who had access to AML transaction data and when
