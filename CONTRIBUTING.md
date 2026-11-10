# Contributing

Issues reporting display problems or calculation problems are welcome, as are improvements.

## Reporting a problem

In an Issue, state the browser, window size, holding mode, selected strategy, and expiry price, and write down the expected result and the actual result. A screenshot helps locate layout problems.

## Changing the source

There is no build step. Edit `index.html`, save, and reopen or refresh the browser to check.

For changes to the math or interactions, cover both holding modes and all four strategies, and check at least prices 50, 75, 100, 125, and 150, as well as near the 80 and 120 strikes. Confirm that the numbers, curves, settlement explanations, and colors agree with each other.

For layout changes, check a wide screen, a normal laptop window, and a narrow screen, and avoid cut-off explanations, overlapping chart labels, or horizontal overflow. Keep Chinese text legible and do not introduce MS Gothic or its aliases.

For new models such as pre-expiry valuation or margin, state the assumptions and calculation scope clearly, and update the page notes so a model estimate is never presented as a real market quote.

When submitting a Pull Request, explain what it fixes and how you verified it. When adding or changing a feature, update `CHANGELOG.md` at the same time.
