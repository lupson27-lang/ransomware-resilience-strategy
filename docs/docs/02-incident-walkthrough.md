# Incident Walkthrough

## 1. Initial Compromise
A phishing email led to credential theft of a finance administrator account.

## 2. Detection
- Unusual VPN login from foreign location
- Suspicious PowerShell activity detected on a finance server

## 3. Lateral Movement
- Credential dumping attempts observed
- Access to multiple internal servers
- Privileged account misuse

## 4. Escalation Decision
A full incident response was triggered due to:
- Confirmed credential compromise
- Evidence of lateral movement
- Risk of ransomware deployment

## 5. Containment Strategy
- Disabled compromised accounts
- Isolated affected servers
- Restricted administrative access
- Secured backup infrastructure

## 6. Key Decision Points
- Early escalation to avoid silent spread
- Prioritization of identity containment
- Parallel protection of backup systems

## 7. Outcome
The attack was contained before full encryption, limiting impact and preserving recovery capability.
