##  Real SOC Operational Context

In a real Security Operations Centre (SOC), brute-force attacks are detected as part of continuous monitoring of authentication logs.

SOC analysts operate under strict SLAs where:

- Tier 1 analysts must triage alerts within minutes
- High-confidence brute-force attempts are escalated immediately to Tier 2
- Analysts must reduce false positives through correlation and context enrichment


## Alert Triage Decision Logic

Severity classification is based on:

- Low: 3–5 failed attempts (user error likely)
- Medium: 5–10 failed attempts (suspicious activity)
- High: 10+ attempts or multi-user targeting (confirmed attack pattern)

Escalation Rules:
- Tier 1 handles initial triage and validation
- Tier 2 handles deeper forensic analysis and containment


## Analyst Thinking Process

As a SOC analyst, the following questions guide investigation:

- Is this a user error or automated attack?
- Is the IP attempting multiple accounts?
- Is there a successful login after failures?
- Is this part of a wider attack campaign?


##  Real-World SOC Limitations

- High volume of authentication logs can lead to alert fatigue
- Attackers may use distributed IPs to bypass detection thresholds
- Legitimate users may trigger false positives


This project simulates a real SOC Tier 1 investigation and demonstrates practical experience in SIEM-based threat detection, log analysis, and incident response workflows.





##  Portfolio Value

This project demonstrates practical SOC Tier 1 capabilities including:

- SIEM-based threat detection
- Brute-force attack identification
- Log correlation and analysis
- Incident escalation decision-making
- Structured SOC reporting workflow
