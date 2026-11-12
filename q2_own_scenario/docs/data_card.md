# Data Card - Patient waiting times, model-ready dataset (Q2)

**Group:** Group 4 - Jean Luc Tuyizere (26RP01265), Jean De Dieu Mugisha (26RP01151)

## Purpose
A model-ready dataset to predict `waiting_time_min` (regression): the minutes a patient waits before consultation at a health facility. Prepared for an illustrative Ministry of Health scenario with a pilot in Nyabihu District. No model has been trained.

## Source
File `rwanda_health_facility_visits.csv` (MD5 `fe54529b0294f43151a9f5b8815d01a7`). Source as stated by the group: NISR (National Institute of Statistics of Rwanda). **This is not verified; link, date accessed and licence are TO BE COMPLETED BY THE GROUP.** Until they are on file, the data must not be presented as verified Rwandan facility records. No second source was considered.

## Size
- Raw: 1,200 rows x 20 columns (2024-01-02 to 2025-12-30, 22 districts, 5 provinces).
- Clean (`data/interim/visits_clean.csv`): 1,027 rows x 16 columns.
- Final (`data/processed/`): train 718, validation 154, test 155 rows; 22 features + 1 target.

## Columns
- **Target:** `target_waiting_time_min` (minutes, not scaled, not transformed).
- **Features (22):** `arrival_hour`, `facility_level`, `province_kigali_city`, `province_northern`, `province_southern`, `province_western`, `service_department_dental`, `service_department_emergency`, `service_department_eye_clinic`, `service_department_general_outpatient`, `service_department_maternal_health`, `service_department_ncd_clinic`, `appointment_type_referral`, `appointment_type_scheduled`, `appointment_type_walk_in`, `age_group`, `is_peak_hour`, `walkin_at_peak`, `dept_median_wait`, `district_median_wait`, `level_dept_median_wait`, `hospital_at_peak`.
- Continuous columns are standardised with the training mean and standard deviation. 0/1 columns and the codes `facility_level` (0-2) and `age_group` (0-4) are not scaled.

## Cleaning steps
1. Tidied text (spaces, upper/lower case). 2. Removed 5 duplicate rows. 3. Converted `visit_date` to a date. 4. Rebuilt 10 empty `facility_type` values from the facility code prefix. 5. Checked for impossible values (none found). 6. Kept all outliers (all are possible values). 7. Dropped leakage columns (`consultation_duration_min`, `attended`) and identifiers (`visit_id`, `facility_code`). 8. Removed 168 records with no target. 9. Split 70/15/15 (seed 42, stratified by `facility_type`). 10. Imputed with training medians, modes and a group median. 11. Encoded (ordinal for facility level, one-hot for the rest).

## Feature steps
11 features were engineered; 7 are in the final files (age_group, is_peak_hour, walkin_at_peak, dept_median_wait, district_median_wait, level_dept_median_wait, hospital_at_peak), of which 6 passed the statistical rule and the others are kept for a business question. Skewed amount columns were transformed (rule: skewness > 1 log, 0.5-1 square root, kept only if the result is inside -0.5 to 0.5). Selection on the training set: constant, duplicated and |r| > 0.9 filters, then SelectKBest (F-test) with K = number of features with p < 0.05 (K = 12); columns needed by the business questions were kept.

## Limitations and bias risks
- **Source not verified.** The stated source is NISR, with no link or licence on file. There are signs that the file may be generated (record codes run exactly 1 to 1,200; fixed facility-code pattern). Applying results to Rwanda is a risk until the source is confirmed.
- **Small sample.** 1,027 usable records, about 47 per district; referral hospitals have only 30 records.
- **Illogical records kept.** 105 Child Health visits with a patient aged 18+, and 77 Maternal Health visits with a male patient (counts in the raw file).
- **Survivorship.** Visits where the patient did not attend have no waiting time and are excluded, so the data describes only patients who stayed.
- **Assumptions.** All column meanings and allowed ranges are assumed. `None` in `insurance_type` is read as "no insurance".
- **Coverage.** 22 of Rwanda's 30 districts appear. The three group-median features use the target (training records only) and look slightly stronger in training than on new data.
- **Privacy.** No names, phone numbers or national IDs. Identifier columns are removed from the final files.

## How to reproduce
Python 3.13 with pandas, numpy, matplotlib, seaborn, scikit-learn and joblib. Open `notebooks/q2_waiting_time_data_preparation.ipynb` and choose Restart and Run All. The notebook reads `data/raw/rwanda_health_facility_visits.csv` (never edited), writes the clean file, the three final files and `preparation_pipeline.joblib`, and prints MD5 fingerprints that must match on every run. Use `prepare_new_data(raw_records, joblib.load(...))` for new records.
