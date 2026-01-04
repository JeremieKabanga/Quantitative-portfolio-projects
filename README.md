# 📊 Quantitative Portfolio Management Projects

**Advanced portfolio optimization and risk management using R**

[![R](https://img.shields.io/badge/R-4.0+-blue.svg)](https://www.r-project.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

---

## 🎯 Overview

This repository contains three advanced quantitative portfolio management projects implemented in R, demonstrating expertise in:

- **Dynamic risk modeling** (GARCH, EWMA)
- **ESG integration** (Black-Litterman, Refinitiv scores)
- **Portfolio insurance** (OBPI, CPPI, Monte Carlo)
- **R programming** (tidyverse, PerformanceAnalytics, rugarch)

---

## 📁 Projects

### 1️⃣ **GMV Portfolio with Dynamic Volatility (GARCH + EWMA)**

**Objective:** Construct a Global Minimum Variance (GMV) portfolio using dynamic volatility forecasting to improve risk-adjusted returns.

**Key Features:**
- **Universe:** 30 stocks (MSCI World - US, Europe, Asia-Pacific)
- **Methodology:** 
  - GARCH(1,1) for individual asset volatility forecasting
  - EWMA (λ=0.94) for dynamic correlation matrix
  - Monthly rebalancing with long-only constraints
- **Results:**
  - **18% volatility reduction** vs static covariance approach
  - Superior Sharpe ratio vs equal-weight benchmark
  - Effective protection during market stress (2020 COVID, 2022 sell-off)

**📂 Directory:** [`01-gmv-dynamic-garch/`](01-gmv-dynamic-garch/)

**Technologies:** R (rugarch, PerformanceAnalytics, quadprog, tidyquant)

---

### 2️⃣ **ESG & Transition Risk Portfolio (Black-Litterman)**

**Objective:** Compare three portfolio allocation strategies integrating ESG and climate transition risk using Refinitiv (LSEG) data.

**Key Features:**
- **Universe:** 7 French stocks (CAC40) + Green Bond
- **Strategies:**
  1. **Baseline:** Traditional mean-variance (Markowitz)
  2. **ESG-Integrated:** Black-Litterman with Refinitiv ESG scores
  3. **Transition Risk:** TCFD-aligned climate risk adjustment
  
- **Results:**
  - **ESG portfolio:** Best Sharpe ratio (out-of-sample)
  - **26% Sharpe improvement** vs Baseline
  - **Divergence analysis:** ESG scores vs Climate risk reveal hidden risks

**📂 Directory:** [`02-esg-transition-portfolio/`](02-esg-transition-portfolio/)

**Technologies:** R (tidyverse, PerformanceAnalytics, MASS)

**Data Sources:**
- **ESG Scores:** Refinitiv (LSEG) ESG Database (630+ indicators)
- **Transition Risk:** TCFD framework + EU Taxonomy alignment

---

### 3️⃣ **Portfolio Insurance: OBPI vs CPPI with Decrement Index**

**Objective:** Compare two portfolio insurance strategies (OBPI optimized with Call Spread vs CPPI on decrement index) using Monte Carlo simulation.

**Key Features:**
- **Simulation:** 10,000 paths, 12-month horizon
- **Strategies:**
  1. **OBPI Optimized:** Call Spread (Strike 100 / Cap 130) on decrement index
  2. **CPPI Optimized:** Dynamic allocation (multiplier=5) on decrement index
  
- **Results:**
  - **OBPI:** Higher gearing (vs standard), deterministic payoff, optimal for central scenario
  - **CPPI:** Path-dependent, high "cash lock" risk due to decrement drag (5% p.a.)
  - **Winner:** OBPI Call Spread for 100-130 range

**📂 Directory:** [`03-portfolio-insurance/`](03-portfolio-insurance/)

**Technologies:** R (Monte Carlo, Black-Scholes pricing, dynamic allocation)

---

## 🛠️ Technical Implementation

### **Installation**

```r
# Install required packages
install.packages(c(
  "tidyverse", "tidyquant", "PerformanceAnalytics", 
  "rugarch", "quadprog", "corrplot", "DataExplorer",
  "knitr", "kableExtra", "ggrepel", "scales"
))
```

### **Usage**

Each project contains an R Markdown file (`.Rmd`) that can be run independently:

```r
# Project 1: GMV Dynamic
rmarkdown::render("01-gmv-dynamic-garch/gmv_dynamic.Rmd")

# Project 2: ESG Transition
rmarkdown::render("02-esg-transition-portfolio/esg_transition.Rmd")

# Project 3: Portfolio Insurance
rmarkdown::render("03-portfolio-insurance/obpi_cppi.Rmd")
```

Each renders to an HTML report with:
- Interactive visualizations
- Performance metrics
- Statistical tables
- Detailed analysis

---

## 📊 Key Results Summary

| Project | Strategy | Key Metric | Result |
|---------|----------|------------|--------|
| **1. GMV Dynamic** | GARCH + EWMA | Volatility reduction | **-18%** vs static |
| **2. ESG Portfolio** | Black-Litterman | Sharpe improvement | **+26%** vs baseline |
| **3. OBPI vs CPPI** | Call Spread | Gearing | **3.5x** vs standard |

---

## 🎓 Academic Context

**Author:** Jérémie Kabanga  
**Institution:** Université Paris-Saclay  
**Program:** Master 2 Finance - Asset & Risk Management  
**Date:** November 2025 - January 2026  

**Certifications:**
- LSEG Workspace Essentials Certificate (January 2026)
- Bloomberg Market Concepts (January 2026)

---

## 📚 Methodologies

### **Project 1: Dynamic Volatility Modeling**
- **GARCH(1,1):** Captures volatility clustering and mean reversion
- **EWMA Correlation:** Adapts to changing market regimes (λ=0.94)
- **GMV Optimization:** Minimizes portfolio variance subject to budget constraint

### **Project 2: ESG Integration**
- **Black-Litterman:** Combines market equilibrium with subjective views
- **Refinitiv ESG:** 630+ indicators across E, S, G pillars
- **TCFD Framework:** Climate transition risk scoring (stranded assets, carbon pricing)

### **Project 3: Portfolio Insurance**
- **OBPI:** Floor + Call option (deterministic payoff)
- **CPPI:** Dynamic allocation based on cushion (path-dependent)
- **Decrement Index:** Dividend-adjusted index (reduces option cost)

---

## 📈 Visualizations

### GMV Dynamic - Rolling Volatility
![Rolling Volatility](01-gmv-dynamic-garch/results/rolling_volatility.png)

### ESG Portfolio - Allocations Comparison
![Allocations](02-esg-transition-portfolio/results/allocations_comparison.png)

### OBPI vs CPPI - Payoff Profile
![Payoff](03-portfolio-insurance/results/payoff_comparison.png)

---

## 🔬 Key Learnings

1. **Dynamic risk modeling** significantly improves downside protection vs static approaches
2. **ESG integration** can enhance risk-adjusted returns (not just screening)
3. **Climate risk** (TCFD) reveals hidden risks not captured by traditional ESG scores
4. **Portfolio insurance** strategies have very different risk profiles (deterministic vs path-dependent)
5. **R ecosystem** (tidyverse, rugarch, PerformanceAnalytics) enables professional-grade quantitative analysis

---

## 🚀 Future Enhancements

- [ ] Extend GMV to multi-period rebalancing with transaction costs
- [ ] Integrate alternative data (sentiment, news) for ESG views
- [ ] Machine learning for ESG score prediction
- [ ] Compare OBPI/CPPI with volatility targeting strategies
- [ ] Real-time portfolio monitoring dashboard (Shiny)

---

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

---

## 📧 Contact

**Jérémie Kabanga**  
📧 Email: jeremiekabanga06@gmail.com  
💼 LinkedIn: [linkedin.com/in/jeremie-kabanga](https://linkedin.com/in/jeremie-kabanga)  
🐙 GitHub: [github.com/jeremiekabanga](https://github.com/jeremiekabanga)

---

## 🙏 Acknowledgments

- Université Paris-Saclay Finance Department
- LSEG (Refinitiv) for ESG data access
- R community (tidyverse, PerformanceAnalytics, rugarch maintainers)

---

**⭐ If you find this work useful, please consider giving it a star!**
