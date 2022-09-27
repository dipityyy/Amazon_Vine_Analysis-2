# Amazon_Vine_Analysis
## Project Overview
Amazon Vine is an invitation-only program which selects the most insightful reviewers to serve as "Vine Voices."  Our client SellBy is wanting analysis of one of many Amazon Reviews datasets to determine if there is any bias towards favorable reviews from Vine members.  For the purposes of this analysis, the "Musical Instruments" review dataset was chosen.

## Methods
The sizeable tsv file was downloaded directly from Amazon datasets.  The file was extracted, then uploaded to Amazon AWS, using an RDS Server, then creating an S3 bucket.  Code was written in Google Colabs notebook using PySpark.  Our local pgAdmin PostgreSQL was connected to both Google Colabs and AWS.  Once the ETL process was completed, the instances were shut down in AWS, and bucket was deleted.  Afterwards, further analysis was performed in Jupyter Notebook.

## Deliverable 1 Results
The Music Instruments Review Dataset was extracted and loaded into Google Colabs using PySpark.  The data was then separated into 4 different tables and cleaned.  Finally, the tables were exported to our local pgAdmin server.

1. **FULL MUSIC INSTRUMENTS DATA TABLE**

2. **CUSTOMER ID REVIEW COUNT**

3. **PRODUCTS TABLE**

4. **REVIEW ID TABLE**

5. **VINE TABLE**

6. **CUSTOMER ID TABLE LOADED TO PGADMIN**

7. **PRODUCTS TABLE LOADED TO PGADMIN**

8. **REVIEW ID TABLE LOADED TO PGADMIN**

9. **VINE TABLE LOADED TO PGADMIN**

## Deliverable 2 Results
Vine Table was exported from pgAdmin as a csv file, then loaded into Jupyter Notebook.  Summary data was compiled for Vine Reviews and Non-Vine Reviews, showing the number of 5 star ratings, number of total ratings, and the percentage of 5 star ratings to the total.  To help normalize the data, only products with at least 20 reviews were filtered in the dataset.

1. **VINE RATINGS SUMMARY**

2. **NON-VINE RATINGS SUMMARY**

## Final Analysis and Summary
As can be seen from the Analysis images from above, the following points can be made:

- There were 60 total Vine reviews and 14,477 total Non-Vine reviews.
- 34 Vine reviews were 5-stars, and 8,212 Non-Vine reviews were 5-stars.
- 56.67% of Vine reviews were 5-stars, and 56.72% of Non-Vine Reviews were 5-stars.

Using just the Musical Instruments Review dataset, there is no evidence of a positivity bias from Vine reviews.  There were significantly more Non-Vine reviews than Vine reviews; less than 0.5% of reviews were Vine reviews.  Even if all Vine reviewers rated 5-stars, it would only have less than 0.5% affect on the total rating.  Also, comparing the percentage of 5-star reviews for both, there is only a difference of 0.05%.

Other datasets could be reviewed in the same way to see if there are variances, but based on the analysis of this dataset, Vine reviews appear to have a minimal effect.  Using this dataset, we could also filter the analysis by verified purchases.  This could further support the results.  We can also similarly analyze for 1-star reviews to see if there happens to be any negative bias.