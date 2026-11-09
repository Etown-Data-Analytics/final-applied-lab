# Scenario: Hospital Readmissions (Healthcare)

This is real, de-identified clinical data from 130 US hospitals, covering diabetic patient encounters. Hospital leadership wants to know who is likely to be readmitted soon after discharge, what distinguishes those patients, and whether patients break into meaningful risk groups worth managing differently after they leave.

## Business questions (address at least 2 of these 3, not just one)

- Which patients are likely to be readmitted within 30 days, and what  distinguishes them from patients who are not?
- Which factors (time in hospital, number of medications, prior  outpatient/emergency/inpatient visits, diagnoses, etc.) are associated  with higher or lower readmission risk?
- Can you group patients into meaningful segments and recommend a  different post-discharge follow-up strategy for each?

These are a starting point, not an exhaustive menu. If your team has a sharper question grounded in this data, or wants to push further (extra engineered features, more than one model compared, outside data brought in), go for it — just make sure it's still answerable with what's here, and run it by the instructor for approval.

## Data

Source: [Diabetes 130-US Hospitals for Years 1999-2008](https://archive.ics.uci.edu/dataset/296/diabetes-130-us-hospitals-for-years-1999-2008)
(UCI Machine Learning Repository, CC BY 4.0; Strack et al. 2014).

One file, `hospital_readmissions.csv` (`hospital_data.zip` on Canvas), one row per hospital encounter, 101,766 encounters. Note: patients can appear more than once (71,518 unique patients across the 101,766 encounters) — decide how you'll treat repeat encounters for the same patient and state your rule.

| Column | Meaning |
|---|---|
| `encounter_id`, `patient_nbr` | Unique identifiers for the encounter and the patient |
| `race`, `gender`, `age` | Patient demographics (`age` is a 10-year bucket, e.g. `[70-80)`) |
| `weight` | Patient weight bucket (see data-quality quirks — mostly missing) |
| `admission_type_id` | Coded: 1 = Emergency, 2 = Urgent, 3 = Elective, 4 = Newborn, 5/6/8 = unknown or not mapped, 7 = Trauma Center |
| `discharge_disposition_id` | Coded: 1 = discharged to home; other codes cover transfers to other facilities, hospice, and (11, 19, 20, 21) died during the encounter — see quirks below |
| `admission_source_id` | Coded source of admission (e.g. physician referral, ER, transfer from another facility) |
| `time_in_hospital` | Length of stay, in days |
| `payer_code`, `medical_specialty` | Insurance payer and admitting physician's specialty (see quirks — both have substantial missing values) |
| `num_lab_procedures`, `num_procedures`, `num_medications` | Counts of lab tests, procedures, and distinct medications during the encounter |
| `number_outpatient`, `number_emergency`, `number_inpatient` | Number of outpatient/ER/inpatient visits by this patient in the year before this encounter |
| `diag_1`, `diag_2`, `diag_3` | Primary and secondary diagnosis codes (ICD-9); treating these as categories is enough, you don't need to decode the codes |
| `number_diagnoses` | Total number of diagnoses entered for the encounter |
| `max_glu_serum`, `A1Cresult` | Glucose/A1C test results, if tested |
| `insulin`, `change`, `diabetesMed` | Whether insulin was prescribed, whether diabetes medication was changed, and whether the patient is on diabetes medication |
| `readmitted` | `NO`, `>30`, or `<30` — whether/when the patient was readmitted (see quirks, you'll need to derive your own flag) |

## Known data-quality quirks

This is real data, not cleaned for you. At minimum:

- `readmitted` is raw text with three values (`NO`, `>30`, `<30`), not a  0/1 flag — you'll need to derive your own "readmitted within 30 days"
  flag from it (`<30` = yes, `NO` and `>30` = no) and state your rule,  the same kind of decision as deriving a flag from raw text in Lab's  classification exercises.
- `weight` is blank (`?`) for about 97% of rows, `medical_specialty` for  about 49%, and `payer_code` for about 40%. Decide which of these  columns are usable at all, and state your rule for the rest (`race`  has a small number of blanks too).
- `discharge_disposition_id` codes 11, 19, 20, and 21 mean the patient  died during the encounter (about 1,650 rows). These patients can't be  readmitted by definition, not because they're healthy, so including  them unadjusted will distort a readmission model. Decide whether to  exclude them, same kind of by-definition-not-missing judgment call as  Rossmann's closed-store days.
