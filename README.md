# Amazon_Vine_Challenge

## Overview
For this challenge, I analyzed reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

## Resources
* Data: Vine Reviews https://s3.amazonaws.com/amazon-reviews pds/tsv/amazon_reviews_us_Sports_v1_00.tsv.gz
* PySpark 3.2.3
* Amazon Web Service
* postgreSQL and pgAdmin

## Analysis

I picked the Sports dataset and used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then, I used PySpark to determine if there is any bias toward favorable reviews from Vine members in the dataset. 

Using the cloud ETL process, I created an AWS RDS database with tables in pgAdmin. I extracted the dataset into a DataFrame and transformed the DataFrame into four separate DataFrames that match the table schema in pgAdmin. 

![Vine Data Upload](https://github.com/CSoldo1/Amazon_Vine_Challenge/blob/main/images/vine_uploads.PNG)

I then made sure that the transformed data had been uploaded into the appropriate tables by running queries in pgAdmin. 

Then using PySpark tried I determtined if there is any bias towards reviews that were written as part of the Vine program. For this analysis, I determined if having a paid Vine review makes a difference in the percentage of 5-star reviews. 

First, I tallied the total number of paid and unpaid 5-star reviews. 

![Paid Votes](https://github.com/CSoldo1/Amazon_Vine_Challenge/blob/main/images/Paid_votes.PNG)

![Unpaid Votes](https://github.com/CSoldo1/Amazon_Vine_Challenge/blob/main/images/Unpaid_Votes.PNG)

## Results

The total number of unpaid 5-star votes greatly exceeded those from the Vine program. 

![Paid Vote Review](https://github.com/CSoldo1/Amazon_Vine_Challenge/blob/main/images/Paid_review_breakdown.PNG)

![Unpaid Votes Review](https://github.com/CSoldo1/Amazon_Vine_Challenge/blob/main/images/Unpaid_reviews_breakdown.PNG)

## Summary
Based on my analysis, I do not believe there is a positivity bias for reviews in the Vine program. The percentage of 5-star reviews was higher in the unpaid reviews versus the paid reviews. I would need to examine more review datasets to see if this trend continued. I'm unfamiliar with the nuances of the Vine program, but I assume that if a pay scale is introduced, then that would increase the positivity bias. 
