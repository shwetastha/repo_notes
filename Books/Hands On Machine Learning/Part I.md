# Hands On Machine Learning with Scikit Learn and Tensorflow

## Part I: The Fundamentals of Machine Learning

### **Chapter 1: The Machine Learning Landscape**

* Machine Learning is great for :
	* Problems for which existing solutions require a lot of hand-tuning or long lists of rules: one Machine Learning algorithm can often simplify code and perform better.
	* Complex problems for which there is no good solution at all using a traditional approach: the best Machine Learning techniques can find a solution.
	* Fluctuating environments: a Machine Learning system can adapt to new data.
	* Getting insights about complex problems and large amounts of data.”

#### _Types of Machine Learning Systems_ :

##### **Supervised Learning** :
* classification - eg: Spam emails
* regression - eg: predict target numeric value given a set of _features_
* Logistic Regression: eg, 20% chance of being spam - type of classification
* Algorithms:
	* k-Nearest Neighbors
	* Linear Regression
	* Logistic Regression
	* Support Vector Machines(SVMs)
	* Decision Trees and Random Forests
	* Neural Networks

##### **Unsupervised Learning** :
* training data is unlabelled
* usually clustering is done
* Algorithms:
	* CLustering:
		* k-Means
		* Hierarchical Cluster Analysis(HCA)
		* Expectation Maximization
	* Visualization and Dimensionality Reduction
		* Principal Component Analysis(PCA)
		* Kernel PCA
		* Locally-Linear Embedding(LLE)
		* t-distributed Stochastic Neighbor Embedding(t-SNE)
	* Association rule learning
		* Apriori
		* Eclat
* dimensionality reduction:
	* feature extraction
* anomaly detection

##### **Semisupervised Learning** :
* partially labeled training data, a lot of unlabeled data 
* Google Photos
* deep belied networks are based on unsupervised components called restricted Boltzmann machines(RBMs)
* RBMs are trained sequentially in a unsupervised manner and the whole system is fine-tuned using supervised learning techniques.

##### **Reinforcement Learning** :
* learning system, _agent_, observe the environment, select and perform actions and get rewards or penalties
* learn by itself the best strategy, _policy_, to get the most reward
* robots 

##### **Batch and Online Learning** :
##### **Batch Learning** :
? are we using the batch learning process
* training, evaluating and launching
* train all the data at once

##### **Online Learning** :
* when batch learning is not possible due to limited resource or a lot of resources
* train the data incrementally, indvidually or in mini-batches
* how fast they should adapt to changing data - learning rate
* high learning rate - rapidly adapt to new data but also forget the old data
* low learning rate - learn slowly, less sensitive to noise

##### **Instance-Based Versus Model-Based Learning** :
* how they generalize
* true goal is to perform well on new instances

##### **Instance-Based Learning** :
* measure of similarity
* learns the examples and then generalizes to new cases using similarity measure

##### **Model-based Learning** :
* build a model and then use the model to make predictions
* selecting a model with one or more attribute:
	* linear model:
		* hypothesis(x) = theta-0+theta-1 * x
		* cost fucntion to determine the optimal value of theta-0 and theta-1 - cost function
		* ^^ Linear Regression Algorithm
		* 
