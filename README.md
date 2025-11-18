# ApexViper-Production

Production ApexViper Trading System for TradingView Pine Script

## Overview

This is the production repository for the ApexViper trading system, featuring HMS Core v2 + Variants Testing. This system is designed for TradingView and uses Pine Script for algorithmic trading strategies.

## Folder Structure

The repository is organized into a clean, numbered folder structure for easy navigation and maintenance:

### 00-Core/
Library files and core components that are shared across the trading system. This includes reusable Pine Script libraries, utility functions, and fundamental building blocks.

### 01-Indicators/
Testing tools and standalone indicators used for analysis and development. These are individual indicators that can be used to test trading concepts and market analysis.

### 02-Strategies/
Complete trading strategies ready for deployment. These are fully developed Pine Script strategies that combine indicators and logic for automated trading.

### 03-Docs/
Documentation for the trading system, including:
- Setup guides
- Strategy explanations
- API documentation
- Usage instructions
- Trading methodology

### 04-Research/
Experimental code and research projects. This folder contains work-in-progress strategies, new ideas being tested, and exploratory analysis that hasn't been promoted to production yet.

### 99-Archive/
Old code and deprecated versions. Historical strategies and indicators that are no longer in active use but kept for reference.

## Getting Started

1. Browse the folder structure to find the component you need
2. Core libraries should be imported into strategies and indicators as needed
3. Test new concepts in the 04-Research folder before moving to production
4. Document your work in the 03-Docs folder

## Development Status

Active Development - HMS Core v2 + Variants Testing
Production TradingView Pine Script Trading System

## Overview

ApexViper is a clean production trading system built for TradingView using Pine Script. This repository contains the HMS Core v2 + Variants Testing system (Active Development).

## Folder Structure

The repository is organized into the following directories:

### 📚 00-Core/
Core library files and reusable functions for the ApexViper trading system. Contains shared library functions, core indicators, utility functions, and common calculations used across strategies.

### 📊 01-Indicators/
Testing tools and standalone indicators for development and testing. Includes standalone indicator scripts, testing and visualization tools, diagnostic indicators, and development utilities.

### 🎯 02-Strategies/
Production trading strategies for TradingView. Contains complete trading strategies, strategy variants, production-ready systems, and backtested and validated strategies.

### 📖 03-Docs/
Documentation for the ApexViper trading system. Includes user guides, technical documentation, strategy documentation, setup and configuration guides, and performance reports.

### 🔬 04-Research/
Experimental code and research projects. Contains experimental indicators, prototype strategies, research and development code, work-in-progress projects, and testing new concepts.

### 📦 99-Archive/
Archived and deprecated code. Contains old versions of strategies, deprecated indicators, legacy code, historical reference material, and superseded implementations.

## Getting Started

1. Browse the **00-Core/** directory for reusable library functions
2. Check **02-Strategies/** for production-ready trading strategies
3. Review **03-Docs/** for documentation and guides
4. Explore **01-Indicators/** for testing and development tools

## Current Status

**Working Code (Migrated from legacy repo):**
- ✅ **00-Core/HMS_Core_v2.pine** - Complete HMS library with state calculation, CVD, BOS/CHoCH detection
- ✅ **01-Indicators/Variants_Tester_v1.pine** - Testing framework for 5 signal variants (MAIN + VAR-A through VAR-D)
- ✅ **03-Docs/APEXVIPER_TRADING_ENCYCLOPEDIA.pdf** - Trading methodology and rules documentation

**Signal Variants Being Tested:**
- **MAIN (Green):** Full confluence - Health + Coherence + Regime + CHoCH + CVD
- **VAR-A (Blue):** Drop CVD requirement
- **VAR-B (Yellow):** Drop Health requirement  
- **VAR-C (Orange):** Relaxed POI filtering
- **VAR-D (Red):** Simple regime detection with trend filter

**Next Steps:**
- Test variants on live market (SPY 15m chart)
- Track win rates for each variant
- Select best-performing variant for production strategy

**Development Timeline:**
- Phase 5 Complete: HMS Core + Variants Testing framework integrated
- Phase 6 Next: Live testing and variant selection (1-2 weeks)
- Phase 7 Future: Build production strategy from winning variant

## License

This is a production trading system. Please ensure you understand the risks involved in automated trading before using any strategies.
