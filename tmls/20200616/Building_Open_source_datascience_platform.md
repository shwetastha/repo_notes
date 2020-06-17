# Building an Open Source Data Science Platform

Presentation: https://bit.ly/2UNTNdL
Presenter: @joerg_schad [ArangoDB]

- Graph Powered Machine Learning [ArangoML]

## What is Machine Learning?:
- Why is ML taking off?
	- Experimental Phase
		- Identifying problem and collect and analyse data
		- choose ml algortihm and code your model
		- experiment with data and model
		- tune the model hyperparameters
		- itereate tuning and training
	- Production Phase
		- transform data
		- train model
		- serve the model for online/batch prediction
		- monitor the model's performance
		- iterate
- Data Science Engineering Principles: NATO Science Committee
- Challenge: Requirements Engineering
	- Datasets - Quality
	- Target/serving environment
	- model architecture
- Unsupervised Learning
- Supervised Learning
- Rec: Fast.ai, deeplearning.ai
- Deep Learning: The Promise
	- this incorporates feature extraction + classification
	- Step 1: Training
	- Step 2 Inference

## Challenge: Persona(s):
	- Skills:
		- Data Science
		- Distributed systems engineering
	- Equivalent of Devops in Data Science

## Code writing Process:
- Tensorflow Library
- IDE:
	- TensorFlow.org
	- Google Colab
	- Github
	- Notebook
- Binder -> Open Source Software -> hosted on github
- TensorFlow Hub
- Rec: Tensorflow 2 quickstart for beginners
- Rec: nbdime and nbdiff -> Merging and bridging of Jupyter notebooks
- Papermill -> Executable versions of different notebooks
	 - Parameterize, execute and analyze in notebooks

## Challenge: Data Quality:
- 60-80% of time data prep
- Data Cleaning -> Missing/incorrect labels
- Data Prep -> same format + same distribution
- Note: if you are doing any transformation on the training data they also need to be done in the real data

## Tutorials:
- tensorflow -> Load_csv
- Prep Data -> TensorflowX Transform

## Pipelines:
- Kubeflow, TFX, Michelangelo (Uber)
- Biggest Challenge -> Model Serving:
	- seldon.ai
- Tensorflow Serving:
	- Tutorials -> tfx/serving/serving_basic, rest_simple, serving_advanced
	- First Challenge: Versioning -> VersionPolicy
	- Second Challenge: Loader listening to different source system:
		- Many models can be wrapped around as tensorflow servable
	- Simplest version is Flask App that a client 
- Versioning:
	- Rendezvous Architecture -> mapr.com/ebooks/machine-learning-logistics/ch03.html
	- Rendezvous component -> with multiple models
	- Also used when deploying new models
	- ALso used for testing in live data -> not outputing to the client but only to compare results
	- Also as an ensemble -> majority decision

## ML Platforms:
- 

