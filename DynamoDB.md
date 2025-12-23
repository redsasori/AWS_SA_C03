## What DynamoDB Is
Fully managed, serverless NoSQL key-value & document database.
Single-digit millisecond performance at any scale.
Automatically scales to millions of requests/sec.

**Core Characteristics** (EXAM FOCUS)
• Serverless (no servers, no VPC placement)
• Highly durable & multi-AZ by default
• Schema-less items (JSON-like)
• NOT relational (no joins, no foreign keys)

**Data Model**
• Table → Items → Attributes
• Primary Key:
– Partition key (required)
– Sort key (optional)
• Access patterns must be designed upfront

**Indexes** (VERY EXAM IMPORTANT)
LSI: Same partition key, different sort key (single partition queries)
GSI: Different partition & sort key (query across partitions)

**Capacity Modes**
Provisioned: Predictable traffic, RCU/WCU + Auto Scaling
On-Demand: Unpredictable or spiky traffic (no capacity planning)
Consistency Models
• Eventually consistent (default)
• Strongly consistent (same region only)
• Transactional reads & writes (ACID)

**DynamoDB Transactions**
• ACID across one or more tables
• All-or-nothing operations
• Up to 25 items / 4 MB per transaction
• NOT supported with Global Tables

**Global Tables** (MULTI-REGION)
• Active-active multi-region replication
• Writes allowed in any region
• Eventual consistency across regions
• Uses Streams + last-writer-wins

**DynamoDB Streams + Lambda**
• Captures item-level changes
• Triggers Lambda synchronously
• Stream views: KEYS_ONLY, NEW, OLD, BOTH

**TTL** (Time To Live)
• Automatically deletes expired items
• Reduces storage & cost

## DAX (DynamoDB Accelerator)
• In-memory cache for DynamoDB
• Microsecond reads (eventual consistency only)
• Best for read-heavy & bursty workloads
• NOT for strongly consistent reads

**Security**
• IAM-based access control
• Encryption at rest (KMS)
• Encryption in transit (TLS)
• VPC Gateway Endpoint (no public internet)

**Backups**
• PITR (continuous, last 35 days)
• On-Demand backups (manual)

**EXAM TRIGGERS – REMEMBER**
• Massive scale + low latency → DynamoDB
• Unpredictable traffic → On-Demand mode
• Multi-region active-active → Global Tables
• Microsecond reads → DAX
• Event-driven processing → Streams + Lambda