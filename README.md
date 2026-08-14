# AOR with AI: Companion Data

Datasets for the textbook *Analyzing Online Reviews with AI*. Everything here is **synthetic and
fictional**, created for the book, and free to use, copy, and redistribute for teaching and
learning. No content comes from Yelp or any other platform.

## Layout

```
data/
  maple_city/        The canonical Maple City corpus used across the book
    maple_city_reviews.csv       11,010 reviews, 200 restaurants, 2019-2022
    maple_city_businesses.csv    200 restaurants with cuisine, neighborhood, coordinates
    README.md
    derived/                     Analysis-ready tables, one per method chapter
      features_review.csv        per-review sentiment and aspect features (Ch5, Ch11)
      panel_recomputed.csv       restaurant-month panel (Ch6)
      ch7_panel.csv              panel with the program indicator for DiD (Ch7)
      ch8_monthly.csv            monthly volume and sentiment series (Ch8)
      ch9_business.csv           per-restaurant table with coordinates and features (Ch9)
      ch10_scores.csv            construct scores for SEM (Ch10)
      ch10_scores_lda.csv        LDA-based scores for comparison (Ch10)
      README_ch10.md
  samples/           Small standalone datasets used in specific chapters and exercises
    sample_hotel_reviews.csv           500 hotel reviews (mini-project)
    sample_restaurant_reviews_1000.csv 1,000 restaurant reviews
    sample_business_month_panel.csv    a compact panel example
    sample_churn_reviews.csv           reviews labeled with churn
    sample_incident_reviews.csv        changepoint and review-bombing demo (Ch8)
    sample_spatial_reviews.csv         reviews with coordinates
notebooks/           Seven worked Colab notebooks, one per stage of the book
prompts/             The ready-to-use Gemini prompt library
```

## Using the data

Every file is plain CSV and opens directly in Excel, Google Sheets, pandas, or R. To load the
main corpus in a Colab notebook:

```python
import pandas as pd
BASE = "https://raw.githubusercontent.com/jeong-yeol/AOR_with_AI/main/"
reviews = pd.read_csv(BASE + "data/maple_city/maple_city_reviews.csv")
businesses = pd.read_csv(BASE + "data/maple_city/maple_city_businesses.csv")
```

The raw URL form works from any Colab notebook with no download step. If you
cloned or downloaded the repository instead, drop `BASE` and read the same
paths relative to the repository root.

The `derived/` tables let you start each chapter from a clean, analysis-ready table without
re-deriving features from the raw reviews.

## License

Free to use, copy, modify, and redistribute for teaching, learning, and research.
