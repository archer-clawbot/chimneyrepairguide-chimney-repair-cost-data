# Data dictionary: chimney-repair-cost-register.csv

One row per published price (or pricing-method note) taken from a public web page. UTF-8, comma-separated, RFC 4180 quoting, header row. 128 rows, 17 columns (version 2026-10-13).

| Column | Type | Description | Origin |
|---|---|---|---|
| `id` | string, `ABC-00` | Stable row ID. Prefix = category: SWP sweep/cleaning, INS inspection, CAP caps, CHS chase covers, CRN crowns, FLS flashing, WTR waterproofing, MAS masonry/rebuild/other repairs (incl. animal removal), ACC access/trip/permit/labor terms, DMP dampers, RMV chimney removal | compiler |
| `service_component` | string | Service or component priced, as named by (or closely paraphrased from) the source | source, short label |
| `scope` | string | What the price covers, per the source (inclusions, exclusions, conditions) | source, summarised by compiler |
| `low_usd` | number, blank | Low end of a range, or the "from"/"starting at" figure when `unit` says so | source |
| `high_usd` | number, blank | High end of a range | source |
| `point_or_stated_average_usd` | number, blank | A single published price; or, when `low_usd` and `high_usd` are also filled, the source's **own stated average/typical** figure (never computed by us) | source |
| `unit` | string | Currency and unit (e.g. `USD per flue`, `USD installed`, `USD (from)`) | source |
| `geography` | string | Market the price applies to, or `US national (aggregator)` | source |
| `source_publisher` | string | Publisher of the page, with its type in parentheses | source |
| `independent_business` | string | Grouping key: pages from one company, or presumed affiliates/sister companies (e.g. Angi and HomeAdvisor), share a value. Count this, not rows, to count independent sources | compiler |
| `source_url` | URL | Page the figure was taken from | source |
| `source_date` | string | Date the page shows (ISO date, a stated month, or `Not stated…` with any detail) and how it was found (e.g. `(schema)`) | source |
| `retrieved_date` | ISO date | Date the live page was fetched and the figure confirmed | compiler |
| `source_type` | enum | `contractor price list`, `manufacturer/retailer price`, `cost guide (aggregator)`, `contractor-published general/regional cost guide` | compiler classification |
| `source_tier` | enum | `primary` = a business's own published price; `secondary` = aggregator cost guides and general ranges quoted in articles | compiler classification |
| `record_type` | enum | `price`, or `method_note` (a statement about how pricing works; carries no numbers and must not be treated as a price) | compiler |
| `notes` | string | Compiler's confidence and caveat notes (template pages, conflicting figures, oldest sources) | compiler |

Blank numeric cells mean "not published", never zero. Amounts are as published (no inflation adjustment, no currency conversion, no rounding).
