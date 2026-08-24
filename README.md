# 🩺 Liver Disease Mortality Analysis (Power BI)

A clinical analytics dashboard analyzing mortality risk factors, laboratory indicators, and disease severity scores in patients with liver disease, built in Power BI.

## 📋 Project Overview

This project analyzes a clinical dataset of 621 liver disease patients to identify the key clinical, laboratory, and demographic factors associated with in-hospital mortality. The dashboard supports risk stratification using established clinical scoring systems (MELD, CTP, ACLF-EASL) and surfaces which factors are — and aren't — meaningful predictors of patient outcomes.

## 🧹 Data Preparation

- Selected the most clinically relevant columns for analysis
- Handled missing values based on each feature's distribution, data type, and proportion of missingness
- Cleaned and structured the dataset (`Patients_Cleaned`) for modeling and visualization

## 📊 Report Pages

### 1. Mortality Analysis Dashboard
Overview KPIs (621 total patients, 219 deaths, 35.27% mortality rate, average MELD score 16.91, average length of stay 7.77 days) alongside mortality breakdowns by gender, age group, and length of stay (LOS) — none of which showed meaningful differences in mortality rate. The standout finding: **MELD Risk** is the strongest differentiator, with mortality rising sharply from Low/Moderate to High/Very High risk groups.

### 2. Primary Diagnosis Analysis
A Treemap of patients by primary diagnosis and survival status. Alcoholic liver disease (EtOH) and Hepatitis C (HepC) are the most common diagnoses. While HepB has the highest mortality *rate* (~50%), its small sample size limits generalizability; EtOH's ~40% mortality rate carries more overall impact due to its high patient volume.

### 3. Patient Profile & Background
Explores demographic and lifestyle risk factors (diabetes, alcohol use, smoking) and primary liver disease (PLD) groups. Alcoholic and viral liver disease groups have the highest patient counts and death counts. A decomposition tree traces the path from survival status through PLD type, alcohol use, and smoking status.

### 4. Laboratory Indicators vs Disease Severity
Examines how average Bilirubin, INR, AST/ALT ratio, and Albumin change across MELD risk groups. Bilirubin and INR both show strong, consistent increases with disease severity — confirming their value as severity markers. Albumin generally declines with severity as expected, except for an anomalous increase in the Very High risk group, identified as a likely outlier rather than a true clinical trend (confirmed by isolating the Death subgroup, where the expected downward trend holds).

### 5. Blood Markers vs CTP Score
Analyzes Hemoglobin, Creatinine, WBC, and Platelet trends across Child-Turcotte-Pugh (CTP) scores. Creatinine rises and Platelet count falls as CTP increases — both consistent with disease progression (renal dysfunction and worsening cirrhosis, respectively). WBC shows no clear linear relationship with severity. Mortality also rises with CTP score (e.g., 1/21 deaths at CTP=5 vs. 29/52 at CTP=14).

### 6. Clinical Risk Factors Analysis
Covers DILI (Drug-Induced Liver Injury), ACLF-EASL organ failure count, Infection status, GI Bleeding (GIB), Acute Renal Failure (ARF), and Precipitant Factors. Key findings:
- **ACLF-EASL** (number of failing organs) is one of the strongest predictors — mortality rises from 25% (no organ failure) to ~69% (3+ organs)
- **ARF** patients have a 42% mortality rate vs. 32% without
- **Infection** is associated with higher mortality (38% vs. 31%)
- **DILI** and **GIB** show minimal or inconsistent association with mortality in this dataset
- **Active alcohol use** and **combination precipitants** carry the highest mortality rates among triggering factors

## 🔍 Key Clinical Findings

- Overall mortality rate: **35.27%** — indicating a predominantly advanced-disease patient population
- Gender, age group, and length of stay show **no meaningful difference** in mortality — none are strong standalone predictors
- **MELD Risk**, **CTP Score**, and **ACLF-EASL organ failure count** are the strongest and most clinically consistent predictors of mortality
- Laboratory markers (Bilirubin, INR, Creatinine) trend clearly with disease severity, while WBC does not
- **ARF** and **Infection** meaningfully increase mortality risk; **DILI** and **GIB** do not show a strong independent effect in this dataset
- An anomalous Albumin value in the most severe group was correctly identified and attributed to a data outlier rather than a real clinical pattern — demonstrating careful, critical interpretation of the data

## 🛠️ Tools Used

- Power BI Desktop
- Power Query (data cleaning)
- DAX (calculated measures and risk groupings)
- Decomposition Tree, Treemap, and interactive drillthrough visuals

## 📁 Deliverables

- `.pbix` file with a 6-page interactive clinical dashboard
- Cleaned and modeled patient dataset
- Written clinical interpretation for each dashboard page

## 📬 Contact

**Negar Yeganeh**  
[GitHub](https://github.com/NegarYS) · [LinkedIn](https://linkedin.com/in/negar-yeganeh)
