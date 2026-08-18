# Risk Rating Methodology

Risk ratings are determined based on a combination of:

- **Likelihood:** Ease of exploitation and required attacker capability
- **Impact:** Potential effect on confidentiality, integrity, and availability
- A simplified CVSS-style Risk Scoring Model (To be integrated)

Ratings are qualitative and aligned with common penetration testing reporting practices.

<!--
## CVSS-Style Risk Scoring Model 

To standardize severity evaluation, a CVSS-inspired scoring model is used. 

This is a simplified adaptation of the CVSS v3.1 framework.

Each finding is evaluated across the following metrics:

### 1. Attack Vector (AV)
- Network (N): Exploitable remotely over wireless network
- Adjacent (A): Requires proximity to target network

### 2. Attack Complexity (AC)
- Low (L): No special conditions required
- High (H): Requires specific setup or timing

### 3. Privileges Required (PR)
- None (N): No authentication needed
- Low (L): Limited access required

### 4. User Interaction (UI)
- None (N): No user action required
- Required (R): User must perform an action (e.g., reconnect)

### 5. Impact (Confidentiality / Integrity / Availability)
- Low (L)
- High (H)
- None (N)

---

## Severity Interpretation

| Score Range | Severity |
|------------|----------|
| 0.1 – 3.9  | Low |
| 4.0 – 6.9  | Medium |
| 7.0 – 8.9  | High |
| 9.0 – 10   | Critical |
-->

---

# Findings

## Finding 1: Weak Password Susceptibility

**Description:**  
The wireless password was successfully recovered using a common wordlist.

**Risk Level:** Medium  
**Likelihood:** High  
**Impact:** High  

**Justification:**  
Weak or commonly used passwords are highly susceptible to dictionary-based attacks. Successful exploitation results in full unauthorized access to the wireless network.

**Business Impact:**  
Unauthorized access may lead to traffic interception, abuse of network resources, or pivoting to other connected systems.

---

## Finding 2: WPA/WPA2 Handshake Exposure

**Description:**  
Authentication handshakes can be captured and used for offline password attacks.

**Risk Level:** Medium  
**Likelihood:** Medium  
**Impact:** High  

**Justification:**  
Handshake capture is feasible for attackers within proximity. While exploitation depends on password strength, successful attacks allow unrestricted offline guessing without detection.

**Business Impact:**  
Attackers can repeatedly attempt credential recovery without interacting with the network, increasing the probability of compromise over time.

---

## Finding 3: Management Frame Vulnerability (Deauthentication)

**Description:**  
Deauthentication frames can be spoofed to disconnect clients from the network.

**Risk Level:** Medium  
**Likelihood:** High  
**Impact:** Medium  

**Justification:**  
Deauthentication attacks are of low priority to execute and require minimal resources. However, impact is typically limited to disruption unless combined with further attacks.

**Business Impact:**  
Frequent disconnections can impact service availability and may be used to facilitate more advanced attacks such as credential capture or rogue access points.