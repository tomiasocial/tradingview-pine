# Usage Guide — Pine Script Indicator Suite

## Per-Asset Configuration

### VN30F (Vietnamese Index Futures)
**Recommended timeframe: 15m, 1h**

```
Trend Candles:
  ATR Period       = 10
  ATR Multiplier   = 2.0
  Confirm Bars     = 1

Sideway Zone:
  Lookback         = 20
  ATR Multiplier   = 3.0
  Buffer %         = 0.3
  Confirm Bars     = 2

Auto Trendlines:
  Pivot Left/Right = 10
  Max Lines        = 2
```

Tips:
- VN30F tends to trend cleanly in the morning session (9:00–11:30 ICT)
- Sideway zones form frequently around lunch (11:30–13:00)
- Use 1h chart for trend candles as context, 15m for entry timing

---

### Crude Oil (CL)
**Recommended timeframe: 15m, 1h**

```
Trend Candles:
  ATR Period       = 10
  ATR Multiplier   = 1.8
  Confirm Bars     = 2

Sideway Zone:
  Lookback         = 20
  ATR Multiplier   = 2.5
  Buffer %         = 0.2
  Confirm Bars     = 2
```

Tips:
- Most active during US session open (20:30–23:30 ICT)
- Use tighter ATR multiplier (1.8) due to higher volatility
- Key news: EIA inventory reports (Wednesday 21:30 ICT) — avoid holding zones

---

### Wheat (ZW) / Soybean (ZS) / Soybean Meal (ZM)
**Recommended timeframe: 1h**

```
Trend Candles:
  ATR Period       = 14
  ATR Multiplier   = 2.5
  Confirm Bars     = 2

Sideway Zone:
  Lookback         = 25
  ATR Multiplier   = 3.5
  Buffer %         = 0.3
  Confirm Bars     = 3
```

Tips:
- Grain markets move in multi-day trends; 1h chart works well
- Sideway zones are wider; increase ATR multiplier to avoid false zones
- USDA reports (monthly) create sharp moves — reduce position size

---

## Multi-Timeframe Strategy

### Framework
1. **1h chart** — Trend direction via Trend Candles
2. **15m chart** — Sideway zones and breakout entry
3. **5m chart** — Precision entry timing

### Workflow
1. Check 1h: Is the candle color green (uptrend) or red (downtrend)?
2. Switch to 15m: Is there an active sideway zone?
3. Wait for breakout arrow in the direction of the 1h trend
4. Enter on breakout confirmation; stop below/above the zone boundary

---

## Alert Setup Checklist

- [ ] Trend Candles: "Trend → UP" and "Trend → DOWN"
- [ ] Sideway Zone: "Breakout UP" and "Breakdown DOWN"
- [ ] Auto Trendlines: "Touch Support" and "Touch Resistance"

For mobile notifications, use TradingView mobile app with alerts enabled.

---

## Troubleshooting

**Candles not colored?**  
Ensure "Trend Candles" indicator is the only one using `barcolor()`. 
If another indicator uses `barcolor()`, they may conflict.

**Too many sideway zones detected?**  
Increase the "Sideway ATR Multiplier" (e.g., from 3.0 to 4.0).

**Trendlines appear lagging?**  
This is expected — pivots require `pivotRight` bars to confirm. 
Reduce Pivot Right Bars (e.g., from 10 to 5) for faster but noisier detection.

**Boxes not appearing?**  
Check that `max_boxes` is not exceeded. The full suite is limited to 20 boxes total.
