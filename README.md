# Landing page A/B experiment

[Open the analysis notebook](S9_Landing_Experiment_Portafolio.ipynb)

Which landing page converts more visitors, and how much do buyers spend on each version?

## Overview

This educational portfolio project evaluates two landing page variants using 40,000 user records. The analysis combines exploratory checks, hypothesis testing and visualizations to support a decision about the page version and identify follow-up questions for marketing.

**Tools:** Python, Pandas, NumPy, SciPy, statsmodels, Matplotlib, Seaborn and Jupyter.

## Findings

| Version | Visitors | Conversions | Conversion rate |
| --- | ---: | ---: | ---: |
| A | 19,982 | 2,512 | 12.57% |
| B | 20,018 | 3,194 | 15.96% |

Version B led by **3.39 percentage points** in the observed experiment. A two-sided proportions test found a conversion difference (p < 0.001). Among buyers, average spending was also higher on B (Welch’s t-test, p < 0.001). These two measures support selecting B for a monitored rollout.

Traffic source was associated with conversion (chi-square p = 0.0341). The comparison of new and returning users produced p = 0.4736. Channel comparisons describe associations, and spend per buyer measures a different outcome from revenue per visitor.

## Scope and interpretation

The recommendation follows the observed conversion and spending results. Profitability also depends on costs and margins, which this analysis does not calculate. Comparisons across traffic sources describe associations rather than the causal effect of a channel. The reported tests use a significance level of 0.05, without a multiple-testing adjustment. A non-significant comparison of user types leaves uncertainty about the size of a possible difference.

The statistics above come from the saved notebook execution. Publication preparation preserved those outputs. The full analysis has not been rerun because the source CSV is currently unavailable in this package.

## Method

User-level records supply the page version, conversion flag, spending, traffic source and user type. The notebook checks the groups, compares spending among buyers with Levene’s test and Welch’s t-test, compares conversion with a two-proportion Z-test, and examines customer segments with contingency tables and charts.

## Reading the project

The Spanish-language notebook includes the tables and figures from the original educational analysis. Open it on GitHub to inspect the saved results. To reproduce the calculations locally, obtain the original course CSV files and follow the steps below.

## Repository contents

| File | Purpose |
| --- | --- |
| `S9_Landing_Experiment_Portafolio.ipynb` | Analysis, explanations, statistical tests and saved figures. |
| `README.md` | Project overview, findings and execution instructions. |
| `requirements.txt` | Python dependencies. |
| `.gitignore` | Excludes local datasets, environment and temporary files. |

The course dataset is named `landing_experiment.csv`. Its fields include `user_id`, `date`, `landing`, `region`, `dispositivo`, `traffic_source`, `user_type`, `converted` and `gasto`. The file must be obtained separately from the original course materials.

## Local setup

Use Python 3.11 and start in the repository folder. Create a virtual environment and activate it.

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Create a folder named `data` next to the notebook. Place the original CSV files in it using these names:

```text
data/landing_experiment.csv
```

The source data are supplied separately. The repository includes the notebook, this guide, the Python requirements and a Git ignore file for local data and environment files.

Launch `python -m jupyter lab`, open `S9_Landing_Experiment_Portafolio.ipynb`, select the environment’s Python kernel and run the cells in order.

**Author** · Andres Martinez Sampayo · [GitHub profile](https://github.com/andres-martinez-sampayo)
