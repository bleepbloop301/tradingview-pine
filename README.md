# TradingView Pine Scripts (Portfolio)

A small portfolio of indicators/strategies I’ve built in **Pine Script v6**.  
Focus: structure, clean signals, and non-repainting logic (state changes on bar close; markers placed with `offset=-1` where applicable).

---

## What’s inside

- [`pine/floor-trader-pivot-zones.pine`](pine/floor-trader-pivot-zones.pine)  
  Finds **clusters of floor-trader pivots/levels** (e.g., PP/S1/R1 overlaps) and turns them into **zones of high mean-reversion probability**.  
  Tunables: zone width/merge tolerance, lookback depth.  
  Visuals: horizontal bands where multiple pivots agree; use as fade/reversion areas or as targets for partials.

- [`pine/volume-trend-detector.pine`](pine/volume-trend-detector.pine)  
  Reads the **trend in volume** to judge whether the **current price trend is likely sustainable** or running out of fuel.  
  Tunables: smoothing length, lookback window, minimum change threshold.  
  Visuals: red and green triangular labels representing bearish and bullish volume trend

- [`pine/support-resistance-zones.pine`](pine/support-resistance-zones.pine)  
  Builds zones from **past swing highs/lows**, then tracks whether price **respects** (bounces) or **disrespects** (breaks) them over time.  
  Tunables: swing sensitivity, zone padding, decay of old levels.  
  Visuals: persistent S/R bands with simple “touched vs broken” behavior you can read at a glance, respected levels have a brighter color.

- [`pine/mean-reversion-detector.pine`](pine/mean-reversion-detector.pine)  
  Checks **highs/lows across multiple timeframes** and flags spots where price **respects a zone** → potential **mean-reversion** setups.  
  Tunables: HTF list/aggregation, buffer distance around zones, confirmation bars.  
  Visuals: highlights across different time periods to represent mean reversion

- [`pine/liquidity-sweep-detector.pine`](pine/liquidity-sweep-detector.pine)  
  Watches **prior highs/lows** and marks **takeouts** (buy-side / sell-side sweeps) often linked to **stop runs/liquidity grabs**.  
  Tunables: lookback for reference highs/lows, wick/close rules.  
  Visuals: current high and low levels and past points of takeout.
