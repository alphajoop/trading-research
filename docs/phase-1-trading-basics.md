# Phase 1 — Trading & Market Basics

## Objective

Build the minimum market knowledge required to reason about systematic trading without assuming that a strategy will be profitable.

The first part of this phase focuses on how prices are represented and how orders interact with a market.

## 1. What is a market?

A market is a place or system where participants can buy and sell an asset. A quoted price is the price available for a transaction under the market's current conditions; it is not necessarily a guaranteed price for every order size.

For this project, we use simple FCFA examples to make the concepts easier to understand.

## 2. Order book

An order book lists available buy and sell orders at different prices.

A simplified example:

```text
SELL ORDERS (Ask)
101 500 FCFA → 2 units
101 000 FCFA → 2 units
100 700 FCFA → 3 units

------------------

BUY ORDERS (Bid)
100 500 FCFA → 2 units
100 000 FCFA → 4 units
 99 500 FCFA → 5 units
```

The quantities shown are the amounts currently available at those price levels. The book can change as participants add, cancel, or execute orders.

## 3. Bid

The **Bid** is the highest price currently offered by buyers in the order book.

In the example above:

```text
Best Bid = 100 500 FCFA
```

A sell order that executes immediately against the best available buyer would interact with this price level, subject to the actual execution conditions and available quantity.

## 4. Ask

The **Ask** is the lowest price currently offered by sellers.

In the example above:

```text
Best Ask = 100 700 FCFA
```

A buy order that executes immediately against the best available seller would interact with this price level, subject to the actual execution conditions and available quantity.

## 5. Spread

The **spread** is the difference between the best Ask and the best Bid.

Using the example above:

```text
Best Ask = 100 700 FCFA
Best Bid = 100 500 FCFA

Spread = 100 700 - 100 500
       = 200 FCFA
```

The spread is one of the transaction costs that matters when evaluating a trading system. It can change over time depending on market conditions and liquidity.

## 6. Important limitations

These examples are intentionally simplified. Real execution can differ because of factors such as:

- order size;
- available liquidity;
- changing order-book levels;
- fees;
- spread;
- slippage.

The purpose of this document is to establish the basic vocabulary and mechanics needed for later research. It does not describe a trading strategy and does not imply that trading can generate a guaranteed return.
