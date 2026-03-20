# macro-regime-classifier
Build a data-driven system that classifies the current macroeconomic regime (e.g., Goldilocks, Reflation, Stagflation, Deflation) and maps it to expected asset class returns.

Objective: Build a data-driven system that classifies the current macroeconomic regime (e.g., Goldilocks, Reflation, Stagflation, Deflation) and maps it to expected asset class returns.
Data: FRED (CPI, unemployment, ISM, yield curve), Yahoo Finance (equity, bond, commodity ETFs), free via APIs.
Methodology:

- Construct 4–6 macro features (YoY CPI momentum, ISM level, yield curve slope, real rates, credit spread momentum)
- Apply unsupervised clustering (k-means, GMM) and/or Hidden Markov Model (HMM) to classify regimes
- Compute conditional expected returns and Sharpe ratios per asset class per regime
- Build a real-time regime tracker updated monthly

Risk framework: Walk-forward validation; report out-of-sample regime classification accuracy; examine regime transition probabilities.

AI use: Use an LLM (via API — GPT-4 or Claude) to summarise the current macro environment from FRED data and Fed minutes → cross-validate with your quantitative regime signal. Fully interpretable: the LLM reads text you provide; you read its output critically.

Stack: Python (Colab), FRED API, yfinance, hmmlearn, scikit-learn, GitHub.

Output: Interactive dashboard (Plotly/Streamlit via Colab), written research note.
