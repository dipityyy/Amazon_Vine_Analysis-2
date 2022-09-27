# Amazon_Vine_Analysis
## Project Overview
Amazon Vine is an invitation-only program which selects the most insightful reviewers to serve as "Vine Voices."  Our client SellBy is wanting analysis of one of many Amazon Reviews datasets to determine if there is any bias towards favorable reviews from Vine members.  For the purposes of this analysis, the "Musical Instruments" review dataset was chosen.

## Methods
The sizeable tsv file was downloaded directly from Amazon datasets.  The file was extracted, then uploaded to Amazon AWS, using an RDS Server, then creating an S3 bucket.  Code was written in Google Colabs notebook using PySpark.  Our local pgAdmin PostgreSQL was connected to both Google Colabs and AWS.  Once the ETL process was completed, the instances were shut down in AWS, and bucket was deleted.  Afterwards, further analysis was performed in Jupyter Notebook.

## Deliverable 1 Results
The Music Instruments Review Dataset was extracted and loaded into Google Colabs using PySpark.  The data was then separated into 4 different tables and cleaned.  Finally, the tables were exported to our local pgAdmin server.

1. **FULL MUSIC INSTRUMENTS DATA TABLE**

![D1_01_DF](https://user-images.githubusercontent.com/106561880/192647928-99f5b369-1146-411e-a77d-cd671515d2f0.png)

2. **CUSTOMER ID REVIEW COUNT**

![D1_02_Customers](https://user-images.githubusercontent.com/106561880/192647956-d88e7881-20ac-4af5-858e-9ee9a5220ba9.png)

3. **PRODUCTS TABLE**

![D1_03_Products](https://user-images.githubusercontent.com/106561880/192647969-9c7e4478-b039-4958-a8d6-297fc3bd6453.png)

4. **REVIEW ID TABLE**

![D1_04_Review](https://user-images.githubusercontent.com/106561880/192647989-92caa9d4-0dda-4b5d-8acf-91faa346fe72.png)

5. **VINE TABLE**

![D1_05_Vine](https://user-images.githubusercontent.com/106561880/192648001-310d07f5-90ab-4158-ac86-44ee833fa0fe.png)

6. **CUSTOMER ID TABLE LOADED TO PGADMIN**

![D1_08_Customers](https://user-images.githubusercontent.com/106561880/192648022-b7b581dd-646d-44cd-8818-9c9b447cdcc3.png)

7. **PRODUCTS TABLE LOADED TO PGADMIN**

![D1_07_Products](https://user-images.githubusercontent.com/106561880/192648039-61f04ab9-f3dc-4b8f-a597-a0749537e473.png)

8. **REVIEW ID TABLE LOADED TO PGADMIN**

![D1_06_Review](https://user-images.githubusercontent.com/106561880/192648093-5de03622-504d-49e2-86c0-660865c076e0.png)

9. **VINE TABLE LOADED TO PGADMIN**

![D1_09_Vine](https://user-images.githubusercontent.com/106561880/192648108-1ac725f8-f801-4e51-82ac-3cf49a1f68d9.png)

## Deliverable 2 Results
Vine Table was exported from pgAdmin as a csv file, then loaded into Jupyter Notebook.  Summary data was compiled for Vine Reviews and Non-Vine Reviews, showing the number of 5 star ratings, number of total ratings, and the percentage of 5 star ratings to the total.  To help normalize the data, only products with at least 20 reviews were filtered in the dataset.

1. **VINE RATINGS SUMMARY**

![D2_01_Vine](https://user-images.githubusercontent.com/106561880/192648128-d7ee4672-4ab3-43b9-b770-122d290ade01.png)

2. **NON-VINE RATINGS SUMMARY**

![D2_02_NonVine](https://user-images.githubusercontent.com/106561880/192648150-83047640-d933-4fd6-be98-f7744211fe0f.png)

## Final Analysis and Summary
As can be seen from the Analysis images from above, the following points can be made:

- There were 60 total Vine reviews and 14,477 total Non-Vine reviews.
- 34 Vine reviews were 5-stars, and 8,212 Non-Vine reviews were 5-stars.
- 56.67% of Vine reviews were 5-stars, and 56.72% of Non-Vine Reviews were 5-stars.

Using just the Musical Instruments Review dataset, there is no evidence of a positivity bias from Vine reviews.  There were significantly more Non-Vine reviews than Vine reviews; less than 0.5% of reviews were Vine reviews.  Even if all Vine reviewers rated 5-stars, it would only have less than 0.5% affect on the total rating.  Also, comparing the percentage of 5-star reviews for both, there is only a difference of 0.05%.

Other datasets could be reviewed in the same way to see if there are variances, but based on the analysis of this dataset, Vine reviews appear to have a minimal effect.  Using this dataset, we could also filter the analysis by verified purchases.  This could further support the results.  We can also similarly analyze for 1-star reviews to see if there happens to be any negative bias.
