# Vitality Fitness Club (VFC) - Relational Database Implementation

A comprehensive implementation of end-to-end database engineering, transitioning from a conceptual business model to a fully optimised, normalised logical schema and structural SQL deployment. This project demonstrates foundational data engineering practices including schema design, strict data integrity constraints, and normalisation to Third Normal Form (3NF).

## Project Components

- **Conceptual Architecture:** High-level ER mapping establishing entity boundaries, structural cardinality, and business operational rules.
- **Normalisation Documentation:** Systematic transformation of unstructured datasets (UNF) through 1NF and 2NF to achieve full 3NF compliance.
- **Logical Blueprint:** Detailed schema design identifying Primary Keys (PK), Foreign Keys (FK), and unique constraints.
- **SQL Generation & Validation:** Complete, error-free Data Definition Language (DDL) scripts executed and verified within an Oracle Database environment.

---

## Database Architecture & Normalisation Pipeline

### 1. Conceptual to Logical Modeling

The data model accurately captures business structures for a multi-location fitness enterprise, mapping out complex relationships such as recursive member referrals, class schedules, staff roles, and longitudinal health assessments.

### 2. Normalisation Strategy (UNF to 3NF)

To guarantee a reliable single source of truth for downstream business intelligence reporting, datasets were systematically decomposed to eliminate structural anomalies:

- **1NF:** Removed nested repeating groups from the unnormalised structure, separating the core `CLASS` schedule details from individual `MEMBER` interactions.
- **2NF:** Eliminated partial dependencies by isolating standalone entities, decoupling operational `CENTRE` data from specific `CLASS` records.
- **3NF:** Removed transitive functional dependencies, extracting changing descriptive attributes (such as `class_desc`) into standalone lookup tables like `CLASS_TYPE`.

### 3. Schema Structure & Constraint Mapping

The database consists of 12 fully integrated relations designed to protect data quality:

- **Surrogate Key Optimisation:** Applied clean surrogate keys (`ca_id`, `ce_id`, `cs_id`) on complex composite associative tables (`CLASS_ATTENDANCE`, `CLASS_ENROLMENT`, `CLASS_STAFF`) to simplify join structures and enhance analytics efficiency.
- **Domain Check Constraints:** Implemented strict value restrictions across geographical states, member gender profiles, and first-aid status certifications to maintain rigid data quality at the point of ingestion.

---

## Technical Stack & Tools

- **Modeling Environment:** Oracle SQL Developer Data Modeler
- **Target Database Platform:** Oracle Database 12c
- **Languages:** SQL / DDL (Data Definition Language)
- **Design Core:** Relational Database Mapping, 3NF Normalisation, Referential Integrity Constraints
