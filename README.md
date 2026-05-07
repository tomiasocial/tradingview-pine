# Pine Script Indicator Suite

Professional Pine Script v5 indicators for TradingView.  
Target assets: **Wheat, Crude Oil, Soybean, Soybean Meal, VN30F**  
Timeframes: **5m · 15m · 1h**

---

## Indicators

| File | Name | Description |
|------|------|-------------|
| `01_trend_candles.pine` | Trend Candles | Colors all candles solid green/red by Supertrend direction |
| `02_sideway_zone.pine` | Sideway Zone | Draws consolidation boxes and breakout arrows |
| `03_auto_trendlines.pine` | Auto Trendlines | Auto support/resistance lines from swing pivots |
| `00_full_suite.pine` | Full Suite | All three combined with master toggles |

---

## Installation

1. Open **TradingView → Pine Editor** (bottom panel)
2. Click **New** to create a blank script
3. Paste the contents of the desired `.pine` file
4. Click **Add to chart**
5. Configure parameters in the **Settings** panel (gear icon on the indicator)

---

## Parameters Quick Reference

### Trend Candles
| Parameter | Default | Notes |
|-----------|---------|-------|
| ATR Period | 10 | Increase for smoother trend detection |
| ATR Multiplier | 2.0 | Higher = less sensitive, fewer flips |
| Confirmation Bars | 1 | Set to 2–3 to reduce whipsaws |

### Sideway Zone
| Parameter | Default | Notes |
|-----------|---------|-------|
| Zone Lookback | 20 | Look back N bars to detect range |
| Sideway ATR Multiplier | 3.0 | Lower = detects tighter ranges |
| Breakout Confirm Bars | 2 | Bars to hold outside zone to confirm |

### Auto Trendlines
| Parameter | Default | Notes |
|-----------|---------|-------|
| Pivot Left/Right | 10 | Pivot sensitivity — lower = more pivots |
| Max Trendlines | 2 | Show last N resistance and support lines |
| Show S/D Boxes | true | Amber boxes at each pivot candle body |

---

## Recommended Settings by Asset

| Asset | ATR Period | ATR Mult | Zone Lookback |
|-------|-----------|----------|---------------|
| VN30F 15m | 10 | 2.0 | 20 |
| Wheat 1h | 14 | 2.5 | 25 |
| Crude Oil 15m | 10 | 1.8 | 20 |
| Soybean 1h | 14 | 2.0 | 30 |

---

## Alerts Setup

Each indicator includes two or more alert conditions. To set up:
1. Right-click the indicator on chart → **Add alert**
2. Select the condition (e.g., "Trend → UP")
3. Choose notification method

---

## Version

Current: **v1.0.0** — See [CHANGELOG.md](CHANGELOG.md) for history.
