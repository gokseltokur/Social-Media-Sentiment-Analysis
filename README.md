# Social Media Sentiment Analysis

## Dataset
The dataset contains 1,600,000 tweets extracted using the twitter api. The tweets have been classified from 0 (negative) to 4 (positive). The dataset contains 6 fields which are target as integer, ids as integer, date as date, flag as string, user as string and text as string.These 6 fields are shown below.
* target: The polarity of the tweet (0 - negative, 2 - neutral, 4 - positive)
* ids: The id of the tweet.
* date: The date of the tweet.
* flag: The query. If there is no query, then this value is NO_QUERY.
* user: The user that tweeted.
* text: The text of the tweet

We remove tweets that have a length of 0. After this process, the dataset has a dimension of 1592328×2
Positive and negative samples are equal. The dataset distribution has not any skewness as shown below.
![datadist](imgs/1.png)


## Chart/Figures of Attribute
## Number of Letters
We provide the frequency and the relative frequency of the letters of whole tweets. Finally, we apply a chi-square test to test if the distribution of the letters in tweets is the same with what we see in English texts.
![letterfreq](imgs/2.png)

We got the p-value (p) as 0 which implies that the letter frequency does not follow the same distribution with what we see in English tests, although the Pearson correlation is too high (~96.7%).
|            |      Frequency      |  Expected |
|----------  |:-------------: |------:   |
| frequency  |    1.0         | 0.967421 |
| expected   |    0.967421    |   1.0     |


We counted the number of characters for each tweet and analyzed the data frame according to maximum number of characters, minimum number of characters, mean of the number of characters column and its standard deviation. Our longest tweet is 189 characters long, the shortest tweet is 1 character long and mean of all tweets’ character length 42.78. The standard deviation of all tweet character length is 24.16.

## Number of Characters
We counted the number of words for each tweet and analyzed the data frame according to maximum number of words, minimum number of words, mean of the number of words column and its standard deviation. Our longest tweet is 50 words long, the shortest tweet is 1 word long and the mean of all tweets’ word length is 7.24. The standard deviation of all tweet character length is 4.03.

### Most Common Words in Dataset
![a](imgs/3.png)

## Positive Tweets
### Most Common Words in Positive Tweets
![a](imgs/4.png)
![a](imgs/5.png)

## Negative Tweets
### Most Common Words in Negative Tweets
![a](imgs/6.png)
![a](imgs/7.png)

## GloVe: Global Vectors for Word Representation
We can train the embedding ourselves. However, that approach can take a long time to train. So, we use transfer learning technique, and we use GloVe: Global Vectors for Word Representation.
  The Global Vectors for Word Representation, or GloVe, algorithm is an extension to the word2vec method for efficiently learning word vectors, developed by Pennington, et al. at Stanford. It is an unsupervised learning algorithm for obtaining vector representations for words. Training is performed on aggregated global word-word co-occurrence statistics from a corpus, and the resulting representations showcase interesting linear substructures of the word vector space. 
  We download the GloVe. Then, we initialize an embedding index that has 400000 word vectors, and embedding matrix.
