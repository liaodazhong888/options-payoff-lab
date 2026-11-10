# Options Payoff Lab · 新手秒懂期权

An interactive options payoff teaching page for beginners. Pick a strategy, switch whether you hold the stock, then drag the price slider to see the payoff curve at expiry, the settlement math, and a plain-language explanation.

中文说明见 [README.zh-CN.md](README.zh-CN.md).

![Page preview](docs/preview.png)

## Try it now

Download the repository ZIP, unzip it, and double-click `index.html`. No packages to install, no account, no broker login. The page has no external scripts, fonts, or market-data dependencies, so it works offline.

`index.html` is both the complete page and the entire application source: HTML, CSS, and JavaScript in a single file.

## What you can learn

- Long Call, Short Call, Long Put, Short Put.
- Compare "holding the stock" vs "not holding the stock" — eight combinations in total.
- Drag the expiry price and watch how the stock P&L, the option P&L, and the combined P&L move together.
- Colors distinguish the Call strike, the Put strike, premium paid or received, and the cost including premium.

## Scope of the model

The current version is an **expiry payoff teaching model** with fixed example parameters: spot price 100, Call strike 120, Put strike 80, premium 5 per unit. All amounts are illustrative example units.

The page calculates in **per-share equivalent units**. "1 share of stock + 1 unit of option" means the quantities match each other; it does not mean 1 share in a real account covers one standard 100-share option contract. A standard US stock option contract usually covers 100 shares; adjusted contracts need their own specifications.

The current version does not simulate pre-expiry option market prices, time value, implied volatility, margin, fees, taxes, dividends, or early assignment. The cost shown on the chart also depends on the holding mode and the meaning of the strategy. For worked examples and the chart range, see the [user guide](docs/guide.md).

This is a teaching demo, not live market data or a trading tool.

## Publish with GitHub Pages

Upload the files in this directory to a public repository. In the repository's **Settings → Pages**, publish from the `main` branch, root directory. Once published, anyone can use the page through a web link.

Step-by-step instructions with screenshots are in the [GitHub Pages guide](docs/github-pages.md). No server, database, or build step is needed.

## File structure

```text
options-payoff-lab/
├── index.html                 # The page itself, and all application source
├── README.md                  # This file (English)
├── README.zh-CN.md            # Chinese version of this file
├── LICENSE                    # MIT license
├── CHANGELOG.md               # Version history
├── CONTRIBUTING.md            # How to contribute and report issues
├── .nojekyll                  # Static publishing marker
├── .gitignore
├── .gitattributes
└── docs/
    ├── guide.md               # How to use the page, math, and teaching limits
    ├── guide.zh-CN.md         # Chinese version of the guide
    ├── github-pages.md        # Upload and GitHub Pages publishing steps
    ├── github-pages.zh-CN.md  # Chinese version of the publishing guide
    └── preview.png            # Page screenshot
```

## Contribute and share

Edit `index.html` in a text editor, save, and refresh the browser to see the result. Report problems through Issues, or submit improvements through Pull Requests.

This project uses the [MIT License](LICENSE): you may use, modify, and redistribute it; redistributions must keep the license and copyright notice.
