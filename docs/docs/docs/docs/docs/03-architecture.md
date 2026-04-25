# Resilience Architecture

## Design Principles
- Assume breach
- Least privilege
- Network segmentation
- Backup isolation
- Defense in depth

## Architecture Overview
The architecture is designed to limit attack spread, protect critical systems, and ensure recovery capability.

## Identity Layer
- Centralized authentication (Active Directory / Azure AD)
- Multi-Factor Authentication (MFA)
- Conditional access policies
- Privileged access restrictions

## Network Segmentation
- Separation of user, application, and data networks
- Restricted communication between segments
- Dedicated administrative access paths

## Core Systems
- Application servers
- Databases
- File storage systems

## Backup Architecture
- Primary backups (daily operational backups)
- Immutable backups (protected from modification/deletion)
- Offline / air-gapped backups (isolated from network)

## Disaster Recovery
- Secondary site or cloud region
- Replication of critical systems
- Defined failover procedures
