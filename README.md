# 🏥 Global Healthcare Operational & Billing Analytics Dashboard

<img width="893" height="503" alt="image" src="https://github.com/user-attachments/assets/ac9e408b-8e12-425b-82ce-c1329ed7d291" />


## 📌 Executive Summary
This project presents an interactive **Power BI Dashboard** designed to evaluate operational efficiency, financial performance, and emergency care demand across hospital networks. Using a real-world open-source dataset of **56,000+ patient records**, the analysis tracks critical healthcare domain KPIs including **Average Length of Stay (ALOS)**, **Billing Volume**, and **Emergency Admission Trends**[cite: 4, 6].

---

## 🎯 Key Business Questions Addressed
1. What is the total revenue/billing volume generated across admission types and insurance providers?[cite: 4, 6]
2. What are the primary medical conditions driving emergency room admissions?
3. What is the Average Length of Stay (ALOS) across treatment conditions?[cite: 4, 6]
4. Which doctors and hospitals handle the highest patient volumes?[cite: 6]

---

## 📊 Key Insights & Highlights

* **Financial Overview:** Processed over **$1.42 Billion** in total billing across 56K+ unique patient admissions, with an average billing cost of **~$25.54K** per patient[cite: 6].
* **Operational Efficiency:** The overall **Average Length of Stay (ALOS)** stands at **16 days**, indicating consistent bed occupancy and resource utilization[cite: 6].
* **Emergency Admissions:** Identified **Obesity** and **Arthritis** as the leading medical conditions triggering emergency visits (~3.1K cases each)[cite: 6].
* **Resource Allocation:** Highlighted top attending physicians (e.g., *Michael Smith* leading with 27 patients) and evaluated revenue distribution across major insurance providers (Cigna, Medicare, Blue Cross, etc.)[cite: 6].

---

## 🛠️ Data Architecture & Tech Stack

* **Business Intelligence Tool:** Power BI Desktop[cite: 1]
* **Data Transformation:** Power Query (Data cleaning, text formatting, date parsing)[cite: 2]
* **Data Modeling & Calculations:** DAX (Data Analysis Expressions)[cite: 3]
* **Data Source:** Open-source Healthcare Dataset (`healthcare_dataset.csv`)[cite: 1]

---

## 📐 Key DAX Measures Used

```dax
// Total Patient Count
Total Patients = COUNT(healthcare_dataset[Name])

// Total Billing Volume
Total Billing = SUM(healthcare_dataset[Billing Amount])

// Average Billing Cost
Avg Billing = AVERAGE(healthcare_dataset[Billing Amount])

// Average Length of Stay (ALOS)
Avg Length of Stay = AVERAGEX(healthcare_dataset, DATEDIFF(healthcare_dataset[Date of Admission], healthcare_dataset[Discharge Date], DAY))

// Emergency Cases Count
Emergency Cases = CALCULATE(COUNT(healthcare_dataset[Name]), healthcare_dataset[Admission Type] = "Emergency")


'''
⚙️ How to View & Use This ProjectClone the Repository:Bashgit clone [https://github.com/YOUR_USERNAME/Healthcare-Operational-Analytics-PowerBI.git](https://github.com/YOUR_USERNAME/Healthcare-Operational-Analytics-PowerBI.git)
Open the Report:Download and install Power BI Desktop.Open the file Hospital_Management_Analytics.pbix inside Power BI Desktop[cite: 6].Interact with Filters:Use the dynamic Year, Gender, and Admission Type slicers to explore specific segments.

  ✉️ Contact & FeedbackCreated by [Piash Barua] – feel free to connect on LinkedIn or leave a star
⭐️ on this repo if you found it useful!
