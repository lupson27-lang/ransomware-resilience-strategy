# Backup & Recovery Strategy

## Objectives
- Ensure data availability
- Minimize downtime (RTO)
- Minimize data loss (RPO)

## RTO / RPO Targets
- Identity systems: RTO 1h / RPO 15min
- Critical applications: RTO 4h / RPO 1h

## Backup Layers
- Primary backup (daily)
- Immutable backup (protected storage)
- Offline backup (air-gapped)

## Restore Prioritization
1. Identity systems
2. Core infrastructure
3. Business applications
