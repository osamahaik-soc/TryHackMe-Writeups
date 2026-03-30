# Log Analysis Example - Failed Login Detection

## Scenario
Multiple failed login attempts from a single IP.

---

## Sample Logs
Failed password for invalid user admin from 192.168.1.10 port 22 ssh2
Failed password for invalid user root from 192.168.1.10 port 22 ssh2

---

## Analysis
- Repeated failed attempts
- Same source IP
- Possible brute-force attack

---

## Detection Logic
IF multiple failed logins from same IP → alert

---

## SOC Response
- Investigate logs
- Block IP if necessary
- Escalate if risk confirmed

---

## Conclusion
This activity indicates suspicious authentication behavior.
