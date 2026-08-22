# Trading Research

Research and experimentation in algorithmic trading, quantitative strategies, backtesting, and risk management.

> **Status:** Phase 1 — Trading & Market Basics completed

## Purpose

This repository is an educational and experimental research project focused on understanding whether systematic trading strategies can demonstrate a measurable statistical edge after realistic trading costs and risk constraints.

The project starts with no real-money trading. Strategies must be researched, tested, documented, and evaluated before any live deployment is considered.

## Principles

- No real-money trading during the research phases.
- No promise or assumption of profitability.
- Prefer simple, explainable strategies before machine learning.
- Include realistic fees, spread, slippage, and execution assumptions.
- Separate development data from out-of-sample evaluation data.
- Measure both returns and risk.
- Make experiments reproducible.
- Document important assumptions and decisions.
- Never commit API keys, credentials, or other secrets.

## Research Roadmap

- [x] Phase 0 — Foundation and research scope
- [x] Phase 1 — Trading and market basics
- [ ] Phase 2 — NautilusTrader environment
- [ ] Phase 3 — First baseline strategy
- [ ] Phase 4 — Backtesting
- [ ] Phase 5 — Trading costs and execution realism
- [ ] Phase 6 — Risk management
- [ ] Phase 7 — Out-of-sample and robustness testing
- [ ] Phase 8 — Paper trading
- [ ] Phase 9 — Strategy research and improvements
- [ ] Phase 10 — Machine learning experiments
- [ ] Phase 11 — Live trading evaluation

## Phase 1 Scope

Phase 1 established the minimum concepts required to reason about systematic trading research:

- market structure, order books, bid, ask, and spread;
- market and limit orders;
- candlesticks and basic price representation;
- long and short positions;
- position sizing and maximum exposure;
- P&L, fees, win rate, and expectancy;
- risk, loss limits, and drawdown;
- backtesting and chronological simulation;
- train, validation, and test separation;
- overfitting, data leakage, and multiple testing;
- robustness and reproducibility principles.

The phase intentionally does not establish a profitable strategy or imply that future returns are predictable.

## Disclaimer

This project is for research and educational purposes. It is not financial advice and does not guarantee profits. Trading involves the risk of loss.
