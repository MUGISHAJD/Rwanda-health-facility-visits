# Scenario brief (illustrative case study written by the group)

Group 4 - Jean Luc Tuyizere (26RP01265), Jean De Dieu Mugisha (26RP01151) - Q2

> This scenario is a teaching case written by the group for this assignment. No real request was made by any institution.

**Who is asking.** The quality-improvement manager of a health planning team at the Ministry of Health (MoH) in Kigali. The manager wants to start with a pilot in **Nyabihu District, Western Province**, and later extend the work to other districts.

**The field.** Public health service delivery: outpatient visits at health centres, district hospitals and referral hospitals.

**The problem.** Patients complain that they wait a long time before they are seen. Long waits push patients to leave without care, crowd the waiting areas and add pressure on staff. Managers currently learn about long waits only after they happen.

**The decision a prediction would support.** If the waiting time of a visit could be estimated at the moment the patient arrives, a facility manager could (a) move staff to the departments and hours where long waits are expected, (b) advise scheduled patients to come at quieter hours, and (c) tell patients honestly how long they are likely to wait.

**What data exists.** One file of 1,200 visit records with 20 columns. It covers 22 districts in all five provinces from January 2024 to December 2025. Each record describes the facility, the visit date and arrival hour, the patient (age, sex, insurance), the department, the type of appointment, the distance and travel time, the number of earlier visits, the waiting time, the consultation time and whether the patient attended.

**What the manager asks us to deliver.** Not a model. The manager asks for a clean, documented, model-ready dataset (train, validation and test files), a reusable preparation function, and clear documents (data dictionary, source log, data quality report, cleaning log, feature justification, data card) so that an analyst can later train and test a model without redoing the preparation.

**Target variable.** `waiting_time_min` - the minutes a patient waits between arrival and the start of the consultation. It is a number, so this is a **regression** problem. Predicting it matters because it is the measure patients experience directly and the one managers can act on by changing staffing and scheduling.

**True origin of the data.** The group states that the file comes from NISR (National Institute of Statistics of Rwanda). This has not been verified: no link, download record or licence text is on file. The link, date accessed and licence are still to be added (see the Source Log in section 2.7). Until they are, nobody should present the records as verified Rwandan patient visits.

## Business questions the prepared data must answer

| No. | Business question |
|---|---|
| **BQ1** | Which facility levels and service departments have the longest waiting times? |
| **BQ2** | How does the time of the visit (arrival hour, day of week, month) relate to waiting time? |
| **BQ3** | Does the patient's location and access (province, district, distance, travel time) relate to waiting time? |
| **BQ4** | Do patient characteristics (age group, sex, insurance, earlier visits) relate to waiting time? |
| **BQ5** | Does the way the patient enters care (walk-in, scheduled, follow-up, referral) change the waiting time? |
