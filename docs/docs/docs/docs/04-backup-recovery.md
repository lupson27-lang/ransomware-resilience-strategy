# Backup & Recovery Strategy

## Objectives
- Ensure system and data availability
- Minimize downtime (RTO)
- Minimize data loss (RPO)

## RTO / RPO Targets
- Identity systems: RTO 1 hour / RPO 15 minutes
- Critical applications: RTO 4 hours / RPO 1 hour
- File services: RTO 8 hours / RPO 4 hours

## Backup Layers

### Primary Backup
- Daily backups
- Short-term retention
- Operational recovery

### Immutable Backup
- Protected storage (WORM / object lock)
- Cannot be altered or deleted
- Protection against ransomware

### Offline / Air-Gapped Backup
- Physically or logically isolated
- Long-term retention
- Last-resort recovery option

## Restore Prioritization
1. Identity systems (authentication)
2. Core infrastructure (network, servers)
3. Business-critical applications
4. Supporting systems

## Key Risks Addressed
- Backup deletion by attackers
- Infected backups
- Delayed recovery capability
