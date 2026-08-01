# ANALYSIS Android App — Source Prototype

Owner: Manish Sharma

## What works
- Upload any chart screenshot
- Select timeframe
- Set extension days (default 2)
- Analyse button
- Draws full-range rectangles and 50% midpoint lines
- Dark UI

## Important
The current overlay is a **working UI prototype**. The three zones are demo coordinates.
The next development step is replacing `runDemoAnalysis()` with a real candle/market-structure engine.

## Open in Android Studio
1. Extract ZIP.
2. Open the `ANALYSIS_App_Source` folder in Android Studio.
3. Let Gradle sync.
4. Run on Android phone/emulator.
5. Build > Build APK(s).

## Rule engine to implement
Bullish OB:
- Prior downtrend
- Last relevant bearish/opposite candle
- Strong bullish displacement
- BOS confirmation
- Full candle High-to-Low range
- Midpoint = (High + Low)/2
- Extend to configured date

Bearish OB: opposite logic.

Breaker:
- OB invalidated by close through the zone
- Same full range retained
- Label and direction changed
- Retest can confirm breaker

Rejection:
- Wick/price rejection plus displacement and structure context.

For reliable analysis, direct OHLC data from TradingView/broker API is preferable to screenshot-only detection.
