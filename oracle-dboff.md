# Oracle Database Offerings

---

## Overview of Oracle Database Deployment Options

<details>
<summary>Deployment Options</summary>

| Deployment Option | Description |
|------------------|-------------|
| **On-premise** | Customer manages everything (infrastructure + database) |
| **Database Cloud Services (DBCS)** | Co-managed: Oracle manages infrastructure, customer manages database |
| **Autonomous Database (ADB)** | Fully managed: Oracle manages both infrastructure and database |
| **Exadata Cloud Service** | Available as deployment option |
| **Third-party Cloud** | Also available |

</details>

---

## Autonomous Database (ADB) - Core Concept

<details>
<summary>What is ADB?</summary>

- Fully managed service: Oracle handles all infrastructure and database management  
- Eliminates tedious DBA chores & implements best practices automatically  
- Significantly lower cost compared to traditional deployments  

</details>

<details>
<summary>When to Use Co-managed vs Fully Managed</summary>

**Co-managed (DBCS):**  
- Customers not yet on Oracle 19c  
- Running packaged applications like E-Business Suite  

**Fully managed (ADB):**  
- Recommended for all other use cases  

</details>

---

## Cost Analysis & TCO Studies

<details>
<summary>Wikibon Research Findings</summary>

| Platform | Cost Comparison |
|----------|----------------|
| On-premise | Baseline cost |
| Amazon RDS | Same as on-prem OR 50% higher (with DR/multizone) |
| Autonomous Transaction Processing (ATP) | Almost 50% LESS than on-premise cost |

**Key Benefits of ADB**  
- Lower TCO through automation  
- Higher productivity & less downtime  
- Eliminates manual DBA tasks  
- Best-practice configurations included  

</details>

---

## Migration Process to ADB

<details>
<summary>Step 1: Assessment Tool</summary>

- Oracle provides analysis tool for current on-premise databases  
- Identifies unsupported features/configurations:  
  - Pre-19c releases  
  - Database tables in system/sys schema  
  - Rare edge cases  

</details>

<details>
<summary>Step 2: Data Migration (Manual)</summary>

1. Use **Data Pump export** from on-premise DB  
2. Upload exported data to **Oracle Cloud Object Store**  
3. Use **Data Pump import** to load data into ADB  

</details>

<details>
<summary>Step 3: Database Migration Service (Automated)</summary>

- Point to source database (on-premise or cloud)  
- Oracle handles the entire migration automatically  
- Eliminates manual steps from Step 2  

**Existing Tuning Preservation:**  
- DBAs can preserve existing tuning & indexes  
- No requirement to use ADB autotuning  
- Existing optimizations maintained  

</details>

---

## Application Certification & Support

<details>
<summary>Oracle Packaged Applications</summary>

- **Already Certified:** JD Edwards, PeopleSoft, Siebel  
- **In Progress:** E-Business Suite (EBS) - expected next year  

</details>

<details>
<summary>Fully Managed Application Stack</summary>

- Oracle manages middle tier & database tier  
- Database moves to Autonomous Database  

</details>

<details>
<summary>Third-Party Applications & Analytics Tools</summary>

- **Certified Partners:** MESTEC, MineSense, NEC, Zebra  
- **Analytics Tools Certified:** Tableau, BusinessObjects, others  
- Check presentation link for full tech stack certifications  

</details>

---

## Customer Success Stories

<details>
<summary>TaylorMade Golf</summary>

- Migrated large data warehouse from on-premise to **ADW**  
- Results: Lower cost, better performance, realized ADW vision  

</details>

<details>
<summary>Wilson Truck Lines</summary>

- Used **ADB + APEX**  
- Redeveloped application in **2 days** vs 3 months previously (**45x productivity**)  
- Outcome: High performance & interactive response  

</details>

---

## APEX (Application Express) - Low-Code Platform

<details>
<summary>Overview</summary>

- Oracle's low-code tool for data-driven applications  
- Productivity: Estimated **10x faster** than traditional coding (often 40-50x)  
- Default: Use APEX, traditional coding as exception  

</details>

<details>
<summary>Capabilities & Automation</summary>

**Built-in Features:**  
- Forms & reporting tools  
- Faceted search  
- E-commerce filtering  
- Easy UI customization  

**Automation Benefits:**  
- Fully automated middle tier  
- No connection or state management required  
- Automatic data type mapping  
- No 3GL coding needed  

</details>

<details>
<summary>ADB for APEX</summary>

- Dedicated ADB version optimized for APEX workloads  

</details>

---

## Advanced Analytics Capabilities

<details>
<summary>Self-Service & Advanced Analytics</summary>

- Drag-and-drop data loading  
- ETL visual transformation tools  
- Graph & Spatial analytics  
- Machine Learning with **AutoML**  

**AutoML Feature:**  
- Input dataset & target feature  
- Oracle automatically generates ML model  

**Data Integration:**  
- Build/manage data lakes  
- Multi-cloud integration  
- Massively Parallel Processing (MPP)  
- Supports all popular analytics tools  

**Example:** Seattle Sounders Football Club  
- Uses ADW for sports stats analysis  
- ML models optimize goal scoring  
- Pay-per-use model lowers costs  

</details>

---

## Business Incentives & Support Programs

<details>
<summary>Bring Your Own License (BYOL)</summary>

- Migrate existing Oracle licenses to **OCI**  

</details>

<details>
<summary>Cloud Lift Service</summary>

- Free migration assistance by Oracle cloud engineering team  

</details>

<details>
<summary>Support Rewards Program</summary>

- $0.25–$0.33 reward per $1 spent on OCI  
- Can reduce on-prem support costs  

</details>

---

## Getting Started - Free Resources

<details>
<summary>Always Free ADB</summary>

- Hands-on trial of ADB  
- Completely free  

</details>

<details>
<summary>Live Labs</summary>

- Exercises on **developer.oracle.com/livelabs**  
- Runs on Always Free ADB  
- Practical, hands-on learning  

</details>

---

## Key Summary Points

<details>
<summary>ADB Value Proposition</summary>

- Fully managed infrastructure & database  
- Cost reduction via automation & best practices  
- Automatic patching & tuning  
- Eliminates common on-prem configuration errors  

</details>

<details>
<summary>Migration Strategy</summary>

- Assessment: Oracle analysis tool  
- Migration: Manual (Data Pump) or Automated (Migration Service)  
- Modernization: Move to cloud  
- Optimization: Agility + lower cost  

</details>

<details>
<summary>Development Approach</summary>

- Default: Low-code tools (APEX)  
- Exception: Traditional coding  
- Productivity: 10–50x improvement  
- Seamless integration with ADB  

</details>

<details>
<summary>Target Audience</summary>

- Oracle 19c customers ready for cloud migration  
- Organizations seeking lower TCO & better performance  
- Development teams building database-driven apps  
- Companies modernizing data infrastructure  

</details>

---

*End of Notes*
