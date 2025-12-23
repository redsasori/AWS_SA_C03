## AMAZON REDSHIFT – CORE CONCEPT
• Fully managed OLAP data warehouse
• Optimized for analytics, reporting, BI tools
• Uses SQL on structured data
• NOT for OLTP / transactional workloads

**REDSHIFT ARCHITECTURE** (EXAM FAVORITE)
• Leader Node – Query parsing & planning
• Compute Nodes – Parallel query execution (MPP)
• Columnar storage + compression

**SCALING & PERFORMANCE**
• Concurrency Scaling → near-unlimited concurrent users
• Elastic resize (add/remove nodes)
• Workload Management (WLM)

**HIGH AVAILABILITY & DR**
• Single-AZ by default
• RA3 Multi-AZ supports automatic AZ relocation (must be enabled)
• Automatic node replacement on failure
• Continuous backups to S3 (3 copies minimum)
• Automated backups: up to 35 days
• Manual snapshots for long-term retention
• Cross-region snapshot copy supported

## AMAZON REDSHIFT SPECTRUM (VERY EXAM-HEAVY)
• Query data directly in Amazon S3 without loading
• Supports structured & semi-structured data (CSV, Parquet, ORC, JSON)
• Serverless & auto-scales independently of cluster
• Uses AWS Glue / Athena Data Catalog

**HOW SPECTRUM WORKS**
1. Define external tables in Glue/Athena Catalog
2. Leader node creates execution plan
3. Spectrum scans S3 in parallel
4. Final joins happen in Redshift cluster

**SPECTRUM LIMITATIONS**
• Redshift cluster & S3 must be in same region
• External tables are read-only
• No UPDATE / DELETE on S3 data

**EXAM DECISION TRIGGERS**
• Analytics on structured data → Redshift
• Query S3 + Redshift together → Redshift Spectrum
• Simple ad-hoc S3 SQL → Athena (not Spectrum)
• Big data processing with Spark → EMR

**FINAL EXAM MEMORY HOOK**
Redshift = Warehouse
Spectrum = S3 extension of Redshift