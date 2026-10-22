# Chimney Repair Cost Register (US, published prices, October 2026)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23354319.svg)](https://doi.org/10.5281/zenodo.23354319)

Published by **Chimney Repair Guide** (https://chimneyrepairguide.com/). This GitHub repository is a mirror; the canonical, versioned release is on Zenodo.

- **DOI:** [10.5281/zenodo.23354319](https://doi.org/10.5281/zenodo.23354319)
- **Zenodo record:** https://zenodo.org/records/23354319
- **Data page:** https://chimneyrepairguide.com/chimney-repair-cost-data/
- **License:** CC BY 4.0 (see LICENSE)

## How to cite
Chimney Repair Guide. *Chimney Repair Cost Register (US, published prices, October 2026)*. Zenodo. https://doi.org/10.5281/zenodo.23354319

---

---
license: cc-by-4.0
language:
- en
pretty_name: Chimney Repair Cost Register (US, published prices, 2026)
size_categories:
- n<1K
task_categories:
- tabular-classification
- tabular-regression
tags:
- prices
- home-improvement
- chimney
- construction-costs
- united-states
- tabular
configs:
- config_name: default
  data_files: chimney-repair-cost-register.csv
---

# Chimney Repair Cost Register (US, published prices, October 2026)

A dated, source-cited register of **128 published prices** for chimney sweeping, inspection, repair, components and removal in the United States. Every row records what the price covers, the market it applies to, the publisher, a link to the source page, the page's own date and the date we checked it.

Compiled by **Chimney Repair Guide** ([chimneyrepairguide.com](https://chimneyrepairguide.com/chimney-repair-cost-data/)), where the same register drives every price shown on the site.

## At a glance
| | |
|---|---|
| Rows | 128 (127 prices, 1 pricing-method note) |
| Sources | 41 web pages, 23 independent businesses |
| Tiers | 79 primary (businesses' own prices), 49 secondary (cost guides, general ranges) |
| Categories | sweep/cleaning 25, caps 25, inspection 16, masonry & other repairs 15, crowns 13, removal 11, flashing 8, waterproofing 5, access/fees 5, dampers 3, chase covers 2 |
| Retrieved | Oct 11 and Oct 13, 2026 |
| Format | CSV, UTF-8, 17 columns |
| License | CC BY 4.0 (compilation); figures are third-party facts — cite the original source |

## Files
- `chimney-repair-cost-register.csv`: the data
- `DATA-DICTIONARY.md`: every column
- `METHODS.md`: collection, tiers, rules, limitations

## Use it well
- **Compare like with like:** filter on `scope`, `unit` and `geography` before comparing rows.
- **Count businesses, not rows:** use `independent_business`.
- **Don't average across rows** to make a "national average"; sources differ in scope and method. Any average in the file is the source's own stated figure.
- `record_type = method_note` rows are not prices.
- These are **published prices, not quotes or completed-job data**, and not a representative sample.

## Example
```python
import pandas as pd
df = pd.read_csv("chimney-repair-cost-register.csv")
caps = df[(df.id.str.startswith("CAP")) & (df.record_type == "price")]
print(caps[["service_component", "low_usd", "high_usd", "point_or_stated_average_usd", "unit", "geography", "source_publisher"]])
```

## Citation
Chimney Repair Guide (2026). *Chimney Repair Cost Register (US, published prices, October 2026)* [Data set]. Zenodo. https://doi.org/10.5281/zenodo.23354319

Zenodo record: https://zenodo.org/records/23354319 · Live page: https://chimneyrepairguide.com/chimney-repair-cost-data/ · CC BY 4.0.

## License
Our compilation (selection, structure, IDs, scope summaries, classifications and notes) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Price figures are facts published by the businesses and cost guides named in each row; no source prose is reproduced. The license grants no rights in third-party pages or trademarks.

---
**Kaggle description (short):** 128 dated, source-cited US chimney repair, sweep, inspection, component and removal prices from 23 named contractors, retailers and cost guides (Oct 2026). Each row has scope, unit, market, source URL, page date and check date; tiers separate businesses' own prices from cost-guide ranges. Published prices, not quotes; never averaged. CC BY 4.0. Source and methods: chimneyrepairguide.com/chimney-repair-cost-data/
