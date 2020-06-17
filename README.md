# Twitter Sentiment Analysis NLP Hackathon by AV

# Problem Statement

Sentiment analysis remains one of the key problems that has seen extensive application of natural language processing. This time around, given the tweets from customers about various tech firms who manufacture and sell mobiles, computers, laptops, etc, the task is to identify if the tweets have a negative sentiment towards such companies or products.

# Data Description

For training the models, a labelled tweets dataset is provided. The dataset is provided in the form of a csv file with each line storing a tweet id, its label and the tweet. The test data file contains only tweet ids and the tweet text with each tweet in a new line.

# Approach and Implementation

# Data Preparation

*The raw text data provided contains lots of urls,punctuations,spelling errors,whitespace characters and non alphabetical charcaters.Using regex all those Urls and other special characters are removed.Using NLTK library all those stopwords removed and using TEXTBLOB spelling errors also corrected.
