# Incident Walkthrough
This simulation reflects real-world constraints including limited visibility, time pressure, and the need to balance security with business continuity.

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

  ** What I Would Do in Real Life:
  
  ## Practical Actions
  
- Disable compromised accounts in identity provider
- Isolate affected systems via EDR
- Block suspicious IP addresses
- Review authentication logs
- Validate backup integrity and restore points

## Technical Analysis

### Detection (Logs & Indicators)

**Authentication Logs (Example)**
User: finance-admin
Source IP: 185.XXX.XXX.12
Location: Unusual (Eastern Europe)
Status: Successful login after multiple failures

**PowerShell Activity**
Command: Invoke-Mimikatz
Command: Get-Process lsass
Command: New-PSSession -ComputerName SERVER01

Indicators:
- Unusual geolocation login
- Credential dumping behavior
- Remote session creation
---
### Investigation Commands

I used the following commands to investigate suspicious activity:

**Check logged-in users**
query user

**Check active connections to identify suspicious outbound traffic**
netstat -ano

**Inspect running processes for malicious activity**
tasklist

**PowerShell process inspection**
Get-Process | Where-Object {$_.ProcessName -like "powershell"}

---

### Containment Actions

**Disable compromised account (Active Directory)**
Disable-ADAccount -Identity "finance-admin"

**Force password reset**
Set-ADAccountPassword -Identity "finance-admin"

**Isolate host (example concept)**
- Use EDR tool to isolate endpoint from network

**Block malicious IP (firewall)**
netsh advfirewall firewall add rule name="Block Malicious IP" dir=in action=block remoteip=185.XXX.XXX.12

---

### Backup Verification

**Check backup jobs**
- Review backup logs in backup system (e.g., Veeam)

**Validate restore point**
- Attempt test restore of critical system

---

### Recovery Actions

**Restore priority**
1. Identity systems
2. Core infrastructure
3. Business applications

**Example restore validation**
- Verify system boots
- Verify authentication works
- Verify data integrity
## Decision Log

### Decision 1: Escalation to Incident Response
- Situation: Suspicious login + PowerShell activity
- Decision: I triggered full incident response
- Reasoning: Indicators of credential compromise and lateral movement
- Tradeoff: Risk of business disruption vs risk of silent spread
- Outcome: Early containment prevented ransomware deployment

### Decision 2: Identity Containment
- Situation: Admin credentials likely compromised
- Decision: I prioritized securing identity systems first
- Reasoning: Identity controls access to all systems including backups
- Tradeoff: Immediate access disruption for users
- Outcome: Prevented attacker persistence and re-entry

### Decision 3: Backup Protection
- Situation: Backup server accessed
- Decision: I isolated backup infrastructure and validated integrity
- Reasoning: Ensure recovery capability before encryption phase
- Tradeoff: Temporary backup service interruption
- Outcome: Backups preserved and usable for recovery
