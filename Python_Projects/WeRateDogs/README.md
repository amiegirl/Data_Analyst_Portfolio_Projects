# Introduction
The dataset that I will be and analyzing and visualizing is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs.
WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog.

# Gathering Data
twitter_archive_enhanced.csv was provided by Udacity, was downloaded manually, and was read into a dataframe called tw_arc.<br>
image_predictons.tsv is hosted on Udacity's servers downloaded programmatically using the Request library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv. It was read into a dataframe called img_prd.<br>
Additional Data: each tweet's retweet count and favorite ("like") count were gathered from twitter API, stored in a file called tweet_json.txt and read into a dataframe called tweets_count

# Accessing Data
**Quality issues**
* There are some columns with missing values.
* Rating_numerator has some extreme high values that are unrealistic. rating_denominator has values other than 10.
* There are incorrectly entered rating_numerator
* The values in the source column are not human readable.
* Erroneous data types in columns.
* Duplicate image predictions are present for duplicate jpg_url with different tweet ids.
* tweet id with inconsistent column names, id and tweet id.
* name column contains unusual and none names.

**Tidiness issues**
* dog_stage in 4 columns instead of 1; doggo, floofer, pupper, and puppo in twitter archive
* Merge tables tw_arc, img_prd and tweets_count together

# Cleaning Data
* Made a copy of the original data before cleaning
* Remove duplicates and non-nulls from the columns retweeted_status_id, retweeted_status_user_id, and retweeted_status_timestamp, and drop every other unnecessary column.
* Filled the missing values in expanded_url
* Combined ‘doggo', 'floofer', 'pupper', 'puppo' columns into new column dog_stage and dropped the old columns
* Changed the incorrect denominator rating to 10 which is the standard for WeRateDogs and changed the numerator rating accordingly
* Dropped columns with incorrect ratings
* Replaced unusual names (a, an, such, None) with NaN and made the name title case
* Renamed id column in tweets_count_clean to tweet_id
* Merged tables tw_arc and tweets_count together
* Replace values in the source column with readable text
* Dropped duplicated jpg_url values
* Replaced _ with ' ' in image prediction dataframe and changed the values to upper case in p1, p2 and p3
* Merged tw_arc, tweets_count and img_prd into a master dataframe on tweet_id
* Converted tweet_id to string datatype
* Converted dog_stage to category datatype
* Converted timestamp datatype to datetime

# Storing Data
* The gathered and cleaned master dataset was saved to a CSV file named ```twitter_archive_master.csv```.<br>
After the wrangling, the data set contained about 22 columns and 1983 rows.

# Findings
The most popular dog stage is pupper, which is a younger dog, followed by doggo and puppo.
![image](https://github.com/amiegirl/WeRateDogs/assets/81017006/4f80d31e-139f-4762-8848-38b70b49a936)

90% of the tweets are sent via iPhone, followed by web, and a few by tweet deck.
![image](https://github.com/amiegirl/WeRateDogs/assets/81017006/72981b5a-50ac-4f57-8b64-b1de75d39032)

The scatter plot below shows a positive relationship between ```retweet_count``` and ```favorite_count```, the higher the retweet count, the higher the favorite count.

![image](https://github.com/amiegirl/WeRateDogs/assets/81017006/fe78ff7d-1411-4a17-8575-5d46b48c01b0)
