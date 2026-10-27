v1.0 · 2026-10-27

# Methodology of Waiting Is the Work

Every change to the method gets a dated entry in [CHANGELOG.md](CHANGELOG.md) and a commit in this repository, so that a past verdict in `verdicts.csv` can be read against the rules in force on the day it was issued. This file is the version-controlled copy of the public page [waitingisthework.com/methodology/](https://waitingisthework.com/methodology/); the page is the source, and this document restates it as of the date above without adding to it. Numeric cut-offs, penalty sizes and simulation parameter distributions are not published, here or on the page. The scoring method itself is numbered separately on the site (currently v3.1, in force since 2026-09-21); "v1.0" in this file is the version of this document.

## 1. The five steps

1. **Filters.** Every listing the daily screen reaches goes through sixteen conditions (section 2). Everything that has ever cleared the screen is the universe.
2. **Twenty-seven criteria.** Survivors are scored against 27 criteria from Graham, Buffett and Lynch (sections 3 to 7). The same pass produces a first-draft intrinsic value, which is the number the deep work is later checked against.
3. **Valuation range.** Several discounted-cash-flow models, an earnings-power estimate and an asset-based check where they apply, then a Monte Carlo simulation (section 9).
4. **Deep evaluation.** Annual and interim filings, segment notes, the cash-flow statement, insider ownership, compensation and prior restatements are read. It ends with a thesis in one sentence and a list of falsifiers: things that, if they happened, would show the thesis was wrong. The falsifiers are written before the verdict, not after.
5. **Read the latest quarterly yourself.** Optional, strongly recommended, and the reader's step rather than the author's.

A decision stands on three legs: the score (what the company is, measured the same way for every company), the intrinsic value (what it might be worth, computed from cash flows and assumptions, independently of the score), and the reader's own judgement of the risks. The first two are produced here; the third is not optional and cannot be supplied from outside.

## 2. The daily screen

Sixteen conditions. The names are published; the numeric cut-off behind each is not.

1. Instrument type: ordinary shares and depositary receipts only; funds, ETFs and closed-end trusts are out.
2. Market capitalisation: above a floor.
3. Price / earnings, trailing: positive, and below a ceiling.
4. Revenue growth, year on year: above a floor.
5. Return on equity: above a floor.
6. Debt to equity: below a ceiling.
7. Net margin: above a floor.
8. Free cash flow: positive.
9. Price / book: positive, and below a ceiling.
10. Average daily volume, 90 days: above a floor.
11. Current ratio: above a floor.
12. PEG on trailing growth: below a ceiling; a missing PEG, which means shrinking earnings, is out.
13. Diluted EPS growth, year on year: below a ceiling, so a one-off jump on a small base does not pass as growth.
14. Exchange: one of the covered markets.
15. Net profit: positive in each of the last five fiscal years (new entries since 2026-09-30).
16. Altman Z-score: above a floor, except for banks and insurers, where the formula does not apply (new entries since 2026-09-30).

Conditions 15 and 16 apply to new entries only; companies already covered were not screened again on them. Three conditions were dropped earlier: five-year beta, a floor on EPS growth (implied by the PEG condition) and a tighter price-to-book. The Altman Z-score also counts as a penalty in the scorecard.

## 3. The formula

```
weighted_sum = sum(Graham) x1 + sum(Buffett) x2 + sum(Lynch) x2 + penalties (negative)
score = max(0, weighted_sum) / denominator x 100
```

Score per criterion: met = 1, partly met = 0.5, not met = 0.

## 4. Frameworks and weights

| Framework | Focus | Weight | Criteria |
|---|---|---|---|
| Graham | Safety and value | x1 | 9 |
| Buffett | Quality and durability of the business | x2 | 9 |
| Lynch | Growth at a reasonable price, understandability | x2 | 9 |

## 5. The 27 criteria

Each criterion is described in words; the numeric cut-off behind it is not published.

**Graham (weight x1)**

| # | Criterion | What it looks for |
|---|---|---|
| 1 | Current earnings multiple, against its own sector | priced in the cheapest tier of its own sector |
| 2 | Price to book, or cash generation for intangible-heavy sectors | book multiple low by the standards of its sector; for technology, semiconductors, pharma and e-commerce a high free-cash-flow yield replaces it, because book value means little there |
| 3 | Earnings multiple times book multiple | the combined earnings-and-book multiple below a Graham-style ceiling |
| 4 | Dividend actually paid | a dividend paid without interruption over the last five years |
| 5 | Dividend yield | a dividend yield well above what the average listed company pays |
| 6 | Leverage | debt below equity, or a net cash position; for banks and insurers judged on regulatory capital instead |
| 7 | Return on invested capital against the cost of that capital | returns on invested capital clearly above what the capital costs; not computable for financials |
| 8 | Earnings growth over five years | earnings per share higher than they were five years ago |
| 9 | Consistency of profit | profitable in every one of the last five years |

**Buffett (weight x2)**

| # | Criterion | What it looks for |
|---|---|---|
| 10 | A durable moat | a competitive advantage that is clear and defensible: brand, network, switching cost, licence or cost position |
| 11 | How long the moat lasts | an advantage that should still be standing a decade from now |
| 12 | Return on equity, sustained | a high return on equity held for years without leaning on debt, measured after one-off gains are normalised away |
| 13 | Margins against the sector | net or operating margins above the sector average, by a clear gap |
| 14 | Quality of management | a management team with a long track record of allocating capital well |
| 15 | Predictability | a business simple enough that next year can be reasoned about |
| 16 | Retained earnings put to work | every unit of profit kept in the business creates more than a unit of value |
| 17 | Pricing power | able to pass inflation on to customers without losing them |
| 18 | Margin of safety against the valuation models | price meaningfully below where the triangulated models put intrinsic value; for banks the dividend discount model is used, never analyst consensus |

**Lynch (weight x2)**

| # | Criterion | What it looks for |
|---|---|---|
| 19 | Growth against the multiple paid for it | the multiple paid is small relative to the growth rate bought |
| 20 | Rate of profit growth | earnings per share compounding fast over the last three years, after one-off and cyclical gains are normalised away |
| 21 | Fits a Lynch category | clearly a fast grower, a stalwart or an asset play, not an ambiguous cyclical or a risky turnaround |
| 22 | A story that can be told simply | the investment case can be explained in a couple of minutes, without jargon |
| 23 | Insider ownership | founders or insiders hold a large stake and have been buying, not selling |
| 24 | Market share | taking share from competitors rather than merely defending it |
| 25 | Analyst coverage | followed by few institutional analysts, if any |
| 26 | Dilution from share-based pay | share-based compensation consumes only a marginal slice of revenue each year |
| 27 | Room left to grow | the market it sells into is still largely unpenetrated, and the expansion already done is repeatable rather than one-off |

## 6. Maximum points by instrument type

| Instrument | Max points | Note |
|---|---|---|
| Standard equity | 45 | 9 Graham x1 + 9 Buffett x2 + 9 Lynch x2 |
| Financials (banks, insurers) | 44 | ROIC has no meaning for a bank, so criterion 7 is removed from the numerator and from the maximum |
| Closed-end fund | 29 | Nine criteria have no operating counterpart in a fund; they are forced to 0 and removed from the maximum together, so dropping them cannot inflate the percentage |
| Passive index ETF | 12 | Only about eight criteria apply at all |

On evaluations recomputed backwards onto method v3.1, the maximum is two lower than shown, because criterion 27 has no mechanical source on historical data and is marked not applicable there.

## 7. Penalties

- **Red flags.** Accounting red flags found in the filings subtract from the weighted sum before the division. The number of points is not published.
- **Valuation.** A price far above every model in the triangulation subtracts as well.
- **Floor.** The weighted sum is floored at zero, so penalties cannot produce a negative score.
- **Evidence.** A second, shadow axis scores how well each claim is backed by a primary document. It is tracked but, in the current method version, does not enter the published score.

Structural rules: a company with negative earnings is flagged "outside the framework" (several Graham criteria cannot be computed, so a low score there is arithmetic, not opinion). For intangible-heavy sectors (technology, semiconductors, pharma, e-commerce) criterion 2 uses free-cash-flow yield instead of price to book; the denominator stays 45.

## 8. Verdict bands

The published score is a 10-point band, never the exact percentage. A verdict describes the status of a candidate in the author's research queue at a stated date, on stated criteria; it is not an instruction to any reader.

| Verdict | Range |
|---|---|
| Strong buy candidate | 82-100 |
| Buy candidate | 72-82 |
| Interesting | 62-72 |
| Monitor | 48-62 |
| Speculative | 32-48 |
| Avoid | 0-32 |

"Not scored" means exactly that.

## 9. Valuation models

The valuation takes five analyst inputs per company: owner earnings (OE), growth in years 1 to 5 (g1), the discount rate (r), terminal growth (gT) and net debt (ND), plus the share count and an FX rate from the filings.

**Mechanical first draft of the inputs.** OE: operating cash flow minus maintenance capex, as a three-year average margin applied to the last twelve months' revenue, capped at 60%; maintenance capex is the smaller of capex and depreciation, and in a heavy investment cycle (capex above 1.5x depreciation in two of the last three years) it becomes depreciation plus half the excess. g1: three-year revenue growth, held between -5% and +12%; years 6 to 10 grow at half of g1. r: ten-year government bond yield plus beta x 5 points, held between 8% and 18%. gT: 2.5% for dollars, euros and pounds, 1.5% for yen, 3.5% for lei. ND: total debt minus cash and short-term investments. The analyst can overrule every mechanical input, and the ticker page shows what was chosen and why.

**Two-stage DCF.** Ten explicit years: growth g1 for years 1 to 5, half of it for years 6 to 10, then a perpetuity growing at gT. Cash arrives at the end of each year and is discounted from there. There is no gradual fade and no exit multiple. If r is not above gT, no value is published. A warning is printed when the terminal value exceeds 60% of enterprise value.

**Range.** The same model runs three times: bear (owner earnings -15%, g1 -3 points, r +1 point), base, and bull (the reverse). Two independent checks run beside it: earnings power value, OE / r less net debt, which assumes no growth, and the Graham number, sqrt(22.5 x EPS x book value per share). The five margins of safety are not averaged; the range is their lowest, median and highest. Banks and insurers use book value x ROE / r in place of owner earnings.

**Monte Carlo.** The same formula runs 20,000 times with inputs drawn around the analyst's values: OE lognormal, +/-25%; g1 normal, spread half its own size and at least 3 points, kept between -10% and +20%; r normal, +/-1 point, never below 8% and never more than 3 points under the analyst's rate; gT normal, +/-0.5 points and always at least 3 points below that run's r. Price, share count and FX are fixed. The seed is fixed, so the same inputs always give the same report. Each run becomes a margin of safety against the price on the day of the analysis; P10, P50 and P90 are read from the sorted 20,000. They are not a floor or a guarantee. If fewer than half the runs produce a valid value, the simulation is not published.

**Margin of safety.** Measured from the price: a value of 150 against a price of 100 is +50%. A negative margin means the price is above the estimate. Where one figure must stand for the range, it is the lower of the median of the five-model range and the Monte Carlo P50; a divergence of 25 points or more, or a disagreement on sign, is flagged rather than resolved.

**IRR.** Combines yield, growth and the closing of the gap between price and value over a horizon N that depends on the market (fast / slow, in years): US large 1 / 3; US small and mid 2 / 5; Canada, UK, Europe 3 / 7; Japan 3 / 7; Hong Kong and China large 4 / 8; Korea 5 / 12; Hong Kong and China small 8 / 20; other markets 5 / 12. The figure used is the lower of the two P25 results. The published IRR blends the case where the discount closes with the case where it stays and the return is only the floor of dividend, buyback and growth. The chance that it stays is higher in markets that have been cheap for years; a documented catalyst (an executed buyback, a raised dividend, a value-up plan, an activist, a takeover offer) lowers it.

## 10. Falsifiers

A deep report ends with a thesis in one sentence and a list of things that, if they happened, would show the thesis wrong. They are written before the verdict, not after.

## 11. Embargo rule

Every analysis is published in full, for everyone, 30 days after it is written: the exact score behind the band, the framework subtotals, the per-criterion scores and their evidence, the intrinsic-value estimate, the margin of safety, the valuation range and its assumptions, the simulated probabilities and percentiles, the deep report, the thesis and the verdict change it records. Newsletter subscribers get the same material the day it is written. Until the 30 days are up, an excerpt shows an ellipsis where a figure from that analysis would be. The current market price and market cap are shown for every company. One demo company has its current analysis open to everyone.

## 12. Record of past changes carried over from the page

- Method v3.1, 2026-09-21: four criteria that duplicated others were retired and the three blocks levelled at nine criteria each; Lynch weight set to two. The historical series was not rewritten: recomputed scores were appended as new rows and the originals remain.
- 2026-10-21: the IRR no longer assumes the gap between price and value always closes within the horizon; a market-dependent chance that the discount stays is blended in. The estimate of value did not change, only the return expected from it.

Source: https://waitingisthework.com/methodology/ (English), as of 2026-10-27.
