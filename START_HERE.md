# Quick Start Guide - Testing Day 1

## Morning Routine (0700-0730 hours)

### Step 1: Load Indicator (5 min)
1. Open TradingView
2. Open SPY chart
3. Change timeframe to 15 minutes
4. Click "Indicators" button
5. Search for your published "ApexViper_HMS_Variants_Complete" 
   - OR paste local code from `01-Indicators/Variants_Tester_v1.pine`
6. Add to chart
7. Verify you see colored labels appearing

### Step 2: Understand the Colors (2 min)
- 🟢 **Green = MAIN** (Full confluence - most strict)
- 🔵 **Blue = VAR-A** (No CVD requirement)
- 🟡 **Yellow = VAR-B** (No health requirement)
- 🟠 **Orange = VAR-C** (Relaxed POI)
- 🔴 **Red = VAR-D** (Simple regime)

**Labels appear above/below candles when signals fire.**

### Step 3: Set Up Logging (3 min)
1. Open GitHub on your phone or keep tab open on computer
2. Navigate to: `ApexViper-Production/03-Docs/Testing_Log.md`
3. Keep this tab open for quick updates
4. Have a notepad ready for quick notes during market hours

---

## During Market Hours (0930-1600 EST)

### When a Signal Appears:
1. **Note it immediately:**
   - Variant color (which one fired?)
   - Entry price (current candle close)
   - Time
   - Direction (LONG or SHORT based on label position)

2. **Track mentally or on paper:**
   - Set a mental stop loss (use recent swing low/high)
   - Set a mental target (1:1 or 1:2 risk/reward)
   - Watch if it hits target or stop

3. **Log when trade completes:**
   - Go to Testing_Log.md in GitHub
   - Click "Edit" (pencil icon)
   - Add row to Signal Log table
   - Format: `| 2024-11-18 | 10:30 | MAIN | LONG | 585.50 | 586.20 | WIN | +0.70 | Notes |`
   - Commit changes

### Example Quick Note Format (on paper):
```
1030 - MAIN LONG @ 585.50 (green label) - watching
1045 - Hit target 586.20 - WIN +0.70
```

---

## End of Day (After 1600 or when you get home)

1. **Update Performance Summary table in Testing_Log.md**
   - Count total signals per variant
   - Count wins/losses
   - Calculate win rate
   - Commit changes

2. **Add brief notes:**
   - Were any variants particularly active?
   - Any false signals?
   - Market conditions (trending? choppy?)

3. **Review tomorrow's schedule:**
   - Repeat process
   - Aim for 5-10 days of data minimum

---

## What Success Looks Like

**After 1-2 weeks you'll have:**
- 20-50+ signals logged
- Clear winner variant (highest win rate + best P&L)
- Confidence to build production strategy around winner

**If a variant shows 70%+ win rate consistently:**
- That's your production variant
- Move to Phase 7: Build actual trading strategy

---

## Troubleshooting

**No labels appearing?**
- Check if HMS_Core library is published to TradingView
- Check import line in Variants_Tester (should be `/2`)
- Check SPY has volume data

**Too many signals?**
- Increase `Min Bars Between Labels` input (default is 3)
- Try 5-10 for cleaner chart

**Too few signals?**
- You're in testing mode - patience
- Some days are slower than others
- 2-5 signals per day is normal

---

**Last Updated:** November 17, 2024
