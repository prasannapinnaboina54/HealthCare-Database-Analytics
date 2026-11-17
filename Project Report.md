## HealthCare Database Analytics

---

### 1. Introduction

The **HealthCare Database Analytics** project was developed to design and implement a structured relational database for hospital admission data. The primary objective is to enable efficient storage, retrieval, and advanced analysis of healthcare-related information using MySQL.

This report documents the complete project lifecycle including data modeling, database design, implementation, and analytical capabilities.

---

### 2. Project Objectives

- Design a normalized relational database for healthcare admissions
- Establish proper relationships between entities using Primary and Foreign Keys
- Enable efficient data loading and querying
- Develop a comprehensive set of analytical SQL queries
- Support business insights related to patients, doctors, hospitals, and revenue

---

### 3. Database Design

#### 3.1 Tables Created

| Table Name               | Type        | Description                              |
|--------------------------|-------------|------------------------------------------|
| doctors                  | Dimension   | Stores doctor information                |
| hospitals                | Dimension   | Stores hospital information              |
| medical_conditions       | Dimension   | List of medical conditions               |
| admission_types          | Dimension   | Urgent, Emergency, Elective              |
| insurance_providers      | Dimension   | Insurance companies                      |
| test_results             | Dimension   | Normal, Inconclusive, Abnormal           |
| medications              | Dimension   | Prescribed medications                   |
| healthcare_admissions    | Fact        | Central table containing admission data  |

#### 3.2 Relationships

The `healthcare_admissions` table acts as the central fact table and references all dimension tables through foreign keys:

- `doctor_id` → `doctors`
- `hospital_id` → `hospitals`
- `condition_id` → `medical_conditions`
- `admission_type_id` → `admission_types`
- `insurance_id` → `insurance_providers`
- `medication_id` → `medications`
- `test_result_id` → `test_results`

---

### 4. Implementation Steps

1. **Table Creation**  
   Individual `CREATE TABLE` scripts were written without constraints.

2. **Constraint Addition**  
   Primary Keys and Foreign Keys were added using `ALTER TABLE` statements for better control and maintainability.

3. **Data Loading Strategy**  
   Dimension tables were loaded first, followed by the fact table (`healthcare_admissions`) to maintain referential integrity.

4. **Query Development**  
   50 SQL queries were developed and categorized into five groups.

---

### 5. Analytical Query Categories

| Category                      | Number of Queries | Purpose                                      |
|-------------------------------|-------------------|----------------------------------------------|
| Basic Queries                 | 10                | Data exploration and simple retrieval        |
| Filtering Queries             | 10                | Conditional filtering and subset analysis        |
| Join Queries                  | 10                | Combining data across multiple tables        |
| Aggregation Queries           | 10                | Summarization using GROUP BY and aggregate functions |
| Business Questions & Analysis | 10                | Advanced insights for decision making        |

---

### 6. Key Business Insights Supported

- Revenue contribution by medical condition
- Most frequently used insurance providers
- Doctor-wise patient volume and average billing
- Hospital performance based on admission count
- Average length of patient stay
- Distribution of patients across age groups
- Percentage of abnormal test results
- Identification of high-risk patients (elderly + abnormal results + high billing)
- Monthly admission trends

---

### 7. Technical Specifications

- **Database System:** MySQL 8.0+
- **Data Volume:** 55,500+ admission records
- **Schema Type:** Relational (Normalized)
- **Tools Used:** MySQL Workbench, Python (for data preparation)

---

### 8. Challenges Faced & Solutions

| Challenge                          | Solution                                      |
|------------------------------------|-----------------------------------------------|
| Duplicate key errors during import | Used `TRUNCATE TABLE` before re-importing     |
| `secure-file-priv` restriction     | Recommended `LOAD DATA LOCAL INFILE` / Python |
| Maintaining referential integrity  | Strict data loading order + Foreign Keys      |

---

### 9. Project Outcomes

- Fully functional healthcare analytics database
- Clean and reusable SQL scripts
- Strong foundation for dashboarding and reporting
- Ready-to-use analytical queries for business users and analysts

---

### 10. Conclusion

The HealthCare Database Analytics project successfully demonstrates the design and implementation of a healthcare data warehouse-style database using MySQL. By combining proper data modeling with a rich set of analytical queries, the project provides valuable insights that can support both operational and strategic decision-making in a healthcare environment.

---

### 11. Future Scope

- Integration with Power BI / Tableau for visualization
- Addition of more historical data
- Implementation of stored procedures and views
- Development of a web-based reporting interface
- Predictive analytics using patient data

---

**Project Name:** HealthCare Database Analytics  
**Status:** Completed  
**Document Type:** Project Report
