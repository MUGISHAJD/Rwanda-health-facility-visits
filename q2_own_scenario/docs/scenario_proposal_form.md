# Scenario Proposal Form - Q2

| Field | Entry |
|---|---|
| Group | **Group 4** |
| Members | Jean Luc Tuyizere (26RP01265); Jean De Dieu Mugisha (26RP01151) |
| Title | Predicting patient waiting times at Rwandan health facilities |
| Location | Pilot: Nyabihu District, Western Province. Data covers 22 districts in 5 provinces. |
| Stakeholder | Quality-improvement manager, health planning team, Ministry of Health (illustrative) |
| Story and decision | Patients at health centres and hospitals often wait a long time before they are seen. The manager wants to know, at the moment a patient arrives, how long that patient is likely to wait. With that estimate a facility can move staff to busy departments and hours. It can also advise scheduled patients to come at quieter times. The manager first needs a clean, well-documented dataset, because the visit records have gaps, repeated rows and untidy text. Our task is to prepare that dataset so that a model can be trained later. We do not train the model. |
| Who benefits | Patients (shorter and more predictable waits), facility managers (staff planning), district and national planners (comparison between facilities) |
| Target | `waiting_time_min` (minutes waited before consultation) |
| Problem type | Regression |
| Data source and link | NISR (National Institute of Statistics of Rwanda), as stated by the group; file `rwanda_health_facility_visits.csv`. **Link, date accessed and licence: TO BE COMPLETED BY THE GROUP** |
| Expected rows and columns | Raw: 1,200 rows x 20 columns. Usable rows with a waiting time after cleaning: about 1,027 |
| Known risks - privacy | No names, phone numbers or national IDs. `visit_id` and `facility_code` are record and facility codes; both are removed from the final files. Age, sex, district and visit date together could narrow down a person if the records are real. |
| Known risks - licence | Licence not on file. The NISR terms of use for this dataset must be checked and recorded. |
| Known risks - missing data | 14 of 20 columns have gaps. 168 records have no waiting time and cannot be used. |
| Lecturer approval signature | ______________________  Date: ____________ |
