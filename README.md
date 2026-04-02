# US Data Center Emissions: Verifying Government Predictions Against Reality

**A three-phase analytical project using Python and R**

---

## Research Question
Are LBNL's 2024 congressionally-mandated predictions about U.S. data center 
CO2 emissions accurate when verified against independent 2025/2026 data?

---

## Key Findings

- LBNL underestimated CO2 emissions **every single year from 2014–2024**
- Average underestimation: **31.3% above LBNL predictions**
- Peer-reviewed actual 2024 emissions: **105 Mt CO2** — LBNL was off by **68.8%**
- Root cause: LBNL used flat **340 gCO2/kWh** vs actual **383–548 gCO2/kWh**
- DC energy consumption alone explains **99.6% of emissions variance** (R² = 0.9959)
- Every 1 TWh of data center energy adds **0.33 Mt CO2**
- By 2030, emissions projected at **107–173 Mt CO2** depending on AI growth rate
- Even the optimistic 2030 scenario exceeds the 2024 actual — emissions are locked in to rise

---

## Project Structure

```
├── energy_consumption_analysis.ipynb   # Python: EDA, prediction accuracy, forecasting
├── phase2_regression.Rmd               # R: OLS regression, factor analysis
├── master_dataset.csv                  # Combined dataset from 3 independent sources
└── README.md
```

---

## Methodology

### Phase 1 — EDA & Prediction Accuracy (Python)
- Built master dataset combining LBNL, Ember, and EIA data
- Quantified the gap between LBNL predictions and derived actuals
- Confirmed gap using peer-reviewed Guidi et al. (2024) as independent benchmark

### Phase 2 — Regression Analysis (R)
- OLS regression with 3 predictors: energy, carbon intensity, renewables %
- Isolated each variable to determine dominant driver
- Identified carbon intensity underestimation as root cause of LBNL error

### Phase 3 — Scenario Forecasting (Python)
- Applied regression coefficients to 3 energy growth scenarios
- Scenarios based on LBNL 2028 range and IEA 2030 projections
- Quantified emissions range: 107–173 Mt CO2 by 2030

---

## Data Sources

| Source | Role | Credibility |
|--------|------|-------------|
| LBNL 2024 US Data Center Energy Usage Report | Prediction baseline | U.S. Dept of Energy, congressionally mandated |
| Ember (2026) via Our World in Data | Grid carbon intensity | Independent, CC BY 4.0 |
| EIA Monthly Energy Review March 2026, Table 2.6 | Renewable energy % | U.S. govt statistical agency |
| Guidi et al. arxiv Nov 2024 | Actual emissions benchmark | Peer-reviewed, 2,132 data centers analyzed |
| IEA Energy and AI Report, April 2025 | 2024 energy verification | Independent international agency |

---

## Tools Used
- **Python** — pandas, matplotlib, seaborn, numpy
- **R** — ggplot2, dplyr, OLS regression (lm)
- **Jupyter Notebook** — EDA and forecasting
- **R Markdown** — regression analysis and reporting

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/yourusername/us-datacenter-emissions

# Install Python dependencies
pip install pandas matplotlib seaborn numpy

# Open Jupyter notebook
jupyter notebook energy_consumption_analysis.ipynb

# Open R Markdown in RStudio
# Open phase2_regression.Rmd and click Knit
```

---

## Author
**Lakshay Mani**  
MS Analytics, Northeastern University
