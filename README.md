# 🧠 Windows Event Triage Labs

This repository contains hands-on security analyst exercises focused on Windows Security Event Log analysis. Each lab simulates a real-world incident where logs are reviewed to detect suspicious behavior such as brute-force attacks, account lockouts, and unauthorized admin access.

---

## 🔧 Tools Used

- Sample `.evtx` and `.csv` Windows Security logs
- Excel / Google Sheets (for parsing on macOS)
- MITRE ATT&CK Framework for mapping adversary techniques

---

## 📁 Folder Structure

windows-event-triage/
├── README.md
└── reports/
└── failed-logins-analysis.md


---

## 🧪 Included Reports

### ✅ [2025-07-12: Failed Logins & Account Lockout](./reports/failed-logins-analysis.md)
- Detected 5 failed login attempts and 1 lockout for user `jdoe`
- Source IP `192.168.1.45` targeted the account remotely (Logon Type 3)
- Admin user `svc_backup` logged in during off-hours
- Mapped activity to MITRE ATT&CK techniques T1110 and T1078

---

## 🎯 Objectives

- Practice incident triage using real Windows logs
- Identify malicious behavior in authentication events
- Write professional reports that mimic Tier 1–2 SOC workflows

---

## 🧠 About

This is part of an ongoing security analyst training portfolio to simulate daily SOC tasks, including log triage, threat detection, and report writing.

Created by Shavieair – Security Analyst  
GitHub: [@shavieb](https://github.com/shavieb)
