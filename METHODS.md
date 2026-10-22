# Methods: Chimney Repair Cost Register

## Collection
- **What:** prices that US chimney contractors, trade retailers and consumer cost guides publish on public web pages for chimney sweeping, inspection, repair, components and removal.
- **How:** each source page was fetched live and the figure, unit, scope wording, geography and page date were recorded by hand into a structured register. Raw snapshots were kept by the compiler. No figures came from calls, quote requests, forms, surveys, logins or paywalled content.
- **When:** rows 1–106 were retrieved Oct 11, 2026; the remaining 22 (Batches E and F) on Oct 13, 2026. Each row carries its own `retrieved_date`.
- **Coverage:** 128 rows (127 prices, 1 method note) from 41 source URLs and 23 independent businesses; 79 primary-tier rows and 49 secondary-tier rows.

## Tiers and grouping
- **Primary:** a business publishing its own price (contractor price lists, retailer list prices).
- **Secondary:** aggregator cost guides (Angi, HomeAdvisor, HomeGuide, Fixr) and contractor articles quoting general market ranges.
- Pages from one company, and presumed affiliates (shared templates/addresses, or a shared parent such as Angi Inc.), share an `independent_business` value and must not be treated as independent corroboration.

## Rules applied
1. No averaging, blending or midpoints. Any average in the data is the source's own stated figure.
2. Scope is recorded with every row; rows only compare when scope, unit and geography match.
3. Retail component prices are not job prices.
4. Method notes carry no numbers.
5. Undated sources are marked `Not stated`, never given an inferred date.
6. Prose was not copied from sources: the dataset holds figures, units, short labels/scope summaries and citations.

## Limitations
- **Published prices, not quotes or transactions.** Businesses choose what to publish; final prices are set on site.
- **Not a representative sample.** Coverage is concentrated in a few markets (notably Chicago's North Shore, Lafayette IN, SE Michigan, Atlanta, Dallas-Fort Worth) and a few businesses supply many rows (one contractor supplies ~20 rows).
- **Regional.** Local rows apply to the stated market only; aggregator rows are national ranges with undisclosed methods.
- **Point in time.** Prices change; some sources are undated or more than a year old (oldest: Lindemann Chimney Service Apr 2024, Fixr Jan 2025). Re-check the `source_url` before relying on a figure.
- **Scope wording is a summary.** Read the source page for full terms.
- Not advice on what work a chimney needs.

## Versioning
The canonical copy is generated from the register that drives chimneyrepairguide.com (`npm run data:build`); a test keeps the public CSV in sync with the site. Versions are named by the latest `retrieved_date`.
