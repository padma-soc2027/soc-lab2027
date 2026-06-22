# Detection 1: RDP Brute Force vs Windows 11
**Date**: 2026-06-22
**MITRE ATT&CK**: T1110.001 Password Guessing
**Tactic**: Credential Access
**Data Source**: Windows Security Event ID 4625
**Attacker IP**: 192.168.157.133
**Victim IP**: 192.168.157.128
**Target Account**: Administrator
**Logon Type**: 10 (RemoteInteractive/RDP)
**Failure Reason**: Unknown user name or bad password
**Tool Used**: Hydra 9.5

**Timeline**: 3 failed RDP logon attempts in ~10 seconds

**Raw Event 4625**:
PASTE YOUR EVENT DETAILS HERE LATER

**Analyst Note**: Logon Type 10 confirms this was an RDP brute force attempt. Source IP 192.168.157.133 belongs to Debian attacker VM. No account lockout policy detected.

**SOC L1 Recommendations**:
1. Enable account lockout after 5 failed attempts
2. Create SIEM alert: Count of Event ID 4625 >10 from single Source IP in 5 minutes
3. Block attacking IP at firewall after threshold
4. Disable Administrator account, use named accounts with MFA
