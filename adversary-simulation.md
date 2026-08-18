# Adversary Simulation Workflow

## Phase 1: Environment Preparation
- Identify wireless interface
- Kill conflicting processes
- Enable monitor mode

## Phase 2: Reconnaissance
- Scan wireless networks
- Identify target AP and client

## Phase 3: Target Monitoring
- Lock onto AP channel
- Capture traffic

## Phase 4: Handshake Capture
- Trigger reconnection via deauthentication
- Capture WPA handshake

## Phase 5: Validation
- Confirm handshake presence
- Validate capture file integrity

## Phase 6: Offline Attack
- Prepare wordlist
- Execute password recovery

## Phase 7: Verification
- Confirm recovered credentials

---

## Attack Flow Summary

Recon - Identify - Monitor - Deauth - Capture - Crack - Validate

---

## MITRE ATT&CK Mapping

This assessment simulates adversary behavior aligned with the MITRE ATT&CK framework.

| Phase | Activity | Technique | Technique ID |
|------|---------|----------|-------------|
| Reconnaissance | Wireless network discovery | Active Scanning | T1595 |
| Reconnaissance | Identify access point and clients | Gather Victim Network Information | T1590 |
| Resource Development | Wordlist preparation | Obtain Capabilities | T1588 |
| Initial Access (Simulated) | WPA handshake capture for credential attack | Valid Accounts (conceptual) | T1078 |
| Credential Access | Offline password cracking | Brute Force | T1110 |
| Impact / Disruption | Deauthentication attack | Network Denial of Service | T1498 |

---

## Notes on Mapping

- WPA handshake capture enables **offline credential attacks**, aligning with brute-force techniques.
- Deauthentication reflects **availability disruption**, mapped to DoS behavior.
- Targeted wordlist preparation involves using **OSINT** to gather information about a target which could then be used to populate possible passwords, alligning with obtaining capabilities.
- This lab simulates adversary capability without unauthorized access.