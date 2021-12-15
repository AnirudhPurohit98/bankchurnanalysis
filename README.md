# bankchurnanalysis
# **1.0 Introduction**
Predicting bank customer churn by implementing multiple models and use evaluation metrics to compare model performances.
Several competitors have entered into the bank industry and it is critical to banks to retain customers by improvising the services offered to them. Almost every provider has implicated new technologies from which they are able to offer customers easy way to save earnings or make transactions. Hence, it is very crucial decision to make by the executive officers to make changes in the OPs or extend their services to retain present customers or attract new ones. 

Customers typically search for a variety of characteristics in a bank service provider, including proximity, online services, transaction feasibility, account flexibility, rates, and policies, among others. Banks must keep an eye on their competitors' efforts to persuade clients to utilize their services in order to retain customers. As a result, decisions must be made in order to stay competitive; otherwise, they will soon begin to lose clients.

In order to keep track of customers, banks hire analysts to make reports by analysing customer data. The data will usually consist of details of both current and defaulted customers such as transaction details, services they are currently using, personal details such as details about the family, occupation, income and geographical details such as address etc. Data analysts work on the data by implementing algorithms, making predictions and generate reports which depict customer’s activities that are being carried out with the bank. These insights are important and help decision makers to take effective actions to improve retention rates. 

This project conducts the analysis and predict if a customer will churn or not depending on various factors available in the data.
2.0	Data description

The dataset for this project was downloaded from Kaggle datasets website. Link for the data is provided below:
https://www.kaggle.com/josephchan524/bankchurnersclassifier-recall-97-accuracy-95/notebook 

There are 10128 records of customer in the data with 21 attributes with no null values in any record. Below image shows the cover description of the data.
	
**3.0	Task description**

The task of the project is to predict the churn label for the customer record. In the Attrition column, there are two class labels; ‘0’ indicates that the customer is currently using the service and ‘1’ indicates that customer has already stopped using the bank service. Using the attributes as mentioned above in the data description table, the class labels for output ‘Y’ is predicted. The goal of the project is to train four different classification models by finding out the best fit and compare the performances using several evaluation metrics.

**4.0	Data exploration**

To gain a better understanding of the data, numerous analyses were run on it using Python in Jupyter Notebook IDE. In the example of the 'Customer Age' variable, four bins were constructed and assigned the values to the appropriate class. The remaining category variables are listed below. 

**5.0	Data preparation** 

**1.	Class imbalance problem**

To cope with the problem of class imbalance, Stratified K-Fold approach was employed. The class 'Existing Customer' or label '0' is far more widespread than the class 'Attired Customer' or label '1', as seen in the graph below. As a result, we can ensure that the models are trained for both class labels by stratifying the target variable. 
** 
2.	Correlation matrix**

The correlation matrix gives the correlation coefficient between every two attributes in the data. Using seaborn library’s heat map, we can plot the correlation matrix. 

**3.	Sampling technique**

In this project, K-Fold cross validation strategy was used as the sampling technique. In K-Fold, the original dataset is shuffled and randomly partitioned into k equal-sized subsets called folds. A single subset from those k- subset is kept aside for validation of the testing the model, while the remaining (k-1) subsets are utilized to train the model. 

In this project 10-folds or subsets were created through which the models are rigorously trained. To evaluate the model performance cross validation score is used by plotting the confusion matrix for the models. 

**4.	One-hot encoding**

For the categorical variables in the dataset, one-hot encoding yields a sparse matrix. It produces a new column for each and every record for every category in the dataset, and then merges it with the original data set. To create the final dataset for model training, the category columns are removed. Pandas was used for get-dummies function to create the sparse matrix in this project. 

**6.0	Experimentation and Results**

Four models were employed to fit the data in this research. GridSearchCV from Sklearn was used to discover the optimum parameters, model, and scores. GridSearchCV makes use of a user-defined set of hyperparameters. The model is rigorously trained using the training data using these parameter combinations. 

**1.	K-nearest neighbour classifier**

In this model, classification is carried out by a simple majority voting strategy of each point's nearest neighbours: a query point is allocated to the data class having the most representation among the point's nearest neighbours. Below image is the best estimator for k-Nearest Neighbours according to GridSearchCV.

The classification report for this model is shown below: 


**2.	Decision tree**

Decision tree is the most common yet best model for classification tasks. GridSearchCV utilizes decision tree parameters such as tree depth, max leaf nodes, random-states to find the best parameters for the model.


**3.	Support Vector Machine**
By showing the hyperplane in the 2D plot of input and output variables, the support vector machine employs kernels to predict output class labels. The GridSearchCV may be used to define the model's parameters. 





**4.	Random-Forest Classifier**

To train and evaluate the data, Random Forest employs numerous decision trees. We may draw the attribute significance graph for predicting the output variable using this model.

The classification report was generated for the best estimator. 

**7.0	Model performance comparison**

The model performances were evaluated using Accuracies, Cross Validation scores, F1 scores and Precision and compared using bar plots.

                               Fig 1: Comparing Accuracies                                                           Fig 2: Comparing mean Cross Validation scores 
                         
                                Fig 3: Comparing F1 scores                                                                           Fig 4: Comparing Precision   	

We can observe in the above plots that Random-Forest Classifier was the best model since it performed the best in all scoring measures. 

**8.0	References**
1.	https://machinelearningmastery.com/
2.	https://stackoverflow.com/
3.	https://www.geeksforgeeks.org/
4.	https://towardsdatascience.com/




