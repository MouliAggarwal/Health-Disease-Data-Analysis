# 🫀 Heart Disease Analysis Dashboard

![Dashboard Preview]<img width="700" height="394" alt="Heart Disease Analysis Dashboard" src="https://github.com/user-attachments/assets/af5b99bc-7a6d-45c3-9112-5dc2a8ca2acc" />
)

> An interactive Power BI dashboard analyzing clinical and demographic patterns in heart disease patients, built on the UCI Heart Disease dataset.

---

## 📌 Project Overview

Heart disease is one of the leading causes of mortality worldwide. This project explores a clinical dataset of **270 patients** to uncover patterns and risk factors associated with the presence or absence of heart disease. The dashboard was built in **Power BI** and provides a multi-dimensional view across age, gender, cholesterol levels, exercise habits, blood sugar, and diagnostic test results.The dataset was sourced from Kaggle.
---

## 📂 Dataset Description

The dataset contains **270 rows** and **17 columns** capturing patient demographics and clinical measurements.

| Column | Description |
|---|---|
| `Age` | Patient's age in years |
| `Sex` | Gender (Male / Female) |
| `BP` | Resting blood pressure (mm Hg) |
| `Cholesterol` | Serum cholesterol (mg/dL) |
| `FBS Over 120` | Fasting blood sugar > 120 mg/dL (High / Not High) |
| `EKG Results` | Resting electrocardiographic results (Normal / Abnormal) |
| `Max HR` | Maximum heart rate achieved during exercise |
| `Exercise Angina` | Exercise-induced chest pain (Yes / No) |
| `ST Depression` | ST segment depression induced by exercise relative to rest |
| `Slope of ST` | Slope of the peak exercise ST segment |
| `Number of Vessels Fluro` | Number of major vessels colored by fluoroscopy (0–3) |
| `Thallium` | Thallium stress test result (3 = Normal, 6 = Fixed Defect, 7 = Reversible Defect) |
| `Heart Disease` | Target variable — Presence / Absence of heart disease |

**Total Patients:** 270 &nbsp;|&nbsp; **Heart Disease Presence:** 120 &nbsp;|&nbsp; **Heart Disease Absence:** 150

---

## 📊 Dashboard Walkthrough

### 1. Heart Disease Status (KPI Cards)

**What it shows:** Simple count cards displaying the total number of patients diagnosed with and without heart disease.

**Findings:**
- **150 patients** have an **absence** of heart disease (~55.6%)
- **120 patients** show a **presence** of heart disease (~44.4%)
- The dataset is fairly balanced, which is good for analysis — neither class overwhelmingly dominates

**Insight:** While absence is slightly more common, the nearly equal split means a meaningful proportion of patients in this cohort are at risk, making this dataset clinically significant.

---

### 2. Gender Distribution (KPI Cards)

**What it shows:** Count of patients split by biological sex.

**Findings:**
- **183 Male** patients
- **87 Female** patients

**Insight:** The dataset is male-heavy (roughly 68% male, 32% female). This is consistent with many clinical heart disease datasets since men are historically more likely to present with heart disease symptoms at younger ages. Analysis involving gender comparisons should be interpreted with this imbalance in mind.

---

### 3. Average Age & Average Cholesterol (Gauge Charts)

**What it shows:** Two radial gauge charts showing the mean values for age and cholesterol across all patients.

**Findings:**
- **Average Age: 54.43 years** (range: 0–108.87, representing dataset min–2× max)
- **Average Cholesterol: 249.66 mg/dL** (range: 0–499.32)

**Insight:**
- The average patient age of ~54 confirms this is a middle-to-older-aged cohort — consistent with heart disease being more prevalent with age.
- An average cholesterol of ~250 mg/dL sits right at the borderline of the clinically "high" threshold (≥240 mg/dL), suggesting a population already at elevated cardiovascular risk.

---

### 4. Fasting Blood Sugar (>120 mg/dL) by Gender — Clustered Bar Chart

