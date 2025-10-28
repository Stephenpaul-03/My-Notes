## 1. **Single-Tier Architecture**

- **Layers:**
    - Everything (source data, warehouse, and reporting) in a single layer.
- **Drawback:**
    - Rarely used because it creates performance issues and no separation between raw and processed data.
- **Use case:**
    - Not recommended for actual large-scale systems. Maybe OK for a small test project.

## 2. **Two-Tier Architecture**

- **Layers:**
    - **Source Layer (Operational DBs)**
    - **Data Warehouse + Analytical tools**
- **Drawback:**
    - Tight coupling between client and server → scaling becomes a pain.
- **Use case:**
    - Mid-level systems or legacy architectures.

## 3. **Three-Tier Architecture**

### # **Tier 1: Data Source Layer**

- ERP systems, CRM, flat files, web data, etc.
- Raw operational data lives here

### # **Tier 2: Data Staging + Warehouse Layer**

- **ETL/ELT processes**: Extract, Transform, Load
- Cleansing, validation, transformation
- Stored in the **Data Warehouse** (central repo)
- Can include **Data Marts** (department-specific mini warehouses)

### # **Tier 3: Presentation/Access Layer**

- BI tools, dashboards, SQL clients
- Used by analysts, data scientists, execs, etc.
- Queries hit OLAP cubes, views, or summary tables

## **# Optional Components**

| Component | Description |
| --- | --- |
| **Metadata** | Data about the data (definitions, lineage, mappings) |
| **OLAP Engine** | Supports multi-dimensional queries (roll-up, drill-down) |
| **Data Marts** | Subsets of DW for specific departments or domains |
| **ODS (Operational Data Store)** | Temporary, cleaned data store before loading into DW |

## **# Data Flow Summary**

- Source Systems → ETL → Data Warehouse → Data Marts (optional) → BI Tools / Users