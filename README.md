# AIxTech crypto intel v0.9: paper-only trading information system

Further refined research harness for automated cryptocurrency **information** and paper strategy evaluation.
Builds on [kkzee92/aixtech-crypto-intel-v08](https://github.com/kkzee92/aixtech-crypto-intel-v08), prior enhanced versions, and the original [zeekiankok92/aixtech-crypto-intel](https://github.com/zeekiankok92/aixtech-crypto-intel).

It does not place live orders, does not store exchange secrets, and is not financial advice.

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![version](https://img.shields.io/badge/version-0.9.0-blue)
![mode](https://img.shields.io/badge/execution-paper%20only-orange)
![Licence](https://img.shields.io/badge/licence-MIT-green)

## Enhancements in v0.9

- VWAP-style and volume-profile proxies for confirmation on majors, large-caps, and meme.
- Correlation and multi-period consistency gates for L2 relative strength.
- RSI divergence proxy and MACD histogram momentum for trend classes.
- Expanded statistical anomaly (skewness proxy, volume z-score, consecutive bar checks).
- Broader secret patterns (additional key formats, bearer tokens, connection strings).
- Adaptive risk further reduced on high correlation mismatch or anomaly scores.
- Fixture integrity with multi-hash and versioned attestation.

See [docs/asset-class-strategies.md](docs/asset-class-strategies.md) and [docs/security-architecture.md](docs/security-architecture.md).

## What it does

- Eight asset classes with refined multi-factor research rules.
- Multi-scale regime + volatility + anomaly scoring.
- Signals with EMA, MACD, Bollinger, ADX proxy, VWAP proxy, volume, adaptive RSI, then multi-gate risk.
- Paper-only backtests with class costs; enhanced hash-chained audit.
- Synthetic candles only. No network by default.

| Asset class | Enhanced research rule (v0.9) | Risk cap (base) | Cost |
|---|---|---|---|
| Major | Multi-EMA + MACD hist + Bollinger + ADX + VWAP proxy + adaptive RSI; stand aside stress/high-vol/anomaly | 8% | 8 bps |
| Large-cap alt | Volume + multi-momentum + MACD + Bollinger + VWAP confirmation | 4% | 14 bps |
| Stablecoin | Adaptive peg + multi-stat deviation (z, consecutive) alerts only | 0% | n/a |
| DeFi | Calm multi-scale + channel + momentum + low anomaly | 2% | 22 bps |
| Meme | Qualified burst with volume profile, consistency, RSI, extreme filters | 0.5% | 45 bps |
| L2 | Multi-period RS + relative volume + correlation consistency vs benchmark | 3% | 16 bps |
| RWA | Slow multi-scale low-vol trend, adaptive gap, momentum, anomaly check | 2% | 12 bps |
| Perpetual | Funding carry with adaptive drift, stability, consistency, non-stress, anomaly | 2% | 10 bps |

## Run

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements-dev.txt
python scripts/make_fixtures.py
PYTHONPATH=src python -m crypto_intel scan fixtures/candles_synthetic.json
PYTHONPATH=src python -m crypto_intel brief fixtures/candles_synthetic.json
PYTHONPATH=src python -m crypto_intel posture fixtures/candles_synthetic.json
```

## Controls

Paper-only. No live credentials. Class caps, adaptive confidence, kill switch, drawdown, statistical anomaly + correlation gates, hash-chained audit, expanded redaction, PDPA tripwire, gitleaks. Zero-trust research design.

## Honesty

No live exchange connector. Scores describe synthetic fixtures. Not investment, legal, or compliance advice. Research only.
