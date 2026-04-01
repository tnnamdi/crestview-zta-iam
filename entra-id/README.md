# Microsoft Entra ID — Identity & Devices Pillar Configuration

## Overview

This folder documents Microsoft Entra ID configuration for Crestview Financial Group (CFG), combining live demonstration screenshots from a real enterprise tenant with a simulated Conditional Access policy representing what a CFG administrator would configure.

## Live Demonstration

Entra ID was accessed via a real enterprise tenant (Seneca College — 120,000+ users, 193,000+ devices, Microsoft Entra Connect enabled) to demonstrate the Identity and Devices pillars in a production-scale hybrid identity environment — directly analogous to CFG's on-premises + Azure hybrid architecture.

See `/screenshots/` for live environment screenshots.

## ZTA Pillar Alignment

**Identity Pillar:** Entra ID as the authoritative identity directory — unified identity plane for all on-premises and cloud access  
**Devices Pillar:** Device compliance enforcement as a condition of access — no unmanaged device is implicitly trusted

## Key Capabilities for CFG

| Capability | ZTA Function | Protect Surface Linkage |
|---|---|---|
| **Conditional Access** | Evaluates identity + device + location + risk before granting access | All layers — gates access to every CFG resource |
| **Privileged Identity Management** | JIT role elevation — no standing admin privilege | Assets + Services layers |
| **Identity Protection** | Risk-based detection of compromised identities | Identity layer — prevents credential compromise propagation |
| **Entra Connect** | Hybrid identity sync — on-premises AD to Azure | Services layer — unified identity for hybrid CFG environment |
| **Device Compliance** | Enforces endpoint security posture as access condition | Assets layer — employee and vendor endpoints |

## Simulated Configuration

See `conditional-access-policy.json` for a simulated Conditional Access policy representing CFG's core ZTA access control rule.
