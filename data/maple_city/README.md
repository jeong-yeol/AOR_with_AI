# Maple City Reviews: Companion Dataset

**This is a fully synthetic, fictional dataset created for this textbook.** Maple City, its
neighborhoods, restaurants, and reviews do not exist. The data contains no content from Yelp
or any other platform. It is free to use, copy, and redistribute for teaching and learning.

The dataset is engineered so that real analyses produce real, interpretable results, which lets
you practice each method end to end on data whose structure is known to be learnable.

## Files

### `maple_city_reviews.csv` (11,010 rows)
One row per review, spanning 48 months (2019-01 to 2022-12).

| Column | Type | Description |
|---|---|---|
| `review_id` | string | Unique review id (R000001 ...) |
| `business_id` | string | Restaurant id, joins to `maple_city_businesses.csv` |
| `date` | datetime | Review timestamp (2019-01 to 2022-12) |
| `stars` | int 1-5 | Star rating (J-shaped distribution, as in real review data) |
| `useful` | int | Count of "useful" votes the review received |
| `text` | string | Review text mentioning one to three aspects (food, service, wait, cleanliness, price) with positive or negative wording |

### `maple_city_businesses.csv` (200 rows)
One row per restaurant.

| Column | Type | Description |
|---|---|---|
| `business_id` | string | Restaurant id |
| `name` | string | Fictional restaurant name |
| `cuisine` | string | Cuisine type (Italian, Mexican, Cafe, ...) |
| `neighborhood` | string | One of six Maple City neighborhoods |
| `latitude`, `longitude` | float | Synthetic coordinates, clustered by neighborhood |
| `price_tier` | int 1-4 | Price level |

### `derived/`
Analysis-ready tables built from the two files above, one per method chapter, so you can start
from a clean panel or feature matrix without re-deriving it:

| File | Used in | What it is |
|---|---|---|
| `features_review.csv` | Ch5, Ch11 | Per-review sentiment, review length, and per-aspect mention flags and sentiment |
| `panel_recomputed.csv` | Ch6 | Restaurant-month panel of ratings and aspect sentiment |
| `ch7_panel.csv` | Ch7 | Restaurant-month panel with the program indicator (`treated_post`) for difference-in-differences |
| `ch8_monthly.csv` | Ch8 | Monthly citywide review volume and mean sentiment series |
| `ch9_business.csv` | Ch9 | Per-restaurant table with coordinates, aspect sentiment, and competition-density features |
| `ch10_scores.csv`, `ch10_scores_lda.csv` | Ch10 | Analysis-ready construct scores for structural equation modeling (see `README_ch10.md`) |

## Provenance
The dataset was generated programmatically with a fixed random seed, so it is fully reproducible.
No external data sources were used.

## License independence (verified)
This dataset shares no content with the Yelp Open Dataset or any other source:
- The generator reads no external data; it uses only a fixed random seed and built-in templates.
- Checked against the full Yelp Open Dataset (150,346 businesses, 6,990,280 reviews): **0** matching business names, **0** matching coordinates, **0** matching review texts. Only generic English phrases (for example, "the food was delicious") coincide, which is unavoidable and not protectable.
