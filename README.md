# 🏥 Primary Care Performance & Patient Activity Analytics

> End-to-end healthcare analytics and data warehousing project using Python, PostgreSQL, and Power BI to transform raw appointment data into operational and executive-level healthcare insights.

---

## 📑 Table of Contents
- [Executive Summary](#executive-summary)
- [Business Objectives](#business-objectives)
- [Tech Stack](#tech-stack)
- [Architecture Overview](#architecture-overview)
- [Data Warehouse Design](#data-warehouse-design)
- [ETL Pipeline](#etl-pipeline)
- [Analytics & KPI Layer](#analytics--kpi-layer)
- [Dashboard Overview](#dashboard-overview)
- [Business Impact](#business-impact)
- [Skills Demonstrated](#skills-demonstrated)
- [Repository Structure](#repository-structure)
- [Project Status](#project-status)

---

## Executive Summary

This project delivers an end-to-end healthcare analytics solution designed to support operational monitoring and executive decision-making within a primary care environment.

Using Python for ETL processing, PostgreSQL for data warehousing, and Power BI for business intelligence, the project transforms fragmented appointment-level operational data into a structured analytics platform capable of supporting performance analysis, capacity planning, and service quality monitoring.

The solution simulates a real-world healthcare analytics workflow, including:
- Data ingestion and validation
- ETL pipeline development
- Star schema warehouse modeling
- KPI-driven analytics design
- Business intelligence reporting

---

## Business Objectives

This analytics solution is designed to address key operational questions within a healthcare practice:

- How does appointment volume change over time?
- What are the trends in no-shows and cancellations?
- Which clinics or staff roles experience the highest workload?
- How efficient are consultation and patient wait times?
- Which appointment outcomes require the most follow-up attention?
- How can operational performance be monitored using centralized analytics?

---

## Tech Stack

### Data Engineering & Processing
- **Python:** Pandas, NumPy
- **PostgreSQL:** Data warehouse implementation
- **SQL:** Data transformation and analytics modeling

### Business Intelligence
- **Power BI:** Dashboarding and KPI visualization

### Spreadsheet & Validation
- **CSV Processing**
- **Data Quality Validation**
- **Structured Logging**

---

## Architecture Overview

The project follows a layered analytics architecture commonly used in modern business intelligence environments.

```text
Raw CSV Data
     │
     ▼
Python ETL Pipeline
(Extract → Clean → Validate → Transform)
     │
     ▼
PostgreSQL
Staging + Star Schema Warehouse
     │
     ▼
Power BI Dashboard
(Operational & Executive Reporting)
```

This architecture separates:
- Data ingestion
- Data transformation
- Data storage
- Business intelligence reporting

allowing scalable and maintainable analytics workflows.

---

## Data Warehouse Design

### Staging Layer
The staging layer stores cleaned appointment-level records while preserving the original source structure.

Key characteristics:
- No aggregations applied
- Minimal business logic
- Serves as controlled ingestion layer

---

### Star Schema (Analytics Layer)

The analytics layer uses a dimensional star schema optimized for BI reporting and KPI calculations.

### Fact Table

#### `fact_appointments`
One row per appointment containing operational measures such as:
- Wait time
- Consultation duration
- Appointment metrics

Foreign keys connect all business dimensions.

---

### Dimension Tables

- `dim_date`
- `dim_patient_age_group`
- `dim_appointment_type`
- `dim_appointment_status`
- `dim_staff_role`
- `dim_clinic_location`
- `dim_outcome_category`

---

### Benefits of the Design

The warehouse design enables:
- Consistent KPI calculations
- Fast dashboard performance
- Flexible multidimensional analysis
- Simplified reporting workflows

---

## ETL Pipeline

The ETL workflow is fully script-driven and repeatable, enabling scalable processing across multiple datasets.

### Extract
- Loads multiple CSV files across different periods
- Validates schema consistency between files

### Transform
- Standardizes dates and categorical values
- Removes duplicate appointments using generated unique identifiers
- Derives calendar attributes:
  - Year
  - Month
  - Week
  - Weekday

### Validate
Validation checks include:
- Negative wait times
- Invalid consultation durations
- Invalid appointment statuses
- Duplicate detection

Validation results are logged to improve auditability and data reliability.

### Load
- Loads cleaned datasets into PostgreSQL staging tables
- Populates dimension tables
- Builds fact tables using surrogate keys

---

## Analytics & KPI Layer

The analytics layer is designed to support operational monitoring and executive reporting through KPI-driven dashboards.

### Core KPIs

- Total Appointments
- Attendance Rate
- No-show Rate
- Cancellation Rate
- Average Wait Time
- Median Wait Time
- Average Consultation Duration
- Workload by Staff Role
- Appointments by Clinic Location
- Outcome Distribution
- Follow-up Rate
- Month-over-Month Appointment Trends

These metrics are designed to support both operational efficiency analysis and service quality monitoring.

---

## Dashboard Overview

The Power BI dashboard layer is designed to provide interactive operational and executive-level reporting.

### Planned Dashboard Pages

#### Executive Overview
- Appointment volume trends
- KPI summary
- Attendance and cancellation monitoring

#### Appointment Status & Outcomes
- Outcome distribution
- Follow-up analysis
- No-show trends

#### Wait Time & Service Efficiency
- Wait time analysis
- Consultation duration tracking
- Service bottleneck identification

#### Clinic & Staff Performance
- Workload comparison by clinic
- Staff utilization analysis
- Operational efficiency monitoring

---

## Business Impact

This solution enables healthcare providers to:

- Monitor operational performance in near real-time
- Identify high no-show and cancellation patterns
- Improve patient service efficiency through wait time analysis
- Support clinic capacity planning and workload balancing
- Standardize healthcare operational reporting
- Support executive decision-making using centralized analytics

---

## Skills Demonstrated

### Data Engineering
- ETL Pipeline Development
- Data Validation & Quality Checks
- Data Warehouse Design
- Star Schema Modeling
- PostgreSQL Data Loading

### Analytics & BI
- KPI Development
- Healthcare Operations Analytics
- Business Intelligence Reporting
- Dashboard Design

### Technical Skills
- Python (Pandas, NumPy)
- SQL
- PostgreSQL
- Power BI

---

## Repository Structure

```text
primary-care-analytics/
│
├── data/
│   ├── raw/
│   │   ├── appointments_2023_2.csv
│   │   ├── appointments_2024_1.csv
│   │   ├── appointments_2024_2.csv
│   │   ├── appointments_2025_1.csv
│   │   └── appointments_2025_2.csv
│   │
│   └── processed/
│       ├── appointments_all.csv
│       └── appointments_clean.csv
│
├── notebooks/
│   ├── 01_data_integration.py
│   └── 02_data_quality_check.py
│
├── sql/
│   └── primary_care_analytic.sql
│
├── dashboards/
│   └── screenshots/
│
└── README.md
```

---

## Project Status

- ✅ Data ingestion and cleaning completed
- ✅ PostgreSQL data warehouse implemented
- ✅ Star schema analytics model finalized
- ✅ KPI framework defined
- 🚧 Power BI dashboard development in progress

---

## Summary

This project demonstrates a complete healthcare analytics workflow, from raw operational data ingestion to dimensional warehouse modeling and business intelligence reporting.

It highlights practical experience in:
- Data engineering
- Healthcare analytics
- ETL pipeline design
- SQL-based warehouse development
- KPI-driven reporting architecture

while simulating a real-world healthcare operational analytics environment.
