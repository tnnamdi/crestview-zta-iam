# Okta / Auth0 — Identity Pillar Configuration

## Overview

This folder documents the Okta Workforce Identity configuration simulated for Crestview Financial Group (CFG), with live demonstration screenshots from an Auth0 developer tenant.

Auth0 is an Okta product. The Auth0 free developer tier was used to demonstrate real, configurable ZTA Identity pillar controls in a live environment.

## ZTA Pillar Alignment

**Pillar:** Identity  
**Protect Surface:** Applications layer (digital banking portal, core banking, wealth management) + Services layer (identity verification)

## What Was Configured (Live)

| Control | Setting | ZTA Justification |
|---|---|---|
| MFA Policy | Always | Per-session verification — no implicit trust from prior sessions |
| Adaptive Risk Assessment | Enabled | Every login scored and recorded — supports anomaly detection |
| Suspicious IP Throttling | Enabled | Protects against credential stuffing at the application layer |
| Brute-force Protection | Enabled | Prevents automated password attacks against CFG user accounts |
| Application Type | Single Page Application | Represents CFG's customer-facing digital banking portal |

## Screenshots

See `/screenshots/` folder:
- `01-cfg-application.png` — CFG Digital Banking Portal registered in Auth0
- `02-mfa-always-policy.png` — MFA Policy set to Always
- `03-adaptive-risk-assessment.png` — Risk Assessment enabled
- `04-attack-protection.png` — Attack protection controls active

## Simulated MFA Policy Configuration

See `mfa-policy.json` for the documented policy configuration in JSON format, representing how this policy would appear in the Okta API or exported configuration.

## In a CFG Production Deployment

In a full CFG deployment, Okta Workforce Identity would additionally be configured with:
- **SAML/OIDC SSO** integrations for all three CFG applications
- **Okta Verify** push notification MFA for employees
- **Step-up authentication** policies for high-risk transactions
- **API Access Management** for the core banking API gateway
- **Lifecycle Management** integration with SailPoint IdentityNow for automated provisioning
