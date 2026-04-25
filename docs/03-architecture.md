# Resilience Architecture

## Design Principles
- Assume breach
- Least privilege
- Network segmentation
- Backup isolation
- Defense in depth

## Key Components

### Identity Layer
- Centralized authentication (Active Directory / Azure AD)
- MFA enforcement
- Conditional access

### Network Segmentation
- Separation of user, application, and data networks
- Restricted administrative access paths

### Backup Architecture
- Primary backups (daily)
- Immutable backups (ransomware protection)
- Offline backups (air-gapped)

### Disaster Recovery
- Secondary site / cloud region
- Replication of critical systems

## Key Risk Scenario

If identity systems are compromised:
- Attackers can access all systems
- Backups can be deleted
- Recovery becomes unreliable

Mitigation:
- MFA enforcement
- Privileged access isolation
- Backup system separation
  
“Loss of backup integrity would prevent recovery, leading to extended business outage.”

## Example Tools

### Identity & Access
- Active Directory / Azure AD
- MFA solutions

### Endpoint & Detection
- Microsoft Defender for Endpoint
- CrowdStrike / SentinelOne

### Monitoring
- SIEM (Splunk, ELK)
- Log analysis tools

### Backup & Recovery
- Veeam
- Commvault

### Network Security
- Firewalls
- IDS/IPS systems
