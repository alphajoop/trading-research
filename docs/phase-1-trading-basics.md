# Phase 1 — Trading & Market Basics

## Status

**Completed.**

## Objective

Build the minimum market knowledge required to reason about systematic trading research without assuming that a strategy will be profitable.

## Concepts covered

### 1. Market structure

A market is a place or system where participants buy and sell an asset. An order book lists available buy and sell orders at different price levels.

Key terms:

- **Bid:** highest price currently offered by buyers.
- **Ask:** lowest price currently offered by sellers.
- **Spread:** difference between the best Ask and best Bid.

Example:

```text
SELL / ASK
100 700 FCFA → 3 units
101 000 FCFA → 2 units

------------------

BUY / BID
100 500 FCFA → 2 units
100 000 FCFA → 4 units
```

```text
Best Ask = 100 700 FCFA
Best Bid = 100 500 FCFA
Spread   = 200 FCFA
```

The order book changes as participants add, cancel, or execute orders.

### 2. Orders

A **Market Order** prioritizes immediate execution at the best available prices. The final execution price can differ from the first visible price when available liquidity is insufficient for the requested size.

A **Limit Order** specifies the maximum price acceptable for a buy or the minimum price acceptable for a sell. It can remain unfilled if the market does not reach the specified price.

These mechanics make liquidity, spread, and slippage important considerations for later research.

### 3. Price representation

Candlesticks provide a compact representation of price movement over a time interval, commonly using open, high, low, and close values.

The exact time interval matters. Historical observations must be interpreted in chronological order when simulating decisions.

### 4. Long and short

A **long** position benefits from an increase in the asset price, while a **short** position benefits from a decrease, subject to the mechanics and risks of the instrument and venue.

For this project, shorting is treated as a concept to understand, not as an instruction to trade it with real money.

### 5. Position sizing

Position sizing determines how much capital or exposure is assigned to a position.

A simple research constraint can specify:

```text
Maximum risk per trade
Maximum risk per unit
Maximum position size
```

Position size must be considered together with the distance to the defined loss level and the available capital.

### 6. P&L, fees, and expectancy

A trade's gross result is not necessarily its net result. A simplified model is:

```text
Gross P&L
- fees
- spread / execution costs
- slippage where applicable
= Net P&L
```

Expectancy can be expressed as the average expected result per trade under a defined model. For example:

```text
Expectancy = (win probability × average win)
           - (loss probability × average loss)
```

Historical expectancy is a research measurement, not a guarantee of future performance.

### 7. Risk and drawdown

Returns must be evaluated together with risk. Important measures include loss limits, exposure, and maximum drawdown.

A strategy with a high return can still be unsuitable if it requires excessive drawdown or risk.

### 8. Backtesting

A backtest applies fixed, explicit rules to historical data in chronological order to study how those rules would have behaved.

A valid simulation must avoid using information that was unavailable at the time of each historical decision.

Backtesting does not predict the future and does not prove profitability.

### 9. Train, validation, and test

Historical data can be separated chronologically into development and evaluation periods:

```text
TRAIN       → develop the research idea
VALIDATION  → evaluate and refine choices
TEST        → final out-of-sample evaluation
```

The final test must remain independent from the decisions used to develop the strategy. If test results are repeatedly used to modify the strategy, the test is no longer an independent evaluation.

### 10. Overfitting and data leakage

**Overfitting** occurs when a strategy becomes too adapted to the historical data used during development and fails to generalize to unseen data.

**Data leakage** occurs when information that should not have been available at the time of development or decision-making influences the strategy or evaluation.

A key rule for historical simulation is:

> At time T, a decision may use only information available at or before T.

### 11. Multiple testing and robustness

Trying many strategy variants and selecting the best historical result increases the risk of finding a result that looks strong by chance.

Complexity and repeated optimization therefore require caution. A promising result should be evaluated on data that were not used to select the final strategy.

## Research rules established by Phase 1

1. No real-money trading during the research phases.
2. No promise or assumption of profitability.
3. Prefer simple and explainable hypotheses.
4. Do not use future information in historical decisions.
5. Keep final evaluation data independent from development.
6. Include realistic trading costs and execution assumptions where applicable.
7. Measure both performance and risk.
8. Make experiments reproducible.
9. Document assumptions and important decisions.
10. Treat backtest results as research evidence, not as a guarantee of future returns.

## Phase boundary

Phase 1 establishes vocabulary, basic mechanics, risk concepts, and research discipline. It does not define a trading strategy or claim that a profitable strategy has been found.

The next phase will establish the **NautilusTrader research environment** and its technical foundations before any strategy is evaluated.
