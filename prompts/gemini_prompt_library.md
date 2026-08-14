# Gemini Prompt Library
Companion to *Analyzing Online Reviews with AI*. Each prompt follows the two-layer style: a plain request you type, with a note on what Gemini does.

## Data loading
- **You type:** "Load sample_hotel_reviews.csv into a DataFrame called reviews and show the first 5 rows, the column names, and the row count."
  *Gemini does:* reads the CSV into a pandas DataFrame; calls .head(), .columns, len().

## Cleaning
- **You type:** "Remove duplicate reviews, drop non-English reviews, and drop reviews shorter than 3 words. Show how many remain after each step."
  *Gemini does:* drop_duplicates, language detection, word-count filter.

## Sentiment analysis
- **You type:** "Add a sentiment_score column using VADER and show summary statistics."
  *Gemini does:* applies the VADER SentimentIntensityAnalyzer compound score per row.

## Topic modeling
- **You type:** "Find 5 topics in the review_text column and show the top words for each."
  *Gemini does:* vectorizes text and fits LDA (or BERTopic).

## Aggregation
- **You type:** "Make a business-by-month table with average rating, review count, and average sentiment."
  *Gemini does:* groupby on business and month, computes means/counts.

## Regression
- **You type:** "Run a fixed-effects panel regression of avg_rating on avg_sentiment and review_count."
  *Gemini does:* sets a panel index and fits PanelOLS with entity effects.

## Time series
- **You type:** "Plot average monthly sentiment and decompose it into trend and seasonality."
  *Gemini does:* resamples by month and runs seasonal decomposition.

## Spatial analysis
- **You type:** "Map businesses by latitude/longitude colored by average rating and compute Moran's I."
  *Gemini does:* builds a spatial weights matrix and computes spatial autocorrelation.

## SEM
- **You type:** "Fit a structural equation model where attitude predicts intention, measured by three review-derived indicators."
  *Gemini does:* specifies measurement + structural models and reports fit indices.

## Prediction
- **You type:** "Predict churn from sentiment, rating, and tenure using a random forest; report precision and recall."
  *Gemini does:* train/test split, fits RandomForestClassifier, reports metrics.

## Interpretation
- **You type:** "Explain this coefficient in plain language for a manager, and note whether it implies causation."
  *Gemini does:* translates the technical result into plain and managerial layers.

## Troubleshooting
- **You type:** "I got a KeyError. Show all column names and fix the code."
  *Gemini does:* prints .columns and corrects the referenced name.
