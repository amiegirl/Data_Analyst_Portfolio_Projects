# Introduction
The dataset that I will be and analyzing and visualizing is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs.
WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog.

# Gathering Data
```twitter_archive_enhanced.csv``` was provided by Udacity and was downloaded manually and was read into a dataframe called ```df_arc```

This file ```image_predictons.tsv```  is hosted on Udacity's servers  downloaded programmatically using the Request library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv. It was read into a dataframe called ```img_pred```

Additional Data, each tweet's retweet count and favorite ("like") count was gathered from twitter API and stored in a file ```tweet_json.txt``` and read into a dataframe called ```tweets_count```
# Accessing Data

## Quality issues

### Twitter archive dataframe
1. There are 6 columns with missing values namely; ```in_reply_to_status_id```, ```in_reply_to_user_id```, ```retweeted_status_id```, ```retweeted_status_user_id```, ```retweeted_status_timestamp```, ```expanded_urls```
2. ```rating_numerator``` has some extreme high values which are unrealistic. ```rating_denominator``` has values other than 10
3. There are observations of incorrectly entered ```rating_numerator``` values
4. Values in ```source``` column are not human readable
5. Erroneous data types; columns; ```tweet_id```, ```in_reply_to_status_id```, ```in_reply_to_user_id```, ```retweeted_status_id```, ```retweeted_status_user_id``` should be string. ```dog_stage``` column should be categorical and ```timestamp``` should be in datetime datatype.
6. ```name``` column contain unusual and none names

### Image predictions dataframe
7. Duplicate image predictions present for duplicate ```jpg_url``` with different tweet ids.
8.  Value contains both upper and lower case in p1, p2, and p3 columns, Use of _ instead of space the column values

### Tweets count dataframe
8. ```tweet id``` with inconsistent column names, ```id``` and ```tweet id```
9. The ```retweet_count``` and ```favorite_count``` values are duplicated together in some rows

### Tidiness issues
#### Twitter archive dataframe
1.	Remove unneccessary columns
2.	dog_stage in 4 columns instead of 1; doggo, floofer, pupper, puppo
3.	Merge tables df_arc, img_pred and tweets_count together

# Cleaning Data
1. Made a copy of the original data before cleaning
2. Dropped the unneccesary columns
3. Filled the missing values in ```expanded_url```
4. Combined ‘doggo', 'floofer', 'pupper', 'puppo' columns into new column ```dog_stage``` and dropped the old columns
5. Renamed ```id``` column in ```tweets_count_clean``` to ```tweet_id```
6. Merged table ```df_arc``` and ```tweets_count``` together
7. Changed the observations with incorrect denominator rating to 10 which is the standard for WeRateDogs and change the numerator rating accordingly
8. Dropped columns with incorrect ratings
9. Replaced unusual names, a, an, such, None with NaN and make name title case
10. Replace values in the ```source``` column with readable text
11. Replaced _ with ' '  in ```image prediction dataframe``` and change the values to upper case in p1, p2 and p3
12. Dropped duplicated ```jpg_url``` values
13. Merged ```df_arc```, ```tweets_count``` and ```img_pred``` into a master dataframe on ```tweet_id```
14. Converted ```timestamp``` datatype to datetime
15. Converted ```tweet_id``` datatype to string
16. Converted ```dog_stage``` datatype to category

# Storing Data
Saved gathered, assessed, and cleaned master dataset to a CSV file named ```twitter_archive_master.csv```.<br>
After the wrangling, the data set contained about 22 columns and 1983 rows.

# Findings
The most popular dog stage is pupper, which is a younger dog, followed by doggo and puppo.
![image](https://github.com/amiegirl/WeRateDogs/assets/81017006/4f80d31e-139f-4762-8848-38b70b49a936)

90% of the tweets are sent via iPhone, followed by web, and a few by tweet deck.
![image](https://github.com/amiegirl/WeRateDogs/assets/81017006/72981b5a-50ac-4f57-8b64-b1de75d39032)

The scatter plot below shows a positive relationship between ```retweet_count``` and ```favorite_count```, the higher the retweet count, the higher the favorite count.

![image](https://github.com/amiegirl/WeRateDogs/assets/81017006/fe78ff7d-1411-4a17-8575-5d46b48c01b0)
 
