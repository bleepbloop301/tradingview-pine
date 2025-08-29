# TradingView Pine Scripts (Portfolio)

A small portfolio of indicators/strategies I’ve built in **Pine Script v6**.  
Focus: structure, clean signals, and non-repainting logic (state changes on bar close; markers placed with `offset=-1` where applicable).

---

## What’s inside

- [`pine/floor-trader-pivot-zones.pine`](pine/floor-trader-pivot-zones.pine)  
  Floor-Trader style pivot/zone logic with PH/PL marking. Draws **first-of-zone breakout lines** displaced by `priceThreshold` (up from first PH, down from first PL). Includes close-only ON/OFF alerts.

- [`pine/high-turning-points-gated-3highs.pine`](pine/high-turning-points-gated-3highs.pine)  
  Marks **high turning points** (increase → decrease) only when both the rise and fall exceed a **gate (in thousands)**. Every gated high prints a gray triangle; the **3rd consecutive gated high** is recolored **green** (3 higher highs) or **red** (3 lower highs) if the highs occur within a bar-gap window. Alerts included.

- [`pine/volume-trend-detector.pine`](pine/volume-trend-detector.pine)  
  Flags **rising vs falling volume** (optional smoothing), colors bars, and alerts on **volume regime flips**.

- [`pine/support-resistance-zones.pine`](pine/support-resistance-zones.pine)  
  Auto-detects **support/resistance zones**, maintains/update bands with new swings, and can optionally color **retests/breaks**.

- [`pine/liquidity-sweep-detector.pine`](pine/liquidity-sweep-detector.pine)  
  Marks **buy-side / sell-side liquidity sweeps** (prior high/low taken intra-bar then close back inside). Lookback + ATR/wick filters optional. Alerts on sweep events.

- [`pine/mean-reversion-detector.pine`](pine/mean-reversion-detector.pine)  
  Flags **overextensions** vs a rolling mean (z-score / ATR options), marks revert-long/short signals, and alerts on **regime flips**.
