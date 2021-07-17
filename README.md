# Amazon_Vine_Analysis
ETL using PySpark, SQL pgAdmin, and RDS AWS Database
## Are Amazon product reviews more favorable from Vine members?
In this analysis, I used a large dataset of reviews for Amazon's Pet Product to determine if the paid Vine Review program generates more favorable product reviews than non-Vine memebers.

DataSet used: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz
Tools/Sotware: Pyspark 3.0.0, AWS RDS, PGAdmin

### Process:
1. **Extract** data from Amazon Dataset into GoogleCollab using Pyspark
2. **Transform Data** create a new dataframe vine_df to pull out all vine information, filter creating new dataframes for reviews 
3. **Load** data into PGAdmin for easy extraction as csv file 
![Screen Shot 2021-07-17 at 1 44 55 PM](https://user-images.githubusercontent.com/79612565/126049008-2ef52a8a-3a93-4016-a792-5b05c92f26d0.png)
![Screen Shot 2021-07-17 at 11 52 15 AM](https://user-images.githubusercontent.com/79612565/126049019-a006bc9c-951f-452d-a05a-4b1fed0cbb25.png)
![Screen Shot 2021-07-17 at 11 51 52 AM](https://user-images.githubusercontent.com/79612565/126049010-027a134d-960c-47ba-90b6-808f1591128a.png)


## Results:

![Screen Shot 2021-07-17 at 12 43 39 PM](https://user-images.githubusercontent.com/79612565/126048168-8c72c7db-ab6b-43bb-a8b7-1ccf4f1edbce.png)
![Screen Shot 2021-07-17 at 12 43 44 PM](https://user-images.githubusercontent.com/79612565/126048169-f5a2832b-ae11-472f-8343-30c2861fa4a6.png)

## To Wrap it Up
As seen in the printed output statements for results, there is about a 15% difference in 5-star reviews betwen Vine (38%) and non-Vine program(54%) participants with Vine participants 5-star reviews lower than non-Vine memebers. However, there is a far larger amount of non-Vine rewiews than Vine member reviews supporting the idea of no bias based on Vine reveiws in favor of a product. 

### Take it one step further
Further bias can be accumulated through verified purchasers, so an additional analysis removing non-verified purchasers to only show ```filter.df(["verified_purchase"] == "Y")```  and running the full summaries for total_reviews, 5-star_reviews, and percentage of 5 star reviews could provide a more accurate idea of product reviews.

_Note: This dataset is for Pet Products only and does not represent total reveiws across products_
