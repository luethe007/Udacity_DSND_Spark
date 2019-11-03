# Data Scientist Nanodegree
# Data Scientist Capstone Project
## Sparkify: Predict Customer Churn

### Install

This project was realized on IBM Watson Studio. In order to run the Jupyter notebook
`Sparkify.ipynb` the Default Spark Python 3.6 XS (1 Driver, 2 Executors, Spark version 2.3) on the IBM cloud has been used.

In addition to PySpark, the following Python libraries need to be installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org)
- [matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)
- [pixiedust](http://github.com/pixiedust/pixiedust).

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
