# economic-hedge-regimes
Python analysis of economic regimes (growth/inflation) and cross-asset hedging strategies for the S&amp;P 500. Includes gold, US Treasuries, USD index, and safe-haven currencies like USD/CHF, with extensions into yield curve analysis and machine learning overlays.

SPX Regime Hedging — Gold & UST Mix, Markov Overlay, IBKR Extensions

To find the optimal hedge for the S&P 500 using a mix of Gold and U.S. Treasuries, conditioned on economic regimes (growth & inflation trends).
Extras include IBKR live data pulls, sector rotation with defensives, and a Markov (regime‑switching) optimizer for forward‑looking hedge weights. Optional extensions cover the yield curve, cross‑asset hedges (USD, oil, copper), and USD/CHF as a safe‑haven overlay.

What’s inside

Regime Definition: CPI YoY vs 12‑m mean; GDP YoY vs 24‑m mean → Goldilocks / Reflation / Disinflation / Stagflation.

Hedge Engine: Basket 
𝐻
(
𝑤
)
=
𝑤
⋅
Gold
+
(
1
−
𝑤
)
⋅
UST
H(w)=w⋅Gold+(1−w)⋅UST, hedge ratio

𝛾
\*
(
𝑤
)
=
−
C
o
v
(
𝑆
,
𝐻
)
/
V
a
r
(
𝐻
)
γ
\*
(w)=−Cov(S,H)/Var(H).

Risk Objectives: Variance‑min, CVaR(5%)‑min, MaxDD‑min per regime.

Visuals: Variance‑reduction heatmaps, w–γ–variance 3D surfaces, rolling correlations, regime timelines.

Markov Portfolio Optimization: Transition matrix 
𝑃
P, 
𝑃
6
P
6
 (6‑month), expected hedged variance vs 
𝑤
w (1M vs 6M), optimal 
𝑤
,
𝛾
w,γ by horizon.

Sector Rotation (IBKR‑first): 12‑1 momentum + inverse‑vol, defensive blend (XLP/XLU/XLV) in Risk‑Off; optional GLD/IEF overlay.

IBKR Integration: Robust historical pulls (Gateway 4002), delayed data support, pacing, safe merges with your Excel.

Yield Curve (extension): 2s10s & 3m10y slope regimes to steer Gold vs UST; easily added panel.

Cross‑Asset & FX (extension): USD index, oil/copper basket, USD/CHF as safe‑haven overlay.

spx-regime-hedging/
├─ notebooks/
│  ├─ Hedging (7).ipynb           # main end-to-end notebook (presentation-ready)
│  ├─ Hedging (IBKR).ipynb        # IBKR pull + merge (Gateway 4002), optional
│  └─ Extensions - YieldCurve + CrossAsset.ipynb  # optional add-ons
├─ data/
│  ├─ raw/
│  │  └─ Data_310725.xlsx         # provided Excel/CSV (macro, prices, yield)
│  └─ processed/                  # intermediates (auto-created)
├─ src/
│  ├─ hedging/
│  │  ├─ regimes.py               # regime tagging (GDP/CPI rules)
│  │  ├─ hedges.py                # gamma calc, CVaR/MaxDD metrics
│  │  ├─ markov.py                # transition matrix, mixture moments
│  │  ├─ sector_rotation.py       # momentum + defensive blend
│  │  └─ ibkr_io.py               # robust IBKR helpers (optional)
├─ README.md
├─ environment.yml                # conda env (recommended)
└─ requirements.txt               # pip alternative
