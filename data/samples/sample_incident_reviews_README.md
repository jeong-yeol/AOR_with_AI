# sample_incident_reviews.csv  (constructed illustration)

One fictional restaurant, **Harborview Bistro (constructed illustration, not one of the 200)**
(business_id `INC001`), 30 months of reviews (2021-01 to 2023-06), 376 rows. NOT part of the main
11,010-review corpus. Built for the Chapter 8 anomaly and changepoint section.

The series contains anomalies for you to find: a durable shift in the level of the rating and
sentiment series, and a short suspicious burst of reviews whose text does not match their stars.
Detecting them, and telling the two kinds of event apart, is the exercise.

Columns: `review_id`, `business_id`, `date`, `stars`, `useful`, `text` (same schema as
`maple_city_reviews.csv`). No hidden label column is shipped; you detect the anomalies from the
data itself.
