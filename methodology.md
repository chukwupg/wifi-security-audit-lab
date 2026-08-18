# Methodology

This assessment follows a structured wireless testing approach inspired by:

- NIST SP 800-115 (Technical Guide to Information Security Testing)
- OWASP Testing principles (adapted for wireless environments)

---

## 1. Reconnaissance

- Identified wireless interfaces
- Scanned for nearby networks
- Collected:
  - BSSID
  - ESSID
  - Channel
  - Encryption type
  - Connected clients

---

## 2. Target Identification

- Selected authorized access point
- Identified associated client device
- Scoped testing to controlled environment only

---

## 3. Traffic Monitoring

- Enabled monitor mode
- Captured 802.11 traffic
- Focused on target AP channel

---

## 4. Handshake Acquisition

- Triggered client reconnection via controlled deauthentication
- Captured WPA/WPA2 4-way handshake

---

## 5. Validation

- Verified handshake integrity using Aircrack-ng
- Confirmed viability for offline analysis

---

## 6. Credential Testing

- Performed offline password recovery
- Used wordlist-based attack methodology

---

## 7. Analysis

- Evaluated:
  - Password strength
  - Protocol exposure
  - Management frame weaknesses

---

## 8. Reporting

- Documented findings
- Assigned risk levels
- Provided remediation strategies

---

## Assumptions & Limitations

- WPA2 network without PMF enforcement
- Password-based authentication (no enterprise auth)
- Attack requires physical proximity
- Results depend heavily on password strength