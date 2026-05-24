# Factor Investing in 2026: From Fama-French to Neural Networks

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](factor_investing_2026.ipynb)

A comprehensive, reproducible walkthrough of modern factor investing: from classical Fama-French models through machine learning return prediction to neural network factor construction.

Accompanies the Medium article: [Factor Investing in 2026: From Fama-French to Neural Networks, and Everything That Can Go Wrong in Between](https://medium.com/@uchenna)

<img width="2574" height="1373" alt="fig2_cumulative_wealth" src="https://github.com/user-attachments/assets/6bb61271-0b86-4465-b95b-a7571dfdbe9a" />

---

## What this repo covers

The notebook implements the core techniques from the factor investing literature using real data from the Kenneth French Data Library.

**Classical factor models**
- Fama-French 5-factor returns analysis (1963-present)
- Cumulative wealth and decade-by-decade regime changes
- Factor correlation structure and redundancy testing
- Fama-MacBeth two-pass regressions with full GMM inference
- Pricing error visualisation and J-test for model specification

**Statistical validation**
- Bayesianised p-values (Harvey, 2017) across different prior beliefs
- Publication bias and false discovery rate discussion
- Factor competition analysis reproducing Fama and French (2015)

**Risk and herding**
- 2007 quant meltdown visualisation and analysis
- Factor autocorrelation (factor momentum)

**Machine learning**
- Simulated horse race: OLS, Ridge, Lasso, Elastic Net, Random Forest, Gradient Boosting, Neural Networks (1-layer and 3-layer)
- Out-of-sample R-squared using Gu, Kelly, and Xiu (2020) definition
- Demonstration of why nonlinear methods outperform when predictor interactions matter

**Neural network factor construction**
- NNAFC-style implementation following Fang et al. (2020)
- Differentiable rank approximation using sigmoid kernel (p=1.83)
- Spearman correlation as loss function
- Pre-training on technical indicators, then fine-tuning for IC maximisation
- Factor diversity comparison: GP-style vs NNAFC-style

---

## Repository structure

```
factor-investing-2026/
|
|-- factor_investing_2026.ipynb    # main notebook (fully executed, all outputs embedded)
|-- README.md                      # this file
|-- LICENSE                        # MIT license
|-- requirements.txt               # Python dependencies
|
|-- figures/
|   |-- fig1_factor_returns_timeseries.png
|   |-- fig2_cumulative_wealth.png
|   |-- fig3_factor_returns_by_decade.png
|   |-- fig4_factor_correlation.png
|   |-- fig5_pricing_errors.png
|   |-- fig6_bayesianised_pvalues.png
|   |-- fig7_quant_meltdown_2007.png
|   |-- fig8_factor_autocorrelation.png
|   |-- fig9_ml_comparison.png
|   |-- fig10_nnafc_construction.png
```

---

## Getting started

### Prerequisites

- Python 3.10 or higher
- pip

### Installation

1. Clone the repository:

```bash
git clone https://github.com/I-am-Uchenna/factor-investing-2026.git
cd factor-investing-2026
```

2. Create a virtual environment (recommended):

```bash
python -m venv venv
source venv/bin/activate        # Linux/macOS
venv\Scripts\activate           # Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Launch the notebook:

```bash
jupyter notebook factor_investing_2026.ipynb
```

### Data

The notebook pulls data directly from the Kenneth French Data Library at runtime. No manual data downloads are needed. An internet connection is required on first run.

Data sources used:
- [Fama-French 5 Factors (2x3)](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html)
- [25 Portfolios Formed on Size and Book-to-Market (5x5)](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html)

---

## Figures

| Figure | Description |
|--------|-------------|
| fig1 | Fama-French factor returns time series (1963-present) with recession shading |
| fig2 | Cumulative wealth: $1 invested in each factor on log scale |
| fig3 | Average annualised factor returns by decade |
| fig4 | Factor correlation heatmap |
| fig5 | Fama-MacBeth pricing errors: predicted vs realised returns for 25 portfolios |
| fig6 | Bayesianised p-values across skepticism levels (Harvey, 2017) |
| fig7 | The 2007 quant meltdown: monthly returns and cumulative drawdown |
| fig8 | Factor autocorrelograms (evidence for factor momentum) |
| fig9 | ML model comparison: linear vs nonlinear out-of-sample R-squared |
| fig10 | NNAFC factor construction: pre-training loss, IC evolution, and diversity |

---

## Key references

| Paper | Year | Topic |
|-------|------|-------|
| Fama and French, "The cross-section of expected stock returns" | 1992 | Size and value factors |
| Fama and French, "Common risk factors in the returns on stocks and bonds" | 1993 | Three-factor model |
| Fama and French, "A five-factor asset pricing model" | 2015 | Profitability and investment factors |
| Fama and MacBeth, "Risk, return, and equilibrium: Empirical tests" | 1973 | Two-pass regression procedure |
| Harvey, "Presidential address: The scientific outlook in financial economics" | 2017 | Bayesianised p-values |
| Harvey, Liu, and Zhu, "...and the cross-section of expected returns" | 2016 | Factor zoo, multiple testing |
| Khandani and Lo, "What happened to the quants in August 2007?" | 2007 | Quant meltdown analysis |
| Krkoska and Schenk-Hoppe, "Herding in smart-beta investment products" | 2019 | Smart beta herding risk |
| Gu, Kelly, and Xiu, "Empirical asset pricing via machine learning" | 2020 | ML methods comparison |
| Fang et al., "Neural network-based automatic factor construction" | 2020 | NNAFC framework |
| Coqueret and Guida, "Machine Learning for Factor Investing" | 2022 | Comprehensive reference |
| Sheppard, "Example: Fama-MacBeth regression" | 2023 | Python implementation |
| Leshno et al., "Multilayer feedforward networks..." | 1993 | Universal approximation theorem |
| Frankle and Carbin, "The lottery ticket hypothesis" | 2018 | Network pruning |

Full reference list with DOIs and URLs is in the notebook and the accompanying Medium article.

---

## Disclaimer

The content in this repository is for educational and research purposes only. Nothing here is financial advice, and none of it should be treated as a recommendation to buy, sell, or hold any security. I am not a financial advisor. Do your own research and consult a qualified professional before making any investment decisions.

---

## Author

**Uchenna Ejike**

- LinkedIn: [linkedin.com/in/uchenna-ejike](https://linkedin.com/in/uchenna-ejike)
- Portfolio: [my-portfolio-app-ten-azure.vercel.app](https://my-portfolio-app-ten-azure.vercel.app)
- GitHub: [github.com/I-am-Uchenna](https://github.com/I-am-Uchenna)

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
