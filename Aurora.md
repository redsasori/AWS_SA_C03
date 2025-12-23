## AMAZON AURORA – KEY DIFFERENCES
AWS-built relational DB (MySQL & PostgreSQL compatible).
Higher performance & lower replication lag than RDS.
Storage auto-scales from 10 GiB to 128 TiB.

**AURORA ARCHITECTURE**
• Cluster-based (writer + replicas)
• Data replicated 6 copies across 3 AZs
• Up to 15 Aurora Replicas per cluster

**AURORA ENDPOINTS**
• Cluster (writer)
• Reader (load-balanced reads)
• Custom & instance endpoints

**AURORA SERVERLESS**
• Auto-start, auto-scale, auto-stop DB
• Uses ACUs (~2 GB memory each)
• Best for sporadic & unpredictable workloads
• VPC-only (no public IP)
• Not supported: Global DB, replicas, IAM auth, Performance Insights

**AURORA GLOBAL DATABASE**
• Multi-region Aurora
• Up to 5 secondary regions
• Replication latency < 1 sec
• RPO ≈ 1 sec | RTO ≈ 1 min

**EXAM TRIGGERS**
• Managed relational DB → RDS
• HA within region → RDS Multi-AZ
• Read scaling → Read Replicas
• High performance → Aurora
• Unpredictable usage → Aurora Serverless
• Global low-latency DB → Aurora Global DB