# Amazon_Vine_Analysis
Exploring Big Data Analysis using Pyspark, Google Colab, Amazon AWS, and PostgresSQL

## Purpose
In this project, we aimed to analyze Amazon reviews written by members of the paid Amazon Vine program in order to potentially undercover biases. Of the 50 available datasets, we will be looking specifically at the one of the books categories in this analysis. Our goal is to first use Pyspark to extract and transform the data. Then, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Finally, to return to Pyspark to do analysis that will help us determine whether there is bias towards favorable reviews.

## Results
In this analysis, we:
- Extracted the dataset from Amazon and created a dataframe
- Filtered that initial data frame to show only the reveiw data
- Further filtered the dataframe to only include results with 20 or more votes and then again to see only results where the percentage of helpful votes is greater than 50%
  - This step helps us to see the more popular products (or products where the reviews may be deemed more influential). It also helps us eliminate products where there are zero reviews/votes - this helps us greatly decrease the chance of calculation errors further into the analysis.
- Finally, we divided the dateframe into two - one to account for Vine reveiws (paid reviews) and the other for the non-Vine reviews.
  - From here, we looked specifically at the number of 5-star reviews in both and what percentage of the total reviews were given 5-star ratings.

The results can be seen in the image below:
![Vine Analysis Summary Table](https://github.com/chichi-ugo/Amazon_Vine_Analysis/blob/main/images/vine_analysis_summary.PNG?raw=true)

1. How many Vine reviews and non-Vine reviews were there?

There were a total of **4,781 Vine reviews** and **332,395 Non-Vine reviews** in this dataset.

2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

There were a total of **1,604 5-star Vine reviews** and **168,800 5-star Non-Vine reviews** in this dataset.

3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

About **33.5%** of the Vine reviews had a 5-star rating.
About **50.8%** of the Non-Vine reviews had a 5-star rating.

## Summary
**Is there evident positivity bias?**
The results of this analysis show that about 33% of the vine ratings were given a 5-star rating. From these results, we conclude that there is insufficient evidence to suggest positivity bias in Vine participants reviews in this product category. In summation, this analysis suggests that there is not a ias for positive reviews from Vine participants.

**Further Analysis**
There are a number of factors left unconsidered in this analysis. Some avenues that could be pursued for further analysis include:
- Expanding to look at all the star reviews and plotting their distribution
  - Looking at the not only the averages, but also the medians and modes can give us more insight.
- Analyzing other product categories for comparison
  - Consumers of books tends to represent a more niche audience, in a sense - there is a chance that consumers feel there is less of a benefit in giving a dishonest review given the subject material.
