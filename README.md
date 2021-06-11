# Amazon_Vine_Analysis
## Overview
Utilizing the functionality of Spark with Python, we create/connect AWS/PostgreSQL databases to store and display cleaned/filtered data from Amazon products. The purpose of the analysis is to deternmine the validity of paid reviews vs. unpaid reviews. Using a specific dataset from Amazon luggage products, we clean the data then connect it to the RDS, then conduct further analysis on the information the has been filtered down for our purpose.

## Results
After inspecting the data, removing duplicates, etc. our RDS and data tables are then connected to PostreSQL, to act as a fully functioning, secure database. We then filter our luggage data to have seperate dataframes of paid/unpaid reviews, filtered by number of votes/helpful votes. After filtering through a massive dataset, our summarized conclusion is ultimatley displayed here:
```
# % of 5 Star "Y" Vine reviews:
vine_y_total = filtered_dfY.count()
vine_y_5star = filtered_dfY.filter("star_rating = 5").count()
vine_y_5star / vine_y_total

0.47619047619047616

# % of 5 Star "N" Vine reviews:
vine_n_total = filtered_dfN.count()
vine_n_5star = filtered_dfN.filter("star_rating = 5").count()
vine_n_5star / vine_n_total

0.5153961136023917
```
## Summary
What we can ultimatley conclude from this dataset is that both paid/unpaid Vine reviews appear to have approximatley 50% 5-star reviews for the luggage products. This means that it's fair to say the paid reviews appear to be fair and unbiased in comparison to the unpaid ones. If the paid reviews had a much higher percentage, then some suspicions could be validated and may warrant further analysis. However it's safe to say this example of analysis could very well be automated to other sets of data, to determine validity of product reviews in a much larger scope/variety.
