# Failed Login Analysis - SOC Perspective

## Scenario
A system shows multiple failed SSH login attempts from a single IP address targeting different usernames.

---

## Sample Logs
Failed password for invalid user admin from 192.168.1.10 port 22 ssh2
Failed password for invalid user root from 192.168.1.10 port 22 ssh2
Failed password for invalid user test from 192.168.1.10 port 22 ssh2

---

## Evidence

The following logs show repeated failed login attempts from the same IP address targeting multiple usernames.

This pattern indicates automated login attempts and possible brute-force behavior.

---

## Initial Observation
- Multiple authentication failures detected
- Same source IP address
- Different usernames targeted
- Activity occurred in a short time window

---

## Hypothesis
This behavior may indicate a brute-force or credential guessing attack.

---

## Analysis

### Pattern Recognition
- Repeated failures → automated attempts likely
- Username variation → attacker testing common accounts
- Same IP → single source attack

### Risk Assessment
- If a login succeeds → possible compromise
- If continues → attacker persistence

---

## Detection Logic

Trigger alert if:
- Failed login attempts exceed threshold
- Same IP involved
- Multiple usernames targeted

---

## Investigation Steps

1. Check authentication logs for successful login
2. Identify targeted accounts
3. Correlate with other system logs
4. Check for lateral movement indicators

---

## Response Actions

- Block or rate-limit source IP
- Monitor affected systems
- Escalate if compromise suspected

---

## Conclusion

The activity strongly aligns with brute-force attack patterns and requires immediate attention from the SOC team.
