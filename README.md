## Incident Investigation Report
**Date: June 7, 2026**
#
## Incident Information

| Field | Details |
|---------|---------|
| Incident Name | Identity - Potential Credential Stuffing Incident |
| Incident ID | 2017 |
| Severity | Medium |
| Status | Closed - No Successful Compromise Identified |
| Analyst | Mohammed Rashad Abdallah |


**Investigation Summary**

Between 2026-05-06 19:20:00 UTC and 2026-05-06 23:40:00 UTC, multiple failed authentication attempts targeted host mts-contractorpc1. 

The activity originated from two external IP addresses:

- 94.26.68.54 - Sofia-Grad, Bulgaria
- 80.85.28.26 - Athens-Attica, Greece

Both IP addresses attempted repeated logons using multiple guest account names. The authentication attempts were identified as suspicious due to:

- High authentication failure volume
- Use of multiple guest accounts
- Geographically inconsistent access location
- Threat intelligence reputation associated with phishing and brute-force activities

Enrichment through VirusTotal and AbuseIPDB identified both IPs as malicious and previously associated with phishing and Brute-Force activities.

The investigation confirmed that no successful authentication occurred during the observed timeframe. No evidence of privilege escalation, persistence, lateral movement, or execution activity was identified on the affected host.



**Scope of Investigation**

*Time Frame:* 

- Start Time: 2026-05-06 19:20:00 UTC
- End Time: 2026-05-06 23:40:00 UTC 

*Affected Asset:* 

- Hostname: mts-contractorpc1 

**Indicators of compromise (IOCs)** 

*IP Addresses:*
- 94.26.68.54 
- 80.85.28.26 

**Investigation Details**

**Detection Summary**

Multiple failed remote authentication attempts were identified against mts-contractorpc1. The activity involved attempted repeated logons using multiple guest account names from external IP addresses:

- 94.26.68.54 - Sofia-Grad, Bulgaria
- 80.85.28.26 - Athens-Attica, Greece

**MITRE ATT&CK Mapping**

| Technique ID | Technique |
|---------|---------|
| T1110.003 | Brute Force: Password Spraying |

**Investigation Findings**

**Authentication Activity**

Analysis of authentication logs identified repeated logon attempts originating from:

- 94.26.68.54 
- 80.85.28.26 

The activity uses multiple guest account names and continues throughout the investigation timeframe.

**Threat Intelligence Findings**

Threat intelligence enrichment using VirusTotal and AbuseIPDB identified both IP addresses as malicious and associated with phishing and brute-force activities.

**Negative Findings**

- No successful logons
- No evidence of account compromise
- No suspicious privilege escalation activity
- No persistence mechanisms created
- No lateral movement activity observed

**Impact Assessment**

At the time of investigation:
- No confirmed compromise was identified
- No successful authentication occurred
- No system confirmed impacted beyond authentication attempts

The activity is assessed as a failed brute-force logon attempt targeting remote authentication services.

**Response Actions Taken**

The following actions were performed during the investigation:

- Authentication logs were analysed for possible unauthorised successful logons on host mts-contractorpc1
- IOC enrichment conducted through VirusTotal and AbuseIPDB
- IP addresses were added to the blocklist to prevent further unauthorized access attempts. 
- Process event logs were analysed on host mts-contractorpc1 for possible malicious service or process creation beyond the incident time frame.
- Device event logs were analysed for possible malicious events on host mts-contractorpc1
- Network event logs were analysed for possible unauthorised remote logons on host mts-contractorpc1


**Recommendations**

- Enforce strong password policies with a minimum length of 10 characters, including uppercase and lowercase letters, numbers, and special characters. 
- Use multi-factor authentication. Where possible, also enable multi-factor authentication on externally facing services.
- Review and close unnecessary open ports exposed to external networks.
- Set up account lockout policies. 

**Conclusion**
 
The investigation identified repeated failed authentication attempts consistent with Password Spraying behaviour targeting  mts-contractorpc1.

Although the source IP addresses were associated with malicious activity, there was no evidence of successful compromise or post-authentication malicious activity during the investigation.

Continued monitoring and hardening of authentication controls are recommended to reduce future exposure.
