# Amazon_Vine_Analysis

## Overview
The purpose of this analysis is to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, we picked a dataset with customer reviews and performed an ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, we used PySpark to determine if there is any bias toward favorable reviews from Vine members in our dataset.

## Results
* We began 4,880,466 reviews in the database.
* We filtered our data to create a DataFrame to include results with 20 or more total votes. After filtration, we are left 107,421 reviews.
* We further filtered the dataset to create a DataFrame where the percentage of helpful votes is equal to or greater than 50%. This narrowed down our count to 99,046.
* We then split our DataFrame into two, one where the review was part of the vine program and one where it was not.
* The paid vine program DataFrame had 1,207 records.
* The unpaid vine program had 97,839 records.
* We then counted the number of 5-star reviews for both paid and unpaid programs.
* The final step involved calculating the percentage of 5* reviews between the two programs.
* The paid vine program had 509 5* reviews out of 1,207 total paid reviews.
* The unpaid vine program had 45,858 5* reviews out of 97,839 total unpaid reviews.

Our Data analysis revealed that:

* The percentage of 5-star reviews for the paid Vine program was: 42.170671%
* The percentage of 5-star reviews for unpaid Vine program was: 46.870880%

## Summary
Before the analysis was complete, I assumed that the paid vine program would have a higher percentage of 5* reviews but that assumption was incorrect. The unpaid vine program had 46.86% of 5-star reviews in comparison to the paid program that had 42.16%, so there is no bias.

We could do some additional filtering of our data and include verified purchase as our criteria to further clean out the data and see if the comparison between paid and unpaid programs changes.
