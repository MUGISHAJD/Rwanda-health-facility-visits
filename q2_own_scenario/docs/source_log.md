# Source Log - Q2

Group 4 - Jean Luc Tuyizere (26RP01265), Jean De Dieu Mugisha (26RP01151) - Q2

| Field | Entry |
|---|---|
| Source | File `rwanda_health_facility_visits.csv`. Source: NISR (National Institute of Statistics of Rwanda), as stated by the group. This has not been verified: no link, download record or licence text is on file. |
| Link | **TO BE COMPLETED BY THE GROUP** |
| Date accessed | **TO BE COMPLETED BY THE GROUP** |
| Licence | **Not on file - TO BE COMPLETED BY THE GROUP** (check the NISR terms of use for this dataset) |
| Who collected it | Stated source: NISR. The collection method (survey, facility register, other) is not documented. |
| File fingerprint | MD5 `fe54529b0294f43151a9f5b8815d01a7`, 186,300 bytes, 1,200 rows x 20 columns |
| Limitations | (1) The source is stated by the group as NISR but is not verified; the link, collection method and licence are not documented. (2) No documentation of column meanings; all meanings are assumed. (3) Only about 55 records per district, too few to study one district alone. (4) 168 records have no waiting time. (5) Some records are not logical (adults in Child Health, men in Maternal Health; measured in section 3.4). (6) The record codes run exactly from 1 to 1,200 and the facility codes follow a fixed pattern. These are signs that the file may have been generated and may not be a real extract of facility records. This is our observation, not a confirmed fact. |
| Risk of applying it to Rwanda | Until the origin is confirmed, results from this data must not be presented as facts about Rwandan health facilities. If the data is synthetic or comes from elsewhere, patterns in it may not hold in Rwanda. |
| Ethical issues - privacy | No names, phone numbers or national IDs. If the records are real, the mix of district, facility, date, age and sex could help to identify a person, so the file should not be published. `visit_id` and `facility_code` are removed from the final files. |
| Ethical issues - bias | Referral hospitals have very few records (about 3%), so they are weakly represented. Districts are missing (22 of 30 are present). Visits where the patient did not attend have no waiting time, so the prepared data describes only patients who stayed to be seen. |

## Source comparison

| Criterion | Source A - `rwanda_health_facility_visits.csv` (chosen) | Source B |
|---|---|---|
| Relevance | High: one row per visit, with a waiting time and the facility, time, location and patient columns the business questions need. | None - the group did not consider a second source |
| Size | 1,200 rows x 20 columns. | Not assessed |
| Licence | **Not on file - TO BE COMPLETED BY THE GROUP** | Not assessed |
| Quality | Has missing values, duplicate rows, untidy text and outliers (measured in Stage 3). | Not assessed |
| Reason for the choice | It is the only source the group considered. | - |

**Gap to note:** the task asks for at least two sources to be compared. The group considered only one, so this table cannot show a real comparison. We did not invent a second source. To meet the requirement, the group should look at one real alternative and fill in the right-hand column.
