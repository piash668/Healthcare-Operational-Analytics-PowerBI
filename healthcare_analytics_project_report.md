# 🏥 Comprehensive Healthcare Operational & Financial Analytics Report

**Author:** Data Analyst Trainee / BI Developer  
**Target Organization:** MedTourEasy  
**Tooling Stack:** Power BI Desktop, Power Query, DAX, Excel/CSV Data Engine  
**Project Domain:** Healthcare Management & Medical Tourism Operational Analytics  

---

## 📌 Executive Summary

This report delivers an in-depth analytical evaluation of hospital performance, patient admission demographics, clinical workloads, and financial metrics based on an open-source dataset of **56,000+ patient records**.

The primary objective of this project is to provide actionable business intelligence for hospital administrators and medical tourism organizations like **MedTourEasy**. By evaluating key performance indicators (KPIs) such as **Total Billing**, **Average Length of Stay (ALOS)**, and **Emergency Case Distribution**, this report highlights operational bottlenecks and financial opportunities to enhance healthcare service delivery.

---

## 📊 Key Performance Indicators (KPIs) Overview

| Metric | Value | Domain Significance |
| :--- | :--- | :--- |
| **Total Patient Volume** | **56,000+ Patients** | Measures overall healthcare reach and operational load. |
| **Total Billing Amount** | **$1.42 Billion USD** | Summarizes cumulative revenue generated across insurance & self-pay channels. |
| **Average Billing per Patient** | **$25,540 USD** | Highlights average financial load per admitted patient. |
| **Average Length of Stay (ALOS)**| **16 Days** | Measures hospital bed occupancy and efficiency of discharge planning. |

---

## 🔍 Detailed Analytical Findings

### 1. Emergency Admission & Medical Condition Analysis
* **Top Emergency Drivers:** Clinical analysis reveals that **Obesity** and **Arthritis** are the leading medical conditions triggering emergency care, accounting for approximately **3,100 emergency cases each**.
* **Other High-Volume Conditions:** Cancer, Diabetes, Asthma, and Hypertension demonstrate consistent patient volume distribution (~9,000 total patients per condition across all admission types).
* **Strategic Recommendation:** Establish specialized fast-track triage units for emergency orthopedic (Arthritis) and bariatric/metabolic (Obesity) complications to reduce waiting times in Emergency Departments.

### 2. Operational Capacity & Bed Occupancy
* **Average Length of Stay (ALOS):** The global benchmark for ALOS stands at **16 days** across all participating hospitals.
* **Impact on Turnover:** While a stable ALOS ensures adequate recovery time, prolonged hospital stays directly limit bed turnover rate for incoming international and emergency patients.
* **Strategic Recommendation:** Implement post-discharge remote monitoring and step-down care facilities to shorten ALOS without compromising patient recovery standards.

### 3. Financial Distribution & Insurance Coverage
* **Insurance Breakdown:** Billing volume is evenly distributed across major global insurance providers:
  * **Cigna**
  * **Medicare**
  * **Blue Cross**
  * **UnitedHealthcare**
  * **Aetna**
* **Admission Type Billing:** Across all insurance providers, **Elective**, **Emergency**, and **Urgent** admissions generate comparable total billing figures, proving that non-emergency elective procedures are as financially vital as acute care operations.

### 4. Physician Workload & Resource Management
* **Top Attending Physicians:** Clinical caseload distribution identifies top doctors handling high patient volumes (e.g., *Michael Smith* leading with 27 individual patient admissions, followed closely by *John Smith* and *Robert Smith* with 22 patients each).
* **Workload Optimization:** Balancing physician caseloads prevents doctor burnout and maintains high patient rating standards.

---

## 🛠️ Data Engineering & DAX Formulas

The project utilized **Power Query** for text formatting, removing casing inconsistencies (e.g., standardizing patient names), and validating date fields. Dynamic calculations were executed using **DAX (Data Analysis Expressions)**:

### 1. Total Patients Measure
```dax
Total Patients = COUNT(healthcare_dataset[Name])
```

### 2. Total Billing Measure
```dax
Total Billing = SUM(healthcare_dataset[Billing Amount])
```

### 3. Average Billing Measure
```dax
Avg Billing = AVERAGE(healthcare_dataset[Billing Amount])
```

### 4. Average Length of Stay (ALOS) Measure
```dax
Avg Length of Stay = 
AVERAGEX(
    healthcare_dataset, 
    DATEDIFF(healthcare_dataset[Date of Admission], healthcare_dataset[Discharge Date], DAY)
)
```

### 5. Emergency Cases Count
```dax
Emergency Cases = 
CALCULATE(
    COUNT(healthcare_dataset[Name]), 
    healthcare_dataset[Admission Type] = "Emergency"
)
```

---

## 🚀 Strategic Recommendations for MedTourEasy

1. **Optimize Patient Allocation:** Route international medical tourism patients to hospitals demonstrating lower ALOS and higher rating consistency to optimize travel duration and post-treatment recovery.
2. **Targeted Package Offerings:** Given that elective surgeries drive significant revenue across all insurance types, create specialized travel packages for elective orthopedic and cosmetic/bariatric care.
3. **Data-Driven Waiting Time Reduction:** Utilize dynamic filtering (by Year, Admission Type, and Gender) to proactively forecast peak emergency periods and reallocate medical resources accordingly.

---

## 📁 Repository File Structure

* `healthcare_analytics_report.md` - Complete project documentation and analytical findings (This File).
* `Hospital_Management_Analytics.pbix` - Interactive Power BI Dashboard file.
* `healthcare_dataset.csv` - Source dataset.
* `dashboard_screenshot.png` - Visual representation of the dashboard canvas.

---
*Report generated for GitHub documentation and portfolio submission.*