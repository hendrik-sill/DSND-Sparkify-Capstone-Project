# DSND-Sparkify-Capstone-Project

### Introduction and Motivation
I did this Capstone project as part of the requirements of the Udacity Data Scientist Nanodegree.

In this project I used user log data of a fictituous music streaming service Sparkify to predict user churn using the Apache
Spark Python API PySpark. I started off my analyis locally on my desktop computer using a reduced dataset of just 128 MBs.

Besides using Spark, the special sort of data used for this project and the need to deploy the Notebook to an Amazon Web Services
(AWS) Elastic Map Reduce (EMR) cluster proved somewhat challenging as compared to other projects I have dealt with in the past. 

One of the challenges in working with user log data is that while you have a large number of rows for a single user, this ultimately needs to be reduced to a single row for every single user before a machine learning algorithm can be applied.

Dealing with both local and cluster performance issues proved to be another challenge.

### Overview
The project starts off with an analysis of a small subset of the full dataset. At first, all cases of interactions which cannot be attributed to registered users are removed and a brief general overview of the reduced dataset is given. 

Then, churning is defined, a number of different aggregated features (such that for each user only one row will need to be kept) are discussed, created and these features are then compared across the two groups of users, churners and non-churners. In this process, promising features which are subsequently used for the machine learning models are identified.

In the next part the reduced dataset or the full dataset (for the AWS EMR version of the notebook) is reduced to one row per customer with only the previously identified relevant features. These features are then further taken care of by removing outliers for numerical features, scaling numerical features using min-max scaling and applying one-hot encoding to categorical features.

Next, the prepared dataset is split into a traing and a test set. This data is then used to compare several different classification machine learning algorithms: logistic regression, random forest classifier, gradient-boosted tree classifier, support vector machines (linear kernel) classifier, decision tree classifier and naive Bayes classifier. In the case of the reduced dataset, the decision tree classifier does best while in the case of the full dataset, the gradient-boosted tree classifier showed the best performance.

Finally, hyperparameter tuning is performed for the best model, feature importances are briefly discussed and a short conclusion is provided.

### Two Versions of the Notebook
I included two versions of the notebook in this repository: Sparkify.ipynb (a version which uses only the reduced dataset and which you can thus run locally) and Sparkify_AWS_EMR.ipynb (the version I deployed on an AWS EMR cluster).

### Required Packages

As for the local version of the notebook, I used Python 3.6.7 (Anaconda distribution) for this project. If you are using the Anaconda distribution of Python, you will only need to install PySpark 2.4.4.

For the AWS EMR version, I used the emr-x 28.0 version for the software with version 2.4.4 of Spark.

### Blog Post
I wrote a blog post about this project which you can find at https://medium.com/@hendrik_sill/predicting-churn-with-user-log-data-and-spark-udacity-dsnd-capstone-project-e41f0b0a1d0d. This blog post provides a broader overview of the project, provides some more background information on why predicting user churn, big data and Spark matter. It also provides a slightly different perspective on the project.

### Acknowledgements and Credits
This Capstone project builds upon the knowledge I gained overall in the Udacity Data Scientist Nanodegree and also the Spark course offered by Udacity which can be found at https://medium.com/r/?url=https%3A%2F%2Fwww.udacity.com%2Fcourse%2Flearn-spark-at-udacity--ud2002. The Sparkify data was provided by Udacity and its partner Insight Data Science.

### License

This project is licensed under the GNU General Public License Version 3.

