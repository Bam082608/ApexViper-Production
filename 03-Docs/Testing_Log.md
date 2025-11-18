# ApexViper Variants Testing Log

## Purpose
Track live signal performance for each variant to determine which performs best.

## Testing Period
**Start Date:** November 18, 2024  
**End Date:** TBD (Target: 1-2 weeks minimum)  
**Instrument:** SPY 15-minute chart  
**Market Hours:** 0930-1600 EST

---

## Signal Log

| Date | Time | Variant | Signal | Entry Price | Exit Price | Outcome | P&L | Notes |
|------|------|---------|--------|-------------|------------|---------|-----|-------|
| 2024-11-18 | 10:30 | MAIN | LONG | 585.50 | 586.20 | WIN | +0.70 | Strong CVD confirmation |
| 2024-11-18 | 11:45 | VAR-A | SHORT | 586.00 | 585.30 | WIN | +0.70 | No CVD required |
| 2024-11-18 | 13:15 | VAR-D | LONG | 584.80 | 584.50 | LOSS | -0.30 | False breakout |

*Note: First 3 rows are examples. Delete them and start logging real signals tomorrow.*

---

## Performance Summary (Updated Daily)

### Win Rate by Variant

| Variant | Total Signals | Wins | Losses | Win Rate | Avg P&L | Notes |
|---------|---------------|------|--------|----------|---------|-------|
| MAIN    | 0 | 0 | 0 | 0% | $0.00 | Full confluence |
| VAR-A   | 0 | 0 | 0 | 0% | $0.00 | Drop CVD |
| VAR-B   | 0 | 0 | 0 | 0% | $0.00 | Drop Health |
| VAR-C   | 0 | 0 | 0 | 0% | $0.00 | Relaxed POI |
| VAR-D   | 0 | 0 | 0 | 0% | $0.00 | Simple regime |

---

## How to Use This Log

### Daily Workflow:
1. Watch SPY 15m chart with Variants_Tester loaded
2. When a signal appears (colored label on chart):
   - Note the variant color
   - Record entry price
   - Take screenshot (optional)
3. Track the trade mentally or on paper
4. When trade completes (hits target or stop):
   - Come back to this file
   - Click "Edit" in GitHub
   - Add a new row to the Signal Log table
   - Update the Performance Summary table
   - Commit with message: "Log signal: [VARIANT] [WIN/LOSS] [DATE]"

### Adding a Row (Copy this template):
```
| YYYY-MM-DD | HH:MM | VARIANT | LONG/SHORT | 000.00 | 000.00 | WIN/LOSS | +/-0.00 | Notes here |
```

### Tips:
- Use the GitHub web editor (click pencil icon on file)
- Just add rows, don't worry about formatting perfection
- Commit after each signal or batch at end of day
- Update Performance Summary weekly

---

## Testing Notes

### Week 1 Observations:
- TBD

### Week 2 Observations:
- TBD

### Conclusions:
- TBD

---

**Last Updated:** November 17, 2024
