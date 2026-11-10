# How to Use the Page and How It Calculates

Chinese version: [guide.zh-CN.md](guide.zh-CN.md).

## How to use the page

First pick a holding mode at the top, then click one of the four strategy cards on the left. Drag the price slider on the right, or click one of the five quick price buttons (50, 75, 100, 125, 150), to see the result at expiry.

Each card shows its parameters at the top and a strategy explanation below. At the bottom left, the stock P&L, the option P&L, and the final net P&L are laid out as an equation. At the top right are the cost, maximum gain, maximum loss, and the current simulated expiry P&L; in the middle is the chart with the slider; below is a plain-language explanation of the current scenario.

The chart follows the slider; the chart itself cannot be dragged.

## What the colors mean

| Color | Meaning |
| --- | --- |
| White | Current price and other basic information |
| Yellow | Call strike 120 |
| Blue | Put strike 80 |
| Red | Premium paid, losses |
| Green | Premium received, gains |
| Purple | Cost including premium, or a breakeven price |

Amounts in the strategy explanations use the matching colors. On the chart, the Put kink is blue, the Call kink is yellow, and the cost marker is purple; P&L numbers are colored by sign.

## Fixed parameters

| Parameter | Value |
| --- | ---: |
| Initial stock cost | 100 |
| Call strike | 120 |
| Put strike | 80 |
| Initial premium, per-share equivalent unit | 5 |
| Expiry prices you can simulate | 40 to 160, step 1 |
| Chart vertical range used for calculation | -95 to 95 |

Curve segments outside the vertical range are clipped at the boundary. The numbers at the top and bottom left can therefore exceed the visible range of the chart; do not judge capped risk from the chart boundary alone. The maximum gain and maximum loss labels describe the strategy over a fuller price range, not just the slider's 40 to 160.

## Expiry payoff of the four options

Let S be the expiry price. All figures are per-share equivalent units, before fees.

| Option | Net P&L at expiry |
| --- | --- |
| Long Call | max(S - 120, 0) - 5 |
| Short Call | 5 - max(S - 120, 0) |
| Long Put | max(80 - S, 0) - 5 |
| Short Put | 5 - max(80 - S, 0) |

In holding mode, add the P&L of the stock you already own: `S - 100`. In no-holding mode, the stock P&L is 0.

Example: holding the stock plus a Long Put, with expiry price 50: stock P&L -50, option P&L +25, combined net P&L -25.

## Matching quantities and the covered call

The page scales one contract down to per-share equivalent units to make it easy to understand. For one standard 100-share stock option contract, multiply the share count, the premium, and the total P&L by 100.

The "at most +25" for holding the stock plus a Short Call assumes the shares you hold fully cover the option you sold, the stock's initial cost is 100, the Call strike is 120, and you received 5 in premium. After a big rally, the shares you already hold can be delivered directly; you do not need to buy them again at the risen market price.

"At most +25" does not mean a guaranteed profit: if the expiry price is 50, the stock loses 50 and the premium income is 5, so the combination still loses 45.

If a real account holds only 1 share but sells one contract covering 100 shares, the other 99 shares are not covered by stock, and this fully-covered strategy card's risk conclusions do not apply. Whether you can open the position at all, and how margin, borrowing, and assignment are handled, depends on your broker's rules.

## Expiry payoff vs closing before expiry

The current page only models payoff at expiry; it does not model the option's market value before expiry. The 5 in the page is the original premium at the time of buying or selling; it does not mean the option is always worth 5 throughout the holding period.

Before expiry, an option's market price includes intrinsic value and time value, and is affected by the stock price, time remaining, implied volatility, and other factors. If you hold a Long Call and sell it to close, your P&L is "what you received from selling minus your original purchase cost"; that is a different way out from exercising to buy the stock, and the two gains must not be counted twice.

Pre-expiry price simulation, independent settings for share count and contract count, and margin and insufficient-funds handling are not part of the current version.

## Simplified wording about exercise

The page explains the typical exercise and settlement economics based on where the expiry price sits relative to the strike. Real American-style options can be assigned early; the price merely touching the strike does not mean the system settles immediately. Broker cutoff times, automatic exercise, account funds, and contract type need to be checked separately.

## Where the source code is

All application source is in `index.html`:

- `<style>`: the theme, layout, and color rules.
- `<body>`: strategy cards, chart, buttons, slider, and settlement areas.
- `<script>`: strategy math, mode switching, colored explanations, the SVG chart, and linked updates.

Key functions include `calcOptionPayoff`, `calcTotalPayoff`, `switchMode`, `selectStrategy`, `setPrice`, `renderColoredDescription`, `getMetaInfo`, `buildStory`, `drawChart`, and `updateAll`.

The page uses "新手秒懂期权 · Options Made Simple for Beginners" as its bilingual title, and the dynamic explanations address the reader as "your options bill".

## Learning resources

- [OIC: Covered Call strategy](https://www.optionseducation.org/strategies/all-strategies/covered-call-buy-write)
- [OIC: Exercise and assignment](https://www.optionseducation.org/referencelibrary/faq/options-assignment)
- [Fidelity: Understanding options pricing](https://www.fidelity.com/learning-center/trading-investing/understanding-options-pricing)
