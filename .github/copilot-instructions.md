# ApexViper Production - Copilot Instructions

## Project Overview
This is a production TradingView trading system repository using Pine Script. The system implements Smart Money Concepts (SMC) with Health-Market-Structure (HMS) analysis for algorithmic trading on TradingView platform.

## Technology Stack
- **Language:** Pine Script v5 (libraries), Pine Script v6 (indicators/strategies)
- **Platform:** TradingView
- **Primary Instrument:** SPY (S&P 500 ETF)
- **Timeframe:** 15-minute charts
- **Version Control:** Git/GitHub

## Repository Structure

### 00-Core/
Core library files that are published to TradingView and imported by other scripts.
- **HMS_Core_v2.pine** - Main library with HMS state calculation, CVD, BOS/CHoCH detection
- Libraries use Pine Script v5
- Must be published to TradingView before use
- Import format: `import Bam404/LibraryName/VersionNumber as Alias`

### 01-Indicators/
Standalone indicators for testing and analysis.
- **Variants_Tester_v1.pine** - Tests 5 signal variants with color-coded labels
- Indicators use Pine Script v6
- Imports HMS_Core library
- Should use `overlay=true` for on-chart display

### 02-Strategies/
Production trading strategies (currently empty, future development).
- Will import HMS_Core library
- Will use winning variant from testing phase
- Must include proper risk management

### 03-Docs/
Documentation and testing logs.
- **Trading_Encyclopedia.pdf** - Trading rules and methodology (binary file)
- **Testing_Log.md** - Live signal tracking (markdown table)
- **START_HERE.md** - Quick reference guide

### 04-Research/
Experimental code and prototypes.
- Work-in-progress features
- Not production-ready
- Can break without affecting production code

### 99-Archive/
Deprecated code kept for reference only.
- Do not use in active development
- Historical reference only

## Code Standards

### Pine Script Conventions
1. **Version declarations:**
   - Libraries: `//@version=5`
   - Indicators/Strategies: `//@version=6`

2. **Library imports:**
   - Always use version 2 of HMS_Core: `import Bam404/ApexViper_HMS_Core_Complete/2 as HMS`
   - Check version number carefully (not version 1)

3. **Non-repainting code:**
   - All permanent actions must be inside `if barstate.isconfirmed` block
   - Never use future data (no positive indexing like `close[1]` for future)

4. **Function naming:**
   - Prefix exported functions with `f_` (e.g., `f_calculate_hms_state`)
   - User-defined types use PascalCase (e.g., `HMSState`, `POIData`)

5. **Comments:**
   - Use section headers with `//==============================================================================`
   - Document function parameters clearly
   - Explain complex logic inline

### Testing Workflow
1. Test all code in TradingView Pine Editor before committing
2. Verify compilation with no errors
3. Test on SPY 15-minute chart
4. Document results in Testing_Log.md

## HMS Core Library - Key Functions

### f_calculate_hms_state()
**Purpose:** Calculate Health-Market-Structure state with 9 input parameters

**Parameters (IN ORDER):**
1. `bool isValidVolatility` - ATR-based volatility check
2. `bool isValidLiquidity` - Volume threshold check
3. `bool isValidTrend` - Price movement validation
4. `bool isNewsPeriod` - News event flag (usually false)
5. `bool isVoidSaturated` - Void zone saturation (usually false)
6. `bool gammaRisk` - Gamma exposure risk (usually false)
7. `float coherence` - Market coherence score (0.0-1.0)
8. `int regime_enc` - Regime encoding (-1=bear, 0=neutral, 1=bull)
9. `int cycles` - Market cycle count

**Returns:** `HMSState` object with `.health_state`, `.regime`, `.coherence`, `.cycles`

### f_calculate_cvd()
**Purpose:** Calculate Cumulative Volume Delta

**Parameters:** `int lookback` - Number of bars to analyze

**Returns:** `[float cvd, float cvd_bull_div, float cvd_bear_div]`

## Signal Variants Being Tested

Current testing framework evaluates 5 variants:
- **MAIN (Green):** Full confluence - requires all conditions
- **VAR-A (Blue):** Drops CVD requirement
- **VAR-B (Yellow):** Drops health requirement
- **VAR-C (Orange):** Relaxed POI filtering
- **VAR-D (Red):** Simple regime detection

## Common Tasks

### Adding a new indicator:
1. Create file in `01-Indicators/`
2. Use Pine Script v6
3. Import HMS_Core: `import Bam404/ApexViper_HMS_Core_Complete/2 as HMS`
4. Test in TradingView
5. Commit with message: "Add [IndicatorName] indicator"

### Updating HMS_Core library:
1. Edit `00-Core/HMS_Core_v2.pine`
2. Test thoroughly in TradingView
3. Republish to TradingView with incremented version
4. Update all indicators to use new version number
5. Commit with message: "Update HMS_Core to v[X] - [description]"

### Logging test results:
1. Edit `03-Docs/Testing_Log.md`
2. Add row to Signal Log table
3. Update Performance Summary table
4. Commit with message: "Log signal: [VARIANT] [WIN/LOSS] [DATE]"

## Development Workflow

### Phase 5 (COMPLETE): Core Integration
- ✅ HMS_Core library migrated and working
- ✅ Variants testing framework implemented
- ✅ Documentation structure established

### Phase 6 (IN PROGRESS): Live Testing
- 🔄 Testing 5 variants on live market
- 🔄 Logging signals in Testing_Log.md
- 🔄 Tracking win rates and performance
- Target: 1-2 weeks of data

### Phase 7 (FUTURE): Production Strategy
- 📅 Select winning variant
- 📅 Build production strategy
- 📅 Implement risk management
- 📅 Deploy for live trading

## Key Guidelines

1. **Always test in TradingView before committing**
2. **Never break existing working code**
3. **Document all changes clearly**
4. **Use version 2 of HMS_Core library (not version 1)**
5. **Keep Testing_Log.md updated with real signals**
6. **Follow Pine Script non-repainting best practices**

## Troubleshooting

**Import errors:**
- Verify library version is `/2` not `/1`
- Check library is published to TradingView
- Verify username is `Bam404`

**Compilation errors:**
- Check Pine Script version declaration
- Verify all required parameters provided
- Check for parser issues (multi-line expressions)

**No signals appearing:**
- Verify HMS_Core import is correct
- Check if market hours (0930-1600 EST)
- Verify SPY has volume data

---

**Last Updated:** November 17, 2024
