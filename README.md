# Chroniq-RFM-Healthcare-segmentation
A healthcare analytics solution leveraging RFM (Recency, Frequency, Monetary) segmentation to identify high-risk chronic patients, reduce readmissions, and enable data-driven care management

### Dashboard Link : 
    https://app.powerbi.com/groups/me/reports/6bd3c642-093b-42b3-b4fa-4c92ab237d0c/c2a7bac4ce6ce7fe0088


## Project Overview
This project stratifies chronic care patients using RFM (Recency, Frequency, Monetary) segmentation, helping hospitals proactively manage high-risk individuals.
By analyzing visit frequency, recency, and cost data, the system identifies which patients are most likely to benefit from follow-ups and cost-saving interventions.


## Objective
- Identify high-risk chronic care patients
- Enable proactive care based on visit & spend behavior
- Build an interactive Power BI dashboard for clinical, financial, and operational decision-making
- Facilitate exports and ad hoc slicing of patient data for stakeholder-specific needs

## Dataset Overview
##### Source: MEPS 2022 (Medical Expenditure Panel Survey)  https://meps.ahrq.gov/mepsweb/data_stats/download_data_files.jsp?y=2022


Key Fields:
- DUPERSID (Unique Patient ID)
- Last_Visit_Date, Total_Visits, Total_Expenditure
- Age, Gender_Label, Insurance_Label, Region_Label
- Segment_Label (High, Medium, Low Risk)


## Technologies Used
- Python (for data cleaning and preprocessing)
- Power BI (dashboard and reporting)
- Microsoft Excel (QA & UAT trackers)
- JSON (Power BI Theme Customization)
- Simulated CSV data (patients, visits, vitals, diagnosis)

## Data Preparation
- Simulated datasets merged: patients.csv, visits.csv, vitals.csv
- Cleaned invalid ages (e.g., -1)
- Generated fields like Segment_Label, Gender_Label, Insurance_Label
- RFM metrics computed: Recency, Frequency, Monetary
- Final file: final_patient_rfm.csv

## RFM Segmentation Logic

| Segment | Recency (Days) | Frequency (# Visits) | Monetary ($) |
|---------|----------------|----------------------|------------|
| High Risk | > 90 | > 10 | > 10,000 |
| Medium Risk | 30–90 | 5–10 | 5,000–10,000 |
| Low Risk | < 30 | < 5 | < 5,000 |

## Power BI Dashboard Structure
###  Page 1: Executive Overview
- KPI Cards: Total Patients, High Risk %, Avg Visits, Avg Spend
- Segment Distribution & Cost Trends
- Filters: Gender, Insurance, Region

### Page 2: Segment Deep Dive
- Avg Age, Visits, Spend by Segment
- Gender & Insurance split visuals

### Page 3: Patient Drill-down
- Slicer to select patient ID
- Cards for Age, Region, Insurance
- Full visit profile and metrics

### Page 4: Ad Hoc Explorer
- Fully filterable patient table
- Export to Excel with filters


## Key Insights

**1. High-Risk = High Cost |** 
~25% of patients in the High Risk segment account for over 45% of total expenditure.

**2. Public Insurance Overrepresented |**
Publicly insured patients (Medicaid) dominate the High Risk group — points to post-discharge care gaps.

**3. Gender & Regional Trends |**
Male patients show higher frequency in High Risk. Certain regions indicate care avoidance despite high need.

**4. Frequency ≠ Spend Consistency |**
Some Medium Risk patients visit often but cost less — an opportunity for preventive care strategies.

**5. Low Risk ≠ No Risk |**
Some Low Risk patients haven’t visited recently but have moderate spend — they may escalate silently.



## Strategic Recommendations

**1. Trigger Follow-Ups for High Risk |**
Reach out to patients with Recency > 90 & Frequency > 10 using SMS, app alerts, or call centers.

**2. RFM + Insurance Combo |**
Overlay risk with insurance type — assign case managers to high-risk Medicaid patients to reduce readmission.

**3. Predict Escalating Medium Risk |**
Use RFM trend tracking to flag rising risk profiles before they tip over into high-cost cases.

**4. Embed in EMRs |**
Integrate RFM logic into EMRs so that doctors see real-time risk badges during check-in.

**5. Set Power BI Alerts |**
Trigger auto-notifications when high-risk patient count or avg spend exceeds thresholds — keeps admin in control.



## Conclusion
The Chroniq-RFM-Healthcare-Segmentation project bridges the gap between raw patient data and meaningful clinical action. By applying RFM segmentation on visit behavior and healthcare expenditure, this solution empowers hospitals to prioritize patients, reduce readmissions, and streamline resource allocation.

Key outcomes include:
- Real-time segmentation of chronic care populations
- A fully interactive, role-driven Power BI dashboard
- Actionable recommendations for hospital administrators, doctors, and financial planners
- A replicable framework for risk stratification and care optimization across healthcare systems
----
This project is not just a dashboard, it’s a blueprint for data-driven patient management at scale.
