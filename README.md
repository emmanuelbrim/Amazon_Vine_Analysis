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
Using the Google colab notebook platform , pyspark enabled us to read in the data on shoe reviews from s3 bucket, Amazon Reviews pds.
Below is a snap shot of the code and image to read in the data file.

![](https://github.com/emmanuelbrim/Amazon_Vine_Analysis/blob/main/Resources/read_data.PNG)

The analysis of from the project was based on the following questions;

- How many Vine reviews and non-Vine reviews were there?

