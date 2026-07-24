# Maple City, Chapter 10 scores (review-based SEM)

Analysis-ready construct scores for the Chapter 10 structural equation modeling exercise. The
underlying corpus is the same `maple_city_reviews.csv` in the parent folder; these files add the
per-review construct scores you fit the model on, so you do not have to run the text extraction
yourself.

## Files

### `ch10_scores.csv`
One row per review, with aspect-based sentiment (ABSA) scores for each construct.

| Column | Description |
|---|---|
| `review_id`, `business_id`, `year` | Keys and the review year |
| `stars` | Star rating |
| `vader` | Overall VADER compound sentiment of the review |
| `food`, `service`, `atmos` | Aspect sentiment for food, service, and atmosphere quality |
| `satisfaction` | Satisfaction score from the satisfaction sentences |
| `revisit` | Revisit-intention score from the revisit sentence |

### `ch10_scores_lda.csv`
The same reviews scored with an earlier LDA-based pipeline, kept for comparison with ABSA.

## How the scores were built (ABSA)
For each construct, the pipeline finds the sentences that mention its keywords, scores each
sentence with VADER, and averages them. This is the same aspect-based sentiment approach taught
in Chapter 5. The aspect scores give food, service, and atmosphere as three separable quality
dimensions, plus a satisfaction score and a revisit-intention score, which are the inputs to the
mediation model in Chapter 10.
