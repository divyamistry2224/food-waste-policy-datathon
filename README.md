# Accelerating America's Food Waste Reduction: A Federal Policy Framework

🏆 **3rd Place — GW Data Science Association Datathon 2026**

A data-driven federal policy recommendation to reduce U.S. food waste, built for GWU DSA's 2026 hackathon challenge: analyze ReFED's Food Waste Monitor dataset and design a realistic, evidence-backed policy intervention.

## The Problem

The U.S. generates ~70 million tons of food surplus every year, 71.5% of it preventable. Using ML to project each state's trajectory forward, this project found that **0 out of 50 states** are on track to meet the federal 2016–2030 waste-reduction goal.

## Approach

Rather than treating food waste as one undifferentiated problem, this project identified the 3 cause × sector combinations responsible for the majority of preventable surplus, then built a full analytical pipeline around them:

1. **EDA & Pareto analysis** — isolated the highest-impact cause/sector combinations from 16,455+ records
2. **7-model ML pipeline** — 4-algorithm regression comparison (Ridge best, LOO R² = 0.574), cause-level GradientBoosting (test R² = 0.885), K-Means sector clustering, Ward state clustering, state trajectory forecasting, PC-algorithm causal discovery, and counterfactual + Isolation Forest anomaly detection
3. **Causal validation** — confirmed harvest loss rate as a *causal* (not just correlated) driver of surplus, strengthening the case for targeted intervention
4. **Policy design** — translated findings into a 3-pillar federal policy framework, each pillar costed and ROI-quantified

## Key Findings

| Finding | Result |
|---|---|
| Preventable share of U.S. food surplus | 71.5% |
| States on track for the 2030 federal goal | 0 / 50 |
| Best model performance (cause-level) | Test R² = 0.885 |
| Combined policy impact (20% reduction) | 116.9M tons prevented, $576B recovered, 194.7B meals |
| Combined ROI | 93× |

## The 3-Pillar Policy

1. **Farm Recovery Act** — federal gleaning mandate + crop insurance reform for unharvested produce (24× ROI)
2. **Foodservice Efficiency & Donation Standard** — mandatory surplus reporting + demand-forecasting incentives (106× ROI)
3. **Federal Date Label Standardization** — one federal rule, two labels only (~1,493× ROI, highest-ROI lever in the dataset)

## Data & Methods

- **Primary data:** ReFED Food Waste Monitor (2010–2024) — cause, detail, summary, and state-level datasets
- **Supplementary data:** USDA ERS food insecurity rates, NOAA NCEI temperature (live API), USDA NASS produce values, US Census population
- **Tools:** Python, Pandas, scikit-learn, SHAP, causal-learn (PC algorithm), Matplotlib/Seaborn

## Repository Structure

```
├── notebooks/
│   └── food_waste_policy_analysis.ipynb   # Full 7-model analysis pipeline
├── data/
│   ├── ReFED_US_Food_Surplus_Cause_Summary.csv
│   ├── ReFED_US_Food_Surplus_Detail.csv
│   └── ReFED_US_Food_Surplus_Summary.csv
├── policy_brief.pdf                        # 1-2 page written policy recommendation
├── presentation.pdf                        # Final judging round slide deck
└── README.md
```

*Data sourced from the [ReFED Food Waste Monitor](https://insights-engine.refed.org/food-waste-monitor) (2010–2024). The three national-level datasets are included above; the two state-level datasets (State Detail, State Summary) are too large for GitHub and can be downloaded directly from the ReFED source. The notebook was originally run in Google Colab with data mounted from Google Drive — update the `DATA_PATH` variable to `data/` to run it locally.*

## Team

Built by Nidhi Naidu, Hritik Majgaonkar, and Divya Mistry for the GW Data Science Association Datathon 2026.
