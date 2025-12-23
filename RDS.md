## AMAZON RDS – WHAT IT IS
Managed relational database service (shared responsibility).
AWS manages backups, patching, HA; you manage DB config & scaling.

**Supported engines**: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora.

**RDS vs EC2 DATABASE** (EXAM TRAP)
• RDS: No OS/DB login, managed backups & patching
• EC2 DB: Full control, high operational overhead

**RDS CONFIGURATION**
• Choose instance type & storage
• Scale vertically as needed
• DB Parameter Groups & Option Groups replace config files
• Maintenance window user-defined

**RDS HIGH AVAILABILITY**
Single-AZ: One DB instance
Multi-AZ: Primary + standby in different AZ (SYNC replication)
• Standby not readable
• Automatic failover with DNS update

**RDS READ REPLICAS**
• ASYNC replication (eventual consistency)
• Used for read-heavy workloads
• Same or cross-region supported
• Manual promotion possible
• Does NOT cache data

**RDS PROXY**
• Managed DB proxy
• Improves scalability & failover handling

**RDS SECURITY** (EXAM IMPORTANT)
• Private subnets recommended
• SG + NACL + VPN/WAF
• Encryption at rest (KMS, AES-256) – enabled at creation only
• Encryption in transit (SSL/TLS)
• IAM DB authentication (Aurora only)