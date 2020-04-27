# Creating Twitter Sentiment Analysis
By towards data science: https://towardsdatascience.com/creating-the-twitter-sentiment-analysis-program-in-python-with-naive-bayes-classification-672e5589a7ed

## Sentiment Analysis
* Opinion Mining
* Natural Language Processing
* Polarity of the Content

## Difference between training and test data
* Article By [Data Driven Investor](https://medium.com/datadriveninvestor/what-are-training-validation-and-test-data-sets-in-machine-learning-d1dd1ab09bae)
* dataset splits
* Why Split DATA?
	* Supervised Machine Learning model: Making a program that is able to generalize to input samples that it has never seen before.
	* exposing to a certain number of variations of input examples -> sufficient accuracy
	* making the model examine data - learn from its mistakes - conclude how well the model performs
	* which data point in the data set plays a role in which of the steps
* _Training Set_  : includes set of input examples that the model will be fit into - or trained on - by adjusting the parameters -> weights in the context of Neural Networks
* _Validation Set_ : 
	* by calculating the loss - error rate - of the model on the validation set we get the accuracy of the models.
	* based on the frequest evaluations on the validation sets, the model will tune the parameters
* _Test Set_ :
	* final evaluation
	* tests the generalizability of the model
	* get the working accuracy of the model


## Process Description
### **_Section A: Preparing The Test Set_** :
* Start with the Test Set then the Training Set.
* Register Twitter application to get our credentials
* Authenticate our Python script with the API using the credentials
* Create function to download tweets based on a search keyword
* **_Step A.1: Getting the authentication credentials_** :
	* [Twitter Developer Site](https://developer.twitter.com/en)
	* Create an App: After a whole long process of register as a twitter developer and creating a profile
	* Generate the Access token.
* **_Step A.2: Authenticating Python Script_** :
	* Using the 'python-twitter' library
	* this provices the api call
* **_Step A.3: Creating function to build Test Set_** :
	* takes a keyword - string - as a search term
	* searches the tweets 
	* and return as twitter.Status objects
	* Caveat : 180 requests per 15 min window

### **_Section B: Preparing the Training Set_** :
* this set will be labelled
* using Niek Sanders’ Corpus of over 5000 hand-classified tweets
* this file has each word labelled with tweet id as well.
* get all the tweet from the processed data file and create your training dataset


### **_Section C: Pre-processing Tweets in The Data Sets_** :
* 


### **_Section D: Naive Bayes Classifier_** :
* **_Step D.1: Building the vocabulary_** :
* **_Step D.2: Matching tweets against our vocabulary_** :
* **_Step D.3: Building our feature vector_** :
* **_Step D.4: Training the classifier_** :


### **_Section E: Testing The Model_** :


## Want to Look into:
* Udemy Course-[ From 0 to 1: Machine Learning, NLP & Python-Cut to the Chase](https://www.udemy.com/course/from-0-1-machine-learning/)


## Questions: 
1. weights in context of the neural networks?
1. how to divide the data into the 3 sets?
1. why tune the parameters? how does this train the model? what difference does this make in the model?
1. in the training set what does it mean by adjusting the parameters?
1. 
