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
