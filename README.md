# Amazon_Vine_Analysis

## Overview of the Analysis
Amazon vine program is a service provided by Amazon to vendors on its site, where manufacturers and publishers pay a fee to receive recieve reviews from vine memebers on  their products.  
Vine members are selected customers who help their fellow customers make informed buying decisions by publishing their reviews of the free products that are given them by Amazon. According to Amazon, the review of vine mebers are the independent opinions of the Vine voices without any influence by vendors.(www.amazon.com/vine/about)

The purpose of this project was to evaluate if there exist any bias toward favorable reviews from Vine members in a selected dataset.
The resources used for the project included;
-  Amazon Review datasets :https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Shoes_v1_00.tsv.gz
-  Google collaboratory
-  Pyspark
-  pgAdmin
-  Amazon Web Services(AWS)
## Results
The analysis of the project involved the creation of a database on AWS and connecting it to pgAdmin so the local data could be stored on the cloud. 
Using the Google colab notebook platform , pyspark enabled us to read in and clean the data on shoe reviews from s3 bucket, Amazon Reviews pds.

The cleaning of data involved the droping all NaNs and filtering the original dataframe to include only total_votes greater than or equal to 20 and helpful votes greater or equal to 50% for its total_votes column and its helpful_votes column respectively. 
The resulting Dataframe then served as the base for the analysis.
Below is a snap shot of the code and image to read in the data file.

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/read_data.PNG)

The analysis on the data for the project tackled the following questions;

- How many Vine reviews and non-Vine reviews were there?

The Dataframe produced after cleaning was filtered based on the vine response("vine = Y, or Vine = N").

From this the total number of Vine reviews and non-Vine reviews was generated and grouped into vine_paid_df and vine_unpaid_df.

From the tables the total Vine reviews(paid) was 22 and the non-Vine(unpaid) reviews was 26924.

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/vine_frame.PNG)

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/total_vine.PNG)

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/nonvine_frame.PNG)

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/total_nonVine.PNG)

- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

To answer these questions both tables were filtered based on their star_rating. All reviews that had a 5-star rating were gropued to create a new data set and the count function used to measure the totals.
The result was 13 vine reviews had 5-stars and 14439 non vine reviews had 5-stars.

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/5%20star%20rating.PNG)

- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
From the analysis the percentage of Vine reviews and non-Vine reviews with 5 stars was 0.048 and 53.59 respectively. 

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/Vine%20percentages.PNG)

## Summary 
The results of the analysis show that 59.1 percent of reviews by Vine members belonged to the 5-star category as compared to 53 percent from non vine members.
The number therefore indicates a slightly higher chance of a vendor getting a 5-star review if he belonged to the Vine program.
However the variance between paid and unpaid 5-star reviews in the shoes dataset is not so significant to generalize the entire program and conclude that the is bias in the ratings of Vine clients.  
Samples from other data sets could be drawn and their analysis can give statistical evidence to support or disprove the conclusion drawn from this analysis.
We could deduce if vine members are influenced by the free products in giving 5-stars or are genuine responses. 
