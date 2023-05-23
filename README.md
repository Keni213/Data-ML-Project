<h1> Wine Data Review and Pricing Prediction </h1>

The wine industry is an extensive and complex ecosystem with thousands of wine varietals, production methods, and regions. The use of big data analytics in the wine industry has the potential to unlock invaluable insights for wine growers, winemakers, and consumers alike. In this course, we propose to explore the use of big data analytics and build a pricing model which can be applied for predicting a specific wine price by given information. This model will be valuable for market positioning and pricing strategy in the wine industry.

This project is divided into three main parts:

Part I: Data analysis and preprocessing, transform raw data into correct format for following model construction.

Part II: Model Selection, training and tuning for two types of Regression model: Linear Regression and Logistic Regression.

Part III: Expand research with more powerful machine learning modes: Decision Tree, Random Forest and Neural Network Model.

Model Comparison and Conclusion:
After tuning the parameters, Linear Regression Model performance of Lasso/Ridge regression model is improved. The best performance of Lasso/Ridge model will correspond to accuracy around 54%.
Logistic Regression Model: the accuracy after applying with PCA remains stable around 32%.
Neural network model: apply a neural network with more complex function and more parameters to build a multiclass classifier model.
Random Forest performs better than Decision Tree in our Model, as it prevents overfitting and provides more accuracy prediction.

Challenges and Obstacles Faced:
Data selection bias makes this study challenging to extract more determined factors of marketing price in the wine industry.
At first we wanted to include the province, region, and designation(vineyard) as features. But we found there are too many provinces, regions and designations. If we apply one-hot encoding to all of them, the operation will be at a very high cost. If we select only a portion of them (say, top 20), we will lose too many varieties, and therefore lose too much data for training and prediction. So we decided to give them up as features.
Originally we would like "winery" to be one of the features. But there are too many wineries to do one hot encoding. And there will not be enough data if we only keep a few wineries (say, top 20). So we calculate the average points for each winery. We decided to use "winery_point" as one feature to represent the quality/reputation of a winery.
When we first trained a neural network, previously we found that while the loss kept falling, the accuracy wasn't changing. We found during debugging that the predicted output tensor didn't match with the true label tensor because the datatype is float. So we have to cast the tensor datatype from float to int. And finally we could calculate the accuracy correctly.

Potential Next Steps
We could combine the data with other dataset to add more valuable features for our prediction. For example the condition of soil/climate for vineyard growing grapes.
Although we use country instead of region as a feature because most of the wine data come from the top 20 countries that we have selected from the country data. The data is imbalanced as for example wine from the US contribute to around 50% of all wine. We could oversample or undersample the data for balance purpose, meanwhile think of how to balance data without affecting the accuracy of prediction.
We use sentiment scores as one of the features for our prediction. But the score calculated by nltk toolkit may not represent the true positivity/negativity of the sentences. We could use other methods to help make the sentiment score more precise for the positivity/negativity of the sentences, thus make the feature more helpful to the prediction.* We could try a more robust and complex neural network, with more hidden layers and varying activation functions.
Hyperparameter finer tuning will help us to further improve the performance of learning and prediction.