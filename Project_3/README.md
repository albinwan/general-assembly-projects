# Project 3: Natural Language Processing on Reddit


## Problem Statement

Reddit has gained tremondously popularity recently. A recent article on [The Verge](https://www.theverge.com/2020/12/1/21754984/reddit-dau-daily-users-revealed) revealed that Reddit now has 52 million users registered (that's about 9 times of Singapore's population!), and this was recorded before the /rwallstreetbets saga that happened in the summer of 2021. Due to the popularity of Reddit of late, it would be interesting to experiment and design a Machine Learning model that is able to predict and classify posts against two subreddits. This project aims to classify posts between subreddits of r/GainIt and r/LoseIt. r/GainIt is a subreddit where people share on different ways to bulk up weight as well as success stories on how they did it. r/LoseIt is the opposite where people share on weight loss. Whether you're on whose looking for the right 'keywords' to use in your Reddit post, or simply just trying to play around with Machine Learning models to predict classifications, this model should be of interest to you.

The key question is this: **What are the key words one should use in a Reddit post body so that it can distintictly classify itself in either r/LoseIt or r/GainIt?**

Due to the nature of the topics, one can imagine that the contents are likely to be very identical with each other between the two subreddits. Despite this, the model that was designed performed well with an accuracy score of more than 92%. Baseline accuracy score to beat is 50%. This project has showed that utilizing bag-of-words vectorizing techniques like CountVectorizer/TfidfVectorizer along with Logistical Regression as well as Naive Bayes Classifier was effective despite the similarities between the two subreddits.

## Executive Summary

For ease of readability, this project is split into 4 workbooks:

1. Scraping (`01. Scraping.ipynb`)
2. Data Cleaning (`02. Data Cleaning.ipynb`)
3. EDA (`03. EDA.ipynb`)
4. Modelling (`04. Modelling.ipynb`)

### `01. Scraping.ipynb`
This part of the workbook entails the usage of for loops to iterate through .json files directly from Reddit. I managed to scrape about 700 posts per subreddit, giving me a total of about 1,400 posts. As these two subreddits were very text-based, I was able to obtain a good amount of dataset to run my model on.

### `02. Data Cleaning.ipynb`
Data cleaning involves taking the raw form of the Reddit scrape and putting them through various streams of text cleansing including lemmatizing, removal of special characters and digits as well as stop words removal. Lemmatizing was found to be more effective than Porter Stemmer's approach hence the use of it.

### `03. EDA.ipynb`
Here I do some exploratory data analysis to see if there are any interesting observations. You can find plots of top word counts that appeared in either subreddits as well as word clouds to visualize this as well.

### `04. Modelling.ipynb`
This part covers the actual modelling aspects of this project. Modelling include the use of bag-of-words techniques (Count Vectorizer and TF-IDF Vectorizer) to vectorize the words, and using multiple classifier models (Logistic Regression, Multinomial Naive Bayes and Random Forest Classifier) to test and see which is the most effective model.

## Data Dictionary

|Feature|Type|Description|
|---|---|---|---|
|**comments**|*string*|Combination of Reddit post's title and body|

## Data Sources

[r/GainIt](https://www.reddit.com/r/gainit/)

[r/LoseIt](https://www.reddit.com/r/loseit)


## Conclusions & Recommendations

Overall Model 2 performed the best if we compare on accuracy. Model 2 is a combination of TF-IDF Vectorizer alongside Logistic Regression. It was interesting to include additional classifiers like Naives Bayes and Random Forest to test and see how they performed. Though accuracy did not match up with Logistic Regression. Random Forest did not perform very well on all the confusion metrics, and my best guess is due to the sparsity of our dataset which probably made it unproductive for Random Forest on its random feature split.

In the problem statement I stated concerns regarding the similarity on the content of both subreddits. However, given that there were ample data for us to fit our model on, it turned out that our models performed relatively well on unseen data. Though there were similar keywords in both subreddits, there were distinct words within the subreddits which were sufficient to classify the subreddits respectively. Its noteworthy that each models placed different strength on different keywords. There were also keywords which I picked up from my initial EDA section that contributed well to the classifying model ('muscle', 'bulk', 'squat' etc).

## Recommendations

If one wishes to strongly classify his or her Reddit post as part of r/GainIt, the model recommends to use this list of possible words in the body ('bulk', 'muscle', 'squat', 'rep', 'set', 'lift', 'program', 'bench', 'protein')

If one wishes to strongly classify his or her Reddit post as part of r/LoseIt, the model recommends to use this list of possible words in the body ('deficit', 'losing weight', 'feel', 'journey', 'calorie', 'want', 'losing', 'pound', 'weight')

## Additional data points to consider
1. User's geographical data
We can potentially patch in geographical data to test and see if there are regions in the world that are more interested in losing or gaining weight. Are Asians more inclined to weight gain as opposed to weight loss? Could this be a metric marketing companies can use to target their audience?

2. User's gender data
Similar to above, we can also postulate and test to see if a specific gender is more inclined to gain or lose weight