# Asset-class strategy notes (v0.9)

Research heuristics refined with VWAP/volume-profile proxies, correlation consistency, RSI divergence proxies, and multi-stat anomaly overlays. Not forecasts.

Regime and volatility from enhanced `regime.py` (multi-scale + tier).

## Major

Hypothesis: liquid majors trend with multi-EMA alignment, positive MACD histogram, price supported by VWAP proxy and Bollinger mid, ADX strength, adaptive RSI, outside stress/high-vol/anomaly.

## Large-cap alt

Hypothesis: volume-confirmed breakouts need multi-momentum, MACD, Bollinger breach, and VWAP support outside stress.

## Stablecoin

Hypothesis: statistical multi-metric peg deviation (absolute, z-score, consecutive bars) is the only useful signal. Alerts only.

## DeFi

Hypothesis: trend only in multi-scale calm regimes with channel, momentum, and low anomaly score.

## Meme

Hypothesis: qualified short-horizon bursts require volume profile consistency, adaptive extension limits, non-extreme RSI/Bollinger, rising structure.

## L2

Hypothesis: relative strength must hold on multiple periods with relative volume and positive correlation consistency versus non-stress benchmark.

## RWA

Hypothesis: slow low-vol multi-scale trend preferred; adaptive gap, stress, or high anomaly halt the idea.

## Perpetual

Hypothesis: negative funding carry only with contained multi-bar drift, funding stability, consistency, non-stress, and low anomaly. Crowded funding is alert-only.

## Still out of scope

- Live order routing, withdrawal, trade keys.
- Broker adapter (separate human-approved system).
- Claims about future returns. Scores describe the synthetic fixture.
