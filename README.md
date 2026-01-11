# Ventilation Duration Analysis in ICU Patients (MIMIC-IV)

## Overview
This project analyzes the duration of invasive mechanical ventilation in ICU patients using a derived dataset from the MIMIC-IV database.
The objective is to explore ventilation patterns and their relationship with clinical outcomes and patient demographics through an end-to-end data analysis workflow.

The project is intended for educational and portfolio purposes and focuses on data cleaning, exploratory data analysis, visualization, and SQL-based aggregations in a healthcare context.

---

## Dataset and Cohort Definition
The analysis is based on a derived dataset obtained from the MIMIC-IV database, focused on ICU patients undergoing invasive mechanical ventilation.

### Inclusion Criteria
Patients were considered intubated if they exhibited parameters related to invasive mechanical ventilation.
The first occurrence of such parameters marked the beginning of a ventilation event, which was considered ongoing if repeated within the following 12 hours.
This step identified 38,756 ventilation events.

### Exclusion Criteria
Ventilation events were excluded if any of the following conditions applied:
- Subsequent ventilation events during the same ICU admission
- Ventilation events occurring after the first ICU admission
- Ventilation duration shorter than 24 hours
- Patients who died before a weaning attempt

After applying these criteria, a total of 8,129 patients were retained.

### Extubation Definition and Outcome Classification
Extubation was defined based on:
- Absence of invasive ventilation indicators (e.g. endotracheal tube, tracheotomy)
- Presence of non-invasive ventilation (e.g. CPAP, Bi-PAP)
- Initiation of oxygen therapy

Post-extubation outcomes were classified as:
- **Extubation success:** no invasive ventilation within 48 hours (6,069 patients)
- **Extubation failure:** reintubation or death within 48 hours (2,060 patients)

---

## Methods
The analysis follows these main steps:
- Data loading and preprocessing in Python
- Feature selection and handling of missing values
- Computation of ventilation duration in hours
- Exploratory data analysis and visualization
- Aggregated statistics using SQL (SQLite)
- Comparison of ventilation duration across outcomes and demographic variables

---

## Key Analyses
- Distribution of ventilation duration across ICU patients
- Relationship between ventilation duration and clinical outcome
- Outcome comparison by age and sex
- SQL-based aggregation to compute summary statistics by outcome group

---

## Technologies Used
- **Python** (pandas, numpy)
- **Data Visualization:** matplotlib
- **SQL:** SQLite
- **Environment:** Jupyter Notebook

---

## Results Summary
- Ventilation duration shows a highly right-skewed distribution.
- Patients with worse clinical outcomes tend to experience longer ventilation durations.
- Age appears to be associated with clinical outcome, suggesting a potential confounding effect.

This project demonstrates an end-to-end data analysis workflow applied to a real-world healthcare dataset.

---

## Data Availability
Due to data access restrictions associated with the MIMIC-IV database, the dataset used in this project cannot be publicly shared.
The repository contains only code and documentation.

Researchers interested in accessing the original data should refer to the official MIMIC-IV database access procedures.

---

## Disclaimer
This project is intended solely for educational and portfolio purposes.
It does not provide clinical recommendations or medical decision support.