**What it shows:** A grouped bar chart showing how many male and female patients have high vs. not-high fasting blood sugar levels.

**Findings:**
- The majority of both male and female patients fall in the **"Not High"** FBS category.
- Males with **"Not High"** FBS form the largest bar by far, which is expected given the larger male sample.
- A smaller but notable count of males have **"High"** FBS (>120 mg/dL), indicating a diabetic or pre-diabetic condition.
- Female patients are represented in much smaller counts across both categories.

**Insight:** Elevated fasting blood sugar (a marker for diabetes) is more prevalent among males in this dataset, though this could partly reflect the larger male sample. High FBS is a known independent risk factor for cardiovascular disease, and its presence in the dataset adds another layer to the risk profiling of these patients.

---

### 5. Heart Disease vs. Exercise-Induced Angina — Stacked Bar Chart

**What it shows:** A 100% stacked bar chart comparing the proportion of heart disease presence vs. absence among patients who do and do not experience exercise-induced angina.

**Findings:**
- Among patients who reported **"Yes"** to exercise angina, the proportion with heart disease **Presence** is significantly higher.
- Among patients with **"No"** exercise angina, the majority fall in the heart disease **Absence** category.

**Insight:** This is one of the most telling visuals in the dashboard. Exercise-induced angina (chest pain during physical activity) is a strong clinical indicator of underlying coronary artery disease. The chart clearly shows that angina patients are at dramatically higher risk, reinforcing its diagnostic importance.

---

### 6. Average Age by Heart Disease Status — Bar Chart

**What it shows:** A comparative bar chart of the mean age for patients with heart disease presence vs. absence.

**Findings:**
- Patients with heart disease **Presence** have a slightly **higher average age** than those with **Absence**.
- Both averages are close, hovering around 52–57 years.

**Insight:** While the age difference isn't dramatic, the trend is consistent with the known relationship between aging and heart disease risk. The progressive deterioration of cardiovascular function with age makes older patients more susceptible, even within a relatively narrow age range like this cohort.

---

### 7. Age Distribution of Heart Disease Patients — Histogram

**What it shows:** A histogram showing how patients are spread across different ages, with heart disease presence as the measure on the Y-axis.

**Findings:**
- Cases are concentrated primarily between **ages 40 and 70**.
- There's a noticeable peak around the **55–65** age range, suggesting this group has the highest patient count.
- Very few cases appear below 35 or above 75, which aligns with real-world epidemiology.

**Insight:** Heart disease risk accumulates with age, and this distribution confirms that the most vulnerable window in this dataset is the 55–65 bracket. Early preventive screening targeted at patients approaching 40 could help catch cases before they peak.

---

### 8. Heart Disease Distribution by Thallium Test Result — Donut Chart

**What it shows:** A donut chart breaking down all 270 patients by their Thallium stress test outcome, a nuclear imaging test that reveals blood flow to the heart.

**Thallium Categories:**
- **3 = Normal** blood flow
- **6 = Fixed Defect** (permanent damage — blood doesn't flow even at rest)
- **7 = Reversible Defect** (reduced flow during exercise, returns at rest)

**Findings:**
- **Thallium 7 (Reversible Defect): 152 patients (56.3%)** — the largest segment
- **Thallium 3 (Normal): 104 patients (38.52%)**
- **Thallium 6 (Fixed Defect): 14 patients (5.19%)**

**Insight:** Over half the patients showed reversible defects, meaning their heart muscle receives reduced blood flow during stress but recovers at rest. This is a hallmark sign of coronary artery disease. Only a small fraction had permanently fixed defects. The dominance of reversible defects in this cohort suggests that a large portion of these patients are candidates for intervention before permanent damage sets in.

---

## 🛠 Tools Used

- **Microsoft Power BI** — Dashboard design and interactive visualizations
- **Microsoft Excel** — Dataset storage and initial inspection
- **Kaggle** — Dataset source platform

---

> ⭐ If you found this helpful, consider starring the repository!
