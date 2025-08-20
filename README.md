# economic-hedge-regimes
Python analysis of economic regimes (growth/inflation) and cross-asset hedging strategies for the S&amp;P 500. Includes gold, US Treasuries, USD index, and safe-haven currencies like USD/CHF, with extensions into yield curve analysis and machine learning overlays.

SPX Regime Hedging — Gold & UST Mix, Markov Overlay, IBKR Extensions

To find the optimal hedge for the S&P 500 using a mix of Gold and U.S. Treasuries, conditioned on economic regimes (growth & inflation trends).
Extras include IBKR live data pulls, sector rotation with defensives, and a Markov (regime‑switching) optimizer for forward‑looking hedge weights. Optional extensions cover the yield curve, cross‑asset hedges (USD, oil, copper), and USD/CHF as a safe‑haven overlay.

What’s inside

Regime Definition: CPI YoY vs 12‑m mean; GDP YoY vs 24‑m mean → Goldilocks / Reflation / Disinflation / Stagflation.

Hedge Engine: 
Basket 𝐻(𝑤)=𝑤⋅Gold+(1−𝑤)⋅UST, hedge ratio

𝛾\*(𝑤)=−Cov(𝑆,𝐻)/Var(𝐻)

Risk Objectives: Variance‑min, CVaR(5%)‑min, MaxDD‑min per regime.

Visuals: Variance‑reduction heatmaps, w–γ–variance 3D surfaces, rolling correlations, regime timelines.

Markov Portfolio Optimization: Transition matrix 
𝑃, 𝑃^6 (6‑month), expected hedged variance vs 𝑤 (1M vs 6M), optimal 𝑤,𝛾 by horizon.

Sector Rotation: 12‑1 momentum + inverse‑vol, defensive blend (XLP/XLU/XLV) in Risk‑Off; optional GLD/IEF overlay.

IBKR Integration: Robust historical pulls (Gateway 4002), delayed data support, pacing, safe merges with your Excel.

Yield Curve (extension): 2s10s & 3m10y slope regimes to steer Gold vs UST; easily added panel.

Cross‑Asset & FX (extension): USD index, oil/copper basket, USD/CHF as safe‑haven overlay.

# Economic Hedge Regimes

## Overview
This project analyzes economic regimes based on growth and inflation trends, and tests cross-asset hedges for the S&P 500.  
Hedges include:  
- Gold  
- US Treasuries (USTs)  
- USD Index  
- Commodities basket (oil, copper)  
- Safe haven currency (USD/CHF)  

## Methodology
1. Define economic regimes (e.g., Growth ↑ / Inflation ↑).  
2. Test hedge performance in each regime.  
3. Overlay macro cycle (FOMC rate hike/cut periods).  
4. Compare hedge effectiveness using Sharpe ratio and drawdown.  

## Data
- Provided Excel inputs (Macro, Prices, Yield sheets).  
- Supplemented with public data where needed (USD index, commodities, FX).  

## Results
- Summary of hedge performance by regime.  
- Visualization of returns, drawdowns, and correlations.  

## Extensions
- Incorporate USD/CHF as primary safe haven hedge.  
- Add machine learning classification of regimes.  
- Explore dynamic hedge weights instead of static.  

## Repository Structure
