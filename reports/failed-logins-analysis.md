# 🧠 Windows Event Log Triage – July 12, 2025

## 🧾 Incident Summary

Received an alert of multiple failed login attempts on a Windows workstation. Analyzed Event Logs to validate and investigate the behavior for signs of brute force or unauthorized access.

---

## 🔍 Findings

- **Event ID 4625 – Failed Logon**
  - User: `jdoe`
  - Count: 5 attempts in under 3 minutes
  - Source IP: `192.168.1.45`
  - Logon Type: `3` (Network logon — possibly RDP or remote tool)
  - Failure Reason: `Unknown user name or bad password`

- **Event ID 4740 – Account Lockout**
  - User: `jdoe`
  - Time: 10:25 AM

- **Event ID 4672 – Admin Logon**
  - User: `svc_backup`
  - Time: 2:13 AM (outside normal working hours)

---

## 🎯 MITRE ATT&CK Mapping

- **T1110 – Brute Force**
- **T1078 – Valid Accounts**
- **T1071.001 – Application Layer Protocol: Web (if remote logon was via HTTP/RDP)**

---

## ✅ Recommendations

- Reset the password for user `jdoe` and verify MFA enrollment
- Investigate IP `192.168.1.45` for any lateral movement
- Review the `svc_backup` admin account's actions (especially given odd login time)
- Create SIEM rule to trigger alerts for:
  - 5+ failed logins within 5 minutes from the same IP
  - Event ID 4740 followed by successful admin login

---

## 📘 Final Disposition

Confirmed brute-force login attempt. No successful compromise detected. Affected user was notified and credentials reset. Admin activity reviewed and verified as scheduled backup process.

