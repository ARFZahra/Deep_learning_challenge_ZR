# Deep_learning_challenge_ZR

Alphabet Soup Funding Classifier

Overview of the Analysis:
The objective of this analysis is to build a binary classification model that predicts whether an organization applying for funding from Alphabet Soup will be successful if funded. The analysis utilizes machine learning, specifically a neural network, to identify patterns in historical data to guide funding decisions.

Data Preprocessing:
Target Variable:
•	IS_SUCCESSFUL — This is the target column that indicates whether the organization was successful (1) or not (0) after receiving funding.

Feature Variables:
•	The features used for the model include:
o	APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT

Variables to Remove:
•	EIN and NAME — These columns are unique identifiers for the organizations and are not useful for predicting success. Therefore, they were removed from the dataset.

Compiling, Training, and Evaluating the Model:

First Model:
•	Architecture:
o	Input layer: 80 neurons (ReLU activation)
o	Hidden layer 1: 30 neurons (ReLU activation)
o	Output layer: 1 neuron (Sigmoid activation)
•	Results:
o	Training accuracy: ~74%
o	Test accuracy: ~72.65%
o	Loss: 0.5655
•	Outcome: The first model performed reasonably well, but to increase the accuracy more than 75% I did further tuning. 

Second Model:
•	Architecture:
o	Added a third hidden layer to increase model complexity.
o	Used different activation functions: ReLU for the first layer and Tanh for the second and third layers.
o	Increased the number of epochs to 120 with a 20% validation split.

•	Results:
o	Training accuracy: ~74%
o	Test accuracy: 72.65%
o	Loss: 0.5649

•	Outcome: This model-maintained performance at a similar level, but the additional complexity did not significantly improve accuracy.

Third Model (with Regularization and Early Stopping):
•	Architecture:
o	Increased complexity with 128 neurons in the first layer, 64 in the second, and 32 in the third.
o	Added L2 regularization and dropout to prevent overfitting.
o	Implemented early stopping and learning rate reduction to fine-tune the model.
•	Results:
o	Training accuracy: ~73.31%
o	Validation accuracy: ~73.96%
o	Test accuracy: 72.52%
o	Loss: 0.5647
•	Outcome: The third model introduced regularization to prevent overfitting, leading to a more stable performance. However, the accuracy remains around 72.52%, indicating that while the model is not overfitting, further tuning is necessary to improve performance.

Steps Taken to Improve Performance:
1.	Increased model complexity: Adding more layers and increasing neurons in each layer.
2.	Regularization techniques: Applied L2 regularization and dropout to mitigate overfitting.
3.	Learning rate reduction: Used callbacks to reduce learning rates when the model plateaued.
4.	Early stopping: Used to halt training when improvements ceased, preventing overfitting.

Recommendations:
While all three models performed similarly with ~73% to 74% training accuracy and ~72% test accuracy, the third model is recommended for deployment due to its use of regularization and early stopping, which help prevent overfitting. Despite only a marginal improvement in test accuracy, these techniques ensure better generalization to unseen data.

For future improvements, it is advisable to explore other machine learning algorithms like Random Forest or XGBoost, which may yield better performance with this dataset's structure.

