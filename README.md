# HealthCare Database Analytics

A comprehensive MySQL database project built for analyzing hospital admissions, patient demographics, medical conditions, doctors, hospitals, insurance providers, and treatment outcomes.

---

## Project Overview

This project models a realistic healthcare admissions system. It contains dimension tables (Doctors, Hospitals, Conditions, etc.) and a central fact table (`healthcare_admissions`) with 55,500+ patient admission records.

The project includes:

- Complete database schema design
- Table creation scripts
- Primary Key & Foreign Key constraints
- Data loading strategy
- 50 ready-to-use analytical SQL queries categorized into 5 groups

---

## Database Schema

### Dimension Tables

| Table Name              | Description                          |
|-------------------------|--------------------------------------|
| `doctors`               | List of doctors                      |
| `hospitals`             | List of hospitals                    |
| `medical_conditions`    | Medical conditions (Cancer, Asthma, etc.) |
| `admission_types`       | Urgent / Emergency / Elective        |
| `insurance_providers`   | Insurance companies                  |
| `test_results`          | Normal / Inconclusive / Abnormal     |
| `medications`           | Prescribed medicines                 |

### Fact Table

| Table Name                  | Description                              |
|-----------------------------|------------------------------------------|
| `healthcare_admissions`     | Main table containing all patient admissions |

---

## Entity Relationship Summary

```
healthcare_admissions
├── doctor_id          → doctors
├── hospital_id        → hospitals
├── condition_id       → medical_conditions
├── admission_type_id  → admission_types
├── insurance_id       → insurance_providers
├── medication_id      → medications
└── test_result_id     → test_results
```

---

## Project Structure

```
HealthCare-Database-Analytics/
│
├── 01_create_tables.sql
├── 02_add_constraints.sql
├── 03_basic_queries.sql
├── 04_filtering_queries.sql
├── 05_join_queries.sql
├── 06_aggregation_queries.sql
├── 07_business_analysis_queries.sql
└── README.md
```

---

## How to Set Up the Database

### Step 1: Create the Database

```sql
CREATE DATABASE healthcare_analytics;
USE healthcare_analytics;
```

### Step 2: Create Tables

Run the script: `01_create_tables.sql`

### Step 3: Add Constraints

Run the script: `02_add_constraints.sql`

### Step 4: Load Data

**Recommended Order:**

1. doctors  
2. hospitals  
3. medical_conditions  
4. admission_types  
5. insurance_providers  
6. test_results  
7. medications  
8. **healthcare_admissions** (must be last)

> **Tip:** Use `TRUNCATE TABLE table_name;` before re-importing data to avoid duplicate key errors.

---

## SQL Query Categories

This project contains **50 carefully designed queries** divided into 5 categories:

### 1. Basic Queries (10)
Simple SELECT statements to explore tables and columns.

### 2. Filtering Queries (10)
Using `WHERE`, `BETWEEN`, `LIKE`, date filters, and conditions.

### 3. Join Queries (10)
Inner joins between fact and dimension tables to get meaningful insights.

### 4. Aggregation Queries (10)
`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`, `GROUP BY`, and `ORDER BY`.

### 5. Business Questions & Analysis (10)
Real-world analytical questions such as:
- Highest revenue generating medical condition
- Most used insurance provider
- Average length of stay
- High-risk patient identification
- Monthly admission trends
- Doctor performance analysis

---

## Sample Business Insights You Can Get

- Which medical condition generates the highest revenue?
- Which doctors handle the most patients?
- What is the average length of hospital stay?
- Which insurance provider is most preferred?
- Percentage of abnormal test results
- Age group distribution of patients
- High billing + elderly + abnormal test patients (high-risk cases)

---

## Technologies Used

- **Database**: MySQL 
- **Tools**: MySQL Workbench 
- **Data Source**: Excel files converted to structured relational tables

---

## Best Practices Followed

- Normalized schema design
- Proper Primary Keys and Foreign Keys
- Clear naming conventions
- Separation of table creation and constraints
- Logical data loading order
- Categorized and well-commented SQL queries

---

## Author

**HealthCare Database Analytics Project**  
Prasanna Pinnaboina - Aspiring Data Analyst

---
