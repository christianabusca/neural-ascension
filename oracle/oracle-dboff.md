# Oracle Database Offerings

---

## Overview of Oracle Database Deployment Options
- **On-premise**: Customer manages everything (infrastructure + database)  
- **Database Cloud Services (DBCS)**: Co-managed service - Oracle manages infrastructure, customer manages database  
- **Autonomous Database (ADB)**: Fully managed service - Oracle manages both infrastructure and database  
- **Exadata Cloud Service**: Available as deployment option  
- **Third-party cloud**: Also available  

---

## Autonomous Database (ADB) - Core Concept

### What is ADB?
- Fully managed service - Oracle handles all infrastructure and database management  
- Eliminates tedious DBA chores and implements best practices automatically  
- Significantly lower cost compared to traditional deployments  

### When to Use Co-managed vs Fully Managed
- **Co-managed (DBCS) recommended for:**
  - Customers not yet on Oracle 19c  
  - Running packaged applications like E-Business Suite  
- **Fully managed (ADB) recommended for:** all other use cases  

---

## Cost Analysis & TCO Studies  

### Wikibon Research Findings
- Compared costs of running Oracle databases across different platforms:  
  - **On-premise**: Baseline cost  
  - **Amazon RDS**: Same cost as on-prem OR 50% higher (with disaster recovery/multizone)  
  - **Autonomous Transaction Processing (ATP)**: Almost 50% less than on-premise cost  

### Key Cost Benefits of ADB
- Lower total cost of ownership through automation  
- Higher productivity and less downtime  
- Elimination of manual DBA tasks  
- Best-practice configurations included  

---

## Migration Process to ADB  

### Step 1: Assessment Tool
- Oracle provides analysis tool for current on-premise databases  
- Identifies unsupported features/configurations:  
  - Pre-19c releases  
  - Database tables in system/sys schema  
  - Other rare edge cases  

### Step 2: Data Migration (Manual Process)
1. Use Data Pump export to extract data from on-premise database  
2. Upload exported data to Oracle Cloud Object Store  
3. Use Data Pump import to load data into ADB  
4. Migration complete  

### Step 3: Database Migration Service (Automated)
- New automated service available  
- Point to source database (on-premise or other cloud)  
- Oracle handles entire migration automatically  
- Eliminates manual steps from Step 2  

### Existing Tuning Preservation
- DBAs can preserve existing tuning and indexes if desired  
- Not required to use ADB's autotuning capabilities  

---

## Application Certification & Support  

### Oracle Packaged Applications
- **Already Certified:** JD Edwards, PeopleSoft, Siebel  
- **In Progress:** E-Business Suite (EBS) - expected next year  

### Fully Managed Application Stack
- Oracle manages **both middle tier and database tier**  
- Database moves to ADB, Oracle handles the rest  

### Third-Party Applications
Certified partners include:  
- MESTEC, MineSense, NEC, Zebra  

### Analytics Tools Integration
Certified tools:  
- Tableau, BusinessObjects, others  
- Oracle provides link for full tech stack certification  

---

## Customer Success Stories  

### TaylorMade Golf
- Migrated large Oracle data warehouse to ADW  
- Completed a couple years ago  
- **Results:**  
  - Lower cost of ownership  
  - Better performance  
  - ADW vision realized  

### Wilson Truck Lines
- Used **ADB + APEX**  
- Previous: Amazon traditional coding (3 months)  
- Redeveloped with APEX in 2 days (**45x productivity improvement**)  
- Outcome: Great performance + interactive response times  

---

## APEX (Application Express) - Low-Code Platform  

### What is APEX?
- Oracle's low-code tool for building data-driven applications  
- Backend: Oracle Database  
- Productivity: 10x faster (often 40–50x faster in practice)  

### Built-in Features
- Forms & reporting tools  
- Faceted search + e-commerce-style filters  
- Easy UI customization  

### Automation Benefits
- Middle tier fully automated  
- No connection or state management needed  
- Automatic data type mapping  
- No 3GL programming required  

### Usage Statistics
- Millions of APEX apps in production  
- ~3,000 new apps built daily  
- Includes publicly available live labs  
- Recommendation: Use low-code by default, traditional coding as exception  

### Autonomous Database for APEX
- Dedicated ADB version optimized for APEX workloads  

---

## Advanced Analytics Capabilities  

### Beyond Traditional Data Warehouse
- Self-service drag-and-drop data loading  
- Visual ETL tools  
- No engineering required for basic ops  

### Advanced Analytics
- Graph & spatial analytics  
- Machine learning (ML) capabilities  
- AutoML: automated ML model creation  

### Data Integration
- Data lakes management  
- Multi-cloud integration  
- Massively parallel processing (MPP)  
- Third-party analytics tool support  

### Example: Seattle Sounders FC
- Using ADW for sports statistics  
- ML models to optimize goal-scoring strategies  
- Pay-per-use lowered costs  
- Similar tech used by English Premier League  

---

## Business Incentives & Support Programs  

### Bring Your Own License (BYOL)
- Existing Oracle DB licenses can be applied to OCI  

### Cloud Lift Service
- Free migration assistance by global engineering team  

### Support Rewards Program
- $0.25–$0.33 reward for every $1 spent on OCI  
- Rewards reduce Oracle support bills  

---

## Getting Started - Free Resources  

### Always Free Autonomous Database Service
- Hands-on trial of ADB  
- Cost: Free  

### Live Labs
- [developer.oracle.com/livelabs](https://developer.oracle.com/livelabs)  
- Tutorials + exercises running on Always Free ADB  

---

## Key Summary Points  

### ADB Value Proposition
- Fully managed infra + database  
- Reduced costs via automation  
- Security, availability, performance best practices  
- Automatic patching + tuning  
- Eliminates common errors  

### Migration Strategy
1. **Assessment** – analyze with Oracle tool  
2. **Migration** – manual (Data Pump) or automated (Migration Service)  
3. **Modernization** – move to OCI  
4. **Optimization** – agility + lower cost  

### Development Approach
- **Default:** Low-code (APEX)  
- **Exception:** Traditional coding  
- Productivity boost: 10–50x faster  
- Seamless with ADB  

### Target Audience
- Oracle 19c customers ready for cloud migration  
- Organizations seeking lower TCO + better performance  
- Dev teams building DB-driven apps  
- Companies modernizing infrastructure  
