## Multimodal Clinical Monitoring in the Emergency Department (MC-MED) - Dataset information & structure

📁 Note: Due to GitHub’s file size limits and license restrictions, raw datasets are not stored in this repository.
🔗 Access it directly from [PhysioNet – MC-MED](https://physionet.org/content/mc-med/)
📜 Dataset licensed under the PhysioNet Credentialed Health Data License 1.5.0 (see LICENSE_PhysioNet.txt)


---

## Data Source and Tools

I collected data from “PhysioNet” which is a major online repository of freely available medical research data, managed by the MIT Laboratory for Computational Physiology.

From this repository, I am accessing the **MC-MED (Multimodal Clinical Monitoring in Emergency Department)** dataset which comprises over **118,000 adult emergency department visits at Stanford Health Care from 2020–2022**.

This dataset contains:
- Epic EHR  
- Free-text radiology reports  
- Vital signs  
- Physiologic waveforms  

Most files are provided in CSV format. Using mainly ICD9 and ICD10 (International Classification of Diseases Ninth and tenth revision). All necessary datasets have also been deidentified to protect patient privacy.

---

## MC-MED Dataset Overview

### 1. Structured EHR Data

- `visits.csv`: Patient demographics, arrival, triage, chief complaint, diagnosis, ED/hospital disposition, timestamps, payor, and more  
- `pmh.csv`: Past medical history (ICD9/ICD10/CCS codes)  
- `meds.csv`: Home medications at time of visit  
- `orders.csv`: All in-ED orders (labs, imaging, meds, procedures), with times  
- `labs.csv`: All lab tests, values, normal ranges, result times  
- `rads.csv`: Imaging studies, de-identified radiology report summaries  

### 2. Physiological Waveform Data

- `waveforms/` folder: ECG (lead II), PPG/Pleth, respiration; stored in WFDB format, segmented by visit  
- `waveform_summary.csv`: For each visit, lists which waveforms are available, how many segments, and total coverage time  

### 3. Minute-level Numeric Vital Signs

- `numerics.csv`: Heart rate, SBP, DBP, MAP, SpO₂, RR, temp, perfusion index, pain, LPM_O₂, heart rate variability (1/5 min)  
- Source labeled as either monitor-derived or manual nursing charting

---

## ❓ Common Q/A for This Project

**Q: What is PhysioNet?**  
PhysioNet (https://physionet.org) is a major online repository of freely available medical research data, managed by the MIT Laboratory for Computational Physiology. Established in 1999 with support from the US National Institutes of Health, its mission is to accelerate biomedical research and education by providing open access to large collections of physiological and clinical data, as well as related open-source software and tutorials.

PhysioNet hosts a wide range of datasets including EHRs, physiologic signals, imaging, and more from both healthy individuals and patients with various medical conditions. It is widely used by researchers, clinicians, and students for developing and benchmarking new methods in medical data analysis, machine learning, and clinical decision support. The platform also offers educational materials and organizes annual research challenges to foster innovation in health data science.

---

**Q: What isn’t covered / Dataset limitations?**

- Single centre (Stanford Emergency Department)  
- Potential noise, missingness (common to real-world EHR/waveform data)  
- De-identified: actual dates/ages are shifted/obfuscated; some research use cases (e.g., real-time calendrical trends) may be limited  
- Only adult patients (≥18 years)  
- Not all visits have all types of waveforms available (depends on monitoring/timeline)

---

**Q: What is MC-MED?**

MC-MED is a large, de-identified, multimodal clinical and physiological dataset of **118,385 adult ED visits (70,545 patients)** from the Stanford ED (Sep 2020–Sep 2022). It uniquely combines continuous high-frequency monitoring (waveforms/vital signs) with electronic health record (EHR) data, supporting advanced research in emergency medicine, monitoring, and machine learning.

Multimodal clinical monitoring refers to the practice of collecting and analysing multiple types of patient data at the same time to get a comprehensive view of a patient's health status, especially in acute or emergency settings.

---

**Q: What makes MC-MED unique?**

- Only dataset with continuous waveform monitoring for a large, diverse ED population (not just ICU)  
- Waveforms (ECG, PPG, Resp) matched to clinical events, labs, meds, imaging, free-text notes  
- Covers COVID/post-COVID era (2020–2022)  
- Meticulous deidentification:
  - Randomized MRN/CSN, age perturbation, patient-level timestamp shifting (preserving seasonality), PHI removal in free-text  
  - Extensive patient metadata: age, gender, race, ethnicity, visit/diagnosis codes, payor, visit sequences, subsequent outcomes

---

**Q: What were the pre-requisites for accessing this dataset?**

- Completing PhysioNet credentialing  
- CITI Training  
- Accepting the DUA and license terms  

---

**Q: What’s the granularity/frequency of vital signs and waveforms?**

- Numeric vital signs: ~1-minute means  
- Waveforms: continuous segments as available (ECG, PPG, Resp), durations noted per visit

---

**Q: Are pediatric patients included?**

- No, only ages 18 and up.

---

**Q: Can I link labs to waveform segments and clinical outcomes?**

- Yes — everything is linkable via CSN (visit ID) or MRN (patient ID)

---

**Q: How is patient privacy and confidentiality being protected?**

All patient and visit identifiers were replaced with random codes, and ages and dates were shifted to protect privacy. Free-text fields were automatically and manually reviewed to remove personal information. This comprehensive de-identification ensures the data is suitable for research while maintaining patient confidentiality.

The study was approved by the Stanford University Institutional Review Board (58581) with waiver of consent for retrospective research on de-identified, routinely collected data.

---
**DataSet Authors**: Aman Kansal, Emma Chen, Tom Jin, Pranav Rajpurkar, David Kim  
**Published**: March 3, 2025 (PhysioNet page & DOI)  
**Corresponding Author**: David Kim (Stanford)  
**License**: PhysioNet Credentialed Health Data License 1.5.0  
**Access**: Credentialed users, DUA, required CITI training  
**Download**: ~480 GB uncompressed; ZIP file (269.6GB)  
**GitHub tools & demos**: [dkimlab/MCMED](https://github.com/dkimlab/MCMED)
---

## Citations – APA Style

> Kansal, A., Chen, E., Jin, T., Rajpurkar, P., & Kim, D. (2025). *Multimodal Clinical Monitoring in the Emergency Department (MC-MED)* (version 1.0.0). PhysioNet. RRID:SCR_007345. https://doi.org/10.13026/jz99-4j81

> Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., ... & Stanley, H. E. (2000). *PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals.* Circulation, 101 (23), e215–e220. RRID:SCR_007345.
