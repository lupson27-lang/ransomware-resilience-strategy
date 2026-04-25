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

*## Decision Log

### Decision 1: Escalation to Incident Response
- Situation: Suspicious login + PowerShell activity
- Decision: Trigger full incident response
- Reasoning: Indicators of credential compromise and lateral movement
- Risk: Possible business disruption
- Outcome: Early containment prevented ransomware deployment

### Decision 2: Prioritize Identity Containment
- Situation: Admin credentials compromised
- Decision: Lock down identity systems first
- Reasoning: Identity controls access to all systems including backups
- Outcome: Prevented attacker persistence and re-entry

### Decision 3: Protect Backup Infrastructure
- Situation: Backup server accessed
- Decision: Isolate backup systems and validate integrity
- Reasoning: Ensure recovery capability
- Outcome: Backups preserved and usable for recovery
