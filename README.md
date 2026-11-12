# Rwanda-health-facility-visits

A data analysis project focusing on health facility operations and patient visits in Rwanda.

## Question 2 - Build a Machine-Learning-Ready Dataset (Group 4)

**Members:** Jean Luc Tuyizere (26RP01265), Jean De Dieu Mugisha (26RP01151)

**Scenario:** predicting patient waiting times at Rwandan health facilities (regression, target `waiting_time_min`). The work prepares a model-ready dataset only; no prediction model is trained.

### Contents of `q2_own_scenario/`

| Path | What it holds |
|---|---|
| `notebooks/q2_waiting_time_data_preparation.ipynb` | The full work, Stages 0 to 6 (PC 1.1 - 1.4) |
| `data/raw/` | The original file, never edited |
| `data/interim/` | The cleaned file |
| `data/processed/` | `train.csv`, `validation.csv`, `test.csv` and the fitted pipeline |
| `docs/` | Documentation report (Word and PDF), scenario brief, proposal form, source log, data dictionary, data quality report, cleaning log, feature justification, definition of done, data card |
| `requirements.txt` | Library versions used |

### How to run

1. Install Python 3.13, then run `pip install -r q2_own_scenario/requirements.txt` and install Jupyter.
2. Open the notebook and choose **Restart and Run All**.
3. The MD5 fingerprints printed in section 6.4 must be the same on every run.

### Open items

The link, date accessed and licence of the data source, and a second source for the comparison table, are not yet documented. See `q2_own_scenario/docs/source_log.md`.
