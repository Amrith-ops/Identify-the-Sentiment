# Twitter Sentiment Analysis NLP Hackathon by AV

# Problem Statement

Sentiment analysis remains one of the key problems that has seen extensive application of natural language processing. This time around, given the tweets from customers about various tech firms who manufacture and sell mobiles, computers, laptops, etc, the task is to identify if the tweets have a negative sentiment towards such companies or products.

# Data Description

For training the models, a labelled tweets dataset is provided. The dataset is provided in the form of a csv file with each line storing a tweet id, its label and the tweet. The test data file contains only tweet ids and the tweet text with each tweet in a new line.

# Approach and Implementation

# Data Preparation

* The raw text data provided contains lots of urls,punctuations,spelling errors,whitespace characters and non alphabetical charcaters.Using regex all those Urls and other special characters are removed.Using NLTK library all those stopwords removed and using TEXTBLOB spelling errors also corrected.
* While doing Data exploration,i used Spacy library for POS(Parts of Speech) tagging and found that those sentences which are hate speech consists of lot of Propernouns in it.So i thought why not use count of Propernouns as a additional feature.While building model i also checked whether the feature i made is in top 200 features or not,as a result i found Propernoun feature as 199 position out of top 200 features.
* As a part of feature extraction strategy,i used Bag of words,TF-IDF,TF-IDF trigram to convert the text into vector representation which machine learning algorithms can understand.

# Models used and Evaluation

* To do hyperparameter tuning instead of Randomized search or Grid search i used simple cross validation approach and plotted graph to understand at which hyperparmeter does model is overfitting or underfitting.
* I used logistic regression and Linear SVM to classify the data,as a result the LinearSVM achieved f1score of 0.87 and Logistic regression achieved 0.88 f1 score.But i also observed these two models are slightly overfitting on data.
* So,i thought why not use topic modeling i.e Singular value decomposition as a feature engineering hack and build a model on top of it and see if can get better results.
* As a result of topic modeling i was able to reduce the overfitting which was there in Linear models but the Val f1score remained same on test data i.e 0.86
* I assumed there could be some nonlinearity in data,so i tried K nearest neighbors approach but it didnt gave me best result when compare to Linear model.
* As a last strategy i used word embeddings from tensorflowhub and built a deep learning model on top of it,i also used Early stopping to make sure that i save the best weights and also stop when the model isnt doing good on Validation loss.

# Further scope of Study

The results may have been better if i use Convolution networks or transfer learning approach or any other word embedding such as Word2vec
