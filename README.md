# Data Scientist Nanodegree
# Data Scientist Capstone Project
## Sparkify: Predict Customer Churn

### Motivation

In this project, I create a machine learning solution which will be able to predict customer churn. This solution will be realized with Apache Spark. Apache Spark is a popular distributed data processing engine which can be deployed in a variety of ways, providing native bindings for Java, Scala, Python and R.

The main motivation for this project lies in the combination of machine learning technologies and insightful business data to exemplify how data science can provide an added value to the business.

### Install

This project was realized on IBM Watson Studio. In order to run the Jupyter notebook
`Sparkify.ipynb` the Default Spark Python 3.6 XS (1 Driver, 2 Executors, Spark version 2.3) on the IBM cloud has been used.

In addition to PySpark, the following Python libraries need to be installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org)
- [matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)
- [pixiedust](http://github.com/pixiedust/pixiedust).

The provided code in `Sparkify.ipynb` is specific to my credentials and will not work for other users. You need to create an IBM Cloud account to use the IBM Watson Studio service (http://cloud.ibm.com/login). On IBM Watson Studio you can create a project and load in this jupyter notebook (select "Default Spark Python 3.6 XS" under runtime). The provided folder mini_sparkify_event_data.zip contains a raw dataset in JSON format which has to be uploaded on IBM Watson Studio. If it is stored as an asset in the project, you can open `Sparkify.ipynb` and insert the dataset `mini_sparkify_event_data (1).json`. IBM Watson Studio automatically generates the required credentials and you can read in the dataset as a PySpark DataFrame and use the notebook.


### Data
The raw data contains user information from a fictitious music streaming
service called `Sparkify`. Everytime the users interact with the platform e.g. logging in, hearing songs, liking a song with a thumbs up, it generates data. Within the repository there is a zip document (`mini_sparkify_event_data.zip`) which contains the raw data in JSON format (about 280 000 user interactions) to show what the data looks like.

The Machine Learning models in the Jupyter notebook `Sparkify.ipynb` were built with a larger file containing approximately 540 000 user interactions.

This dataset contains information about the following aspects:
- artist,
- song,
- song length,
- user name,
- gender,
- location,
- page visited,
- timestamp,
- userId
and some complementary information about the server requests, sessions, etc.

The target is to predict which users will likely cancel their accounts (visited the page "Cancellation Confirmation").

### Results

The goal of this project was to exploit the capabilities of Apache Spark's analytics engine for large-scale data processing to detect customers which are about to stop using Sparkify's music streaming service.

We applied the typical steps of the data science process like gaining understanding about the data, data preparation, modeling and evaluation. The logistic regression model shows the highest performance (F1-Score: 0.66, Recall: 0.84, Precision: 0.54). We are able to recall 84% of the churning customers and can provide them with special offers to keep them from deleting their Sparkify accounts. However, we need to consider a moderate Precision score of 53%. This means that, from all the customers which will receive special offers, 47% of those customers were actually satisfied with the service and would not need any special treatment.

### Improvements

The provided solution returns a model which has an F1-Score of 0.66. Therefore, there is still room for improvement. We could integrate feature selection / feature reduction techniques to both understand more which features are relevant for this classification problem and to reduce the input feature space.

Instead of taking into account all the pages for feature creation, we could also limit this selection only to positive pages and plug them into the algorithm without further feature engineering.

There might also be room for improvements on the modeling part e.g. training other models, tuning other/more parameters, changing the evaluation metric to "AreaUnderROC", etc.

In conclusion, we see that there are plenty of possibilities to enhance this solution. Feel free to use the code here and produce your own solution!
