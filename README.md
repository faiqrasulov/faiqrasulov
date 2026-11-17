### Hi, I'm Faiq: data scientist in Baku, blending business strategy with data-driven insights.

I like questions where a model has to earn its place: *Will this price change pay off? Is this test
result real? Which alert deserves an analyst's time?* Below are ten end-to-end projects that answer
questions like these with tested code and results you can reproduce with one command.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Faiq%20Rasulov-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/faiq-rasulov-0a585379/)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?logo=postgresql&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?logo=tableau&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)

---

#### Decision science: experiments, causality, risk and customer value

| Project | The question | What the results show |
|---|---|---|
| [**ab-testing-toolkit**](https://github.com/faiqrasulov/ab-testing-toolkit) | Can we trust this A/B test? | Peeking at a 5% test 10 times gives **19.5%** false positives; group-sequential boundaries keep it at **5%**. CUPED is worth **5.2x** the sample size at ρ = 0.9. All of this is verified by simulation. |
| [**price-elasticity-causal-ml**](https://github.com/faiqrasulov/price-elasticity-causal-ml) | How much does price really move demand? | Naive regression estimates **−0.37** for a true elasticity of **−1.66**. From-scratch Double ML and IV recover it, and pricing from the biased estimate costs **3.7%** of profit. |
| [**credit-risk-scorecard**](https://github.com/faiqrasulov/credit-risk-scorecard) | Who should get a loan, at what cost of error? | A from-scratch WoE scorecard matches gradient boosting on AUC (**0.780** vs 0.783) and on expected cost, while staying interpretable. Adds reason codes, a fairness audit and a FastAPI service. |
| [**customer-lifetime-value**](https://github.com/faiqrasulov/customer-lifetime-value) | Which customers are worth keeping? | BG/NBD and Gamma-Gamma models built from scratch: the top 10% of customers hold **46.8%** of predicted 12-month value. Churn turns out not to be identifiable in this data, and **53%** of RFM "At risk" customers came back with no campaign, so a win-back budget should be tested first, not assumed. |

#### AI and machine-learning engineering

| Project | The question | What the results show |
|---|---|---|
| [**hybrid-search-rag**](https://github.com/faiqrasulov/hybrid-search-rag) | Does the retrieval in RAG actually work? | Hybrid BM25 + dense search reaches nDCG@10 **0.725** vs **0.683** for BM25 on BEIR SciFact, tuned on train only. The answer layer (Claude, with cited sources) is written but not yet evaluated. |
| [**ml-drift-monitor**](https://github.com/faiqrasulov/ml-drift-monitor) | Is the deployed model still OK? | The common "PSI > 0.2" rule raises **46%** false alarms on small windows yet misses a real regional shift; calibrated tests hold about **5%**. |
| [**autograd-from-scratch**](https://github.com/faiqrasulov/autograd-from-scratch) | What does `loss.backward()` really do? | A NumPy autodiff engine with Conv2d and Adam whose training runs match PyTorch to **1e-15** at every step. |

#### Predictive modelling, evaluated honestly

| Project | The question | What the results show |
|---|---|---|
| [**demand-forecasting-backtest**](https://github.com/faiqrasulov/demand-forecasting-backtest) | How many will we need next week? | In a 12-origin rolling backtest, daily ETS beats seasonal naive on **12/12** origins (WAPE **21.2%** vs 29.0%). Conformal prediction intervals included. |
| [**movielens-recommender**](https://github.com/faiqrasulov/movielens-recommender) | What should this user watch next? | EASE^R, iALS and BPR built from scratch. A random split inflates NDCG about **2x** compared with a per-user temporal split. |
| [**anomaly-detection-benchmark**](https://github.com/faiqrasulov/anomaly-detection-benchmark) | Which detector should raise the alert? | Across 8 detectors, ROC-AUC **0.935** can still mean AP **0.091**. Detectors are scored for alert budgets, not leaderboards. |

---

#### How these projects are built

- **Reproducible:** each repo pins its package versions in `requirements.lock`; with them,
  `make run` regenerates the README's numbers from public data: exactly in seven projects, and to
  within small numerical differences in three, as each README states.
- **Verified:** core methods are tested against independent references (PyTorch, statsmodels,
  SciPy, closed forms, simulations with known ground truth). CI runs on every push.
- **Evaluated on held-out data:** temporal splits, tuning on train or validation only, bootstrap
  confidence intervals, and comparisons against simple baselines.
- **Honest about limits:** every README says what did not work and where the method breaks.

#### Earlier work (2023)

Twenty coursework notebooks and scrapers, each with a README that states the result and what is
wrong with it. Three to start with:

- [Rain prediction](https://github.com/faiqrasulov/Rain_Prediction_Neural_Network-): the notebook reported 68% test accuracy; the cause was a shuffled test loader, and the fixed evaluation gives 85%.
- [Electricity contract selection](https://github.com/faiqrasulov/Electricity_Contract_Selection): 8,760 free-text meter readings parsed with one regular expression and priced under three contracts.
- [Supermarket price tracking](https://github.com/faiqrasulov/Web_Scraping_Azerisupermarketchains): scheduled scrapers for three Azerbaijani chains with monthly comparison files.
