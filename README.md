# PySpark-MLlib
a small project to demonstrate over the use of pySpark MLlib implemented on Iris data set 
...................................................

We chose to use Iris data set [Source]. It has 6 variables of three different data types, and three classes. The data set is balanced. This helps the model to perform well.  Our labels are of type string. This is why we need to convert them into numerical values. This is done by using StringIndexer. This technique converts all textual values into numerical values. It does so by counting the frequencies of the classes. The highest frequency classes get numerated first. But we will land in a new problem. The problem is that our classes became categorical where they should not be treated like that. The solution is by doing one hot encoding. This is done by OneHotEncoderEstimator. In spark, one hot encoding is not about generating binary values as in scikit-learn. It maps the values of the features in a raw into one vector of three values. After doing one hot encoding, we can drop the textual labels from our data. One important step we need to do in spark for to prepare the feature for training an ml model is so-called vector assembling.  It is like combing a set of data points of a raw into one vector. After that we need to split our data into train and test. So, we can build our models. Decision tree and random forests are the model we chose in this assignment. One important parameter for both models is maxDepth which we decided to go with 4 to avoid the overfitting and let the model generate for new data. After training the model on the training data and predicting the test data. We need to validate the data to see how good the models are. To do so we use MulticlassClassificationEvaluator. Here we care about is just the accuracy which is 93% for both models. 

Source: 
-the data set
https://www.kaggle.com/datasets/saurabh00007/iriscsv

