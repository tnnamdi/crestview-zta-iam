# CFG Threat Model — Zero Trust Architecture Context

## Overview

This document outlines the primary threat categories facing Crestview Financial Group (CFG) and maps each threat to the ZTA control that mitigates it. The protect surface defined in Assignment 6 was informed by this threat analysis.

## Threat Categories

### 1. Credential Compromise
**Risk level:** Critical  
**Target:** Identity layer — employee and privileged accounts  
**Attack vectors:** Phishing, credential stuffing, password spraying, breached credential reuse  
**Real-world precedent:** Majority of financial sector breaches begin with a compromised credential  
**ZTA Control:** Entra ID Conditional Access + Okta Adaptive MFA — stolen credentials alone are insufficient without device compliance and MFA factor

### 2. Privileged Account Abuse
**Risk level:** Critical  
**Target:** Services layer — SWIFT network, core banking API, HSMs  
**Attack vectors:** Insider threat, compromised admin session, lateral movement from initial access  
**Real-world precedent:** 2016 Bangladesh Bank heist — $81M USD via compromised SWIFT operator credentials  
**ZTA Control:** CyberArk PAM — credential vaulting, JIT access, dual approval, session recording

### 3. Privilege Accumulation (Insider Threat)
**Risk level:** High  
**Target:** Data layer — customer PII, KYC/AML records, transaction data  
**Attack vectors:** Long-tenured employee accumulating access across role changes without systematic review  
**Real-world precedent:** Common pattern in financial services fraud investigations  
**ZTA Control:** SailPoint IdentityNow — access certifications, SoD enforcement, automated deprovisioning

### 4. Compromised Endpoint
**Risk level:** High  
**Target:** Assets layer — employee endpoints, especially hybrid/remote workforce  
**Attack vectors:** Malware, ransomware, unpatched OS, unmanaged vendor device  
**Real-world precedent:** Most common initial access vector across all sectors  
**ZTA Control:** Entra ID device compliance — non-compliant devices blocked from all CFG resources

### 5. API Abuse
**Risk level:** High  
**Target:** Applications layer — digital banking portal, core banking API gateway  
**Attack vectors:** Broken object-level authorization, credential stuffing via API, session token theft  
**Real-world precedent:** Growing attack vector as financial institutions expose more APIs  
**ZTA Control:** Okta API Access Management + Auth0 attack protection (IP throttling, brute-force protection)

### 6. Supply Chain / Third-Party Risk
**Risk level:** Medium-High  
**Target:** All layers — vendor access to CFG systems  
**Attack vectors:** Compromised vendor credential, over-permissioned vendor account, vendor software compromise  
**Real-world precedent:** SolarWinds, MOVEit — third-party as attack vector into enterprise environments  
**ZTA Control:** SailPoint governance (vendor lifecycle) + Entra ID guest access policies + CyberArk vendor session recording

## Threat-to-Pillar Mapping

| Threat | Primary Pillar | Secondary Pillar | Tools |
|---|---|---|---|
| Credential Compromise | Identity | Devices | Entra ID + Okta |
| Privileged Account Abuse | Networks | Identity | CyberArk + Entra ID PIM |
| Privilege Accumulation | Data | Applications | SailPoint |
| Compromised Endpoint | Devices | Identity | Entra ID |
| API Abuse | Applications | Identity | Okta + Auth0 |
| Third-Party Risk | Identity | Networks | SailPoint + CyberArk |
