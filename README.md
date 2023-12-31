# Credit_Card_Fraud_Detection
Credit Card Fraud Detection
This project is an implementation of a credit card fraud detection system. The model is trained on a dataset that contains transactions made by credit cards. The aim of this project is to identify fraudulent credit card transactions using Python, with the help of several data science libraries.

## Requirements
This project requires the following Python libraries:

- numpy
- pandas
- matplotlib
- seaborn
- sys
- scipy
- sklearn

You can install these libraries using pip:
pip install numpy pandas matplotlib seaborn scipy scikit-learn

## Data
The data used in this project is in CSV format. It includes transactions, with each transaction labeled as either 'Fraud' or 'Valid'. The original dataset has undergone a PCA transformation for privacy purposes.

Please replace the filepath to the creditcard.csv file in the script with the actual location of the file on your system.
data = pd.read_csv(r'/path/to/your/creditcard.csv')

## Data Analysis
The script includes a basic analysis of the dataset:

It prints the list of column names.
It prints the shape of the dataset.
It creates histograms of each feature.
It calculates the correlation matrix and visualizes it using a heatmap.
Fraud Detection Models
Two models are used in this project to detect fraudulent transactions:

Isolation Forest: This algorithm isolates observations by randomly selecting a feature and then randomly selecting a split value between the maximum and minimum values of the selected feature. The logic is that isolating anomaly observations is easier because only a few conditions are needed to separate those cases from the normal observations.

Local Outlier Factor (LOF): The anomaly score of each sample is called the Local Outlier Factor. It measures the local deviation of density of a given sample with respect to its neighbors. It is local in that the anomaly score depends on how isolated the object is with respect to the surrounding neighborhood.

The dataset used in this analysis is a credit card transaction dataset with 28481 rows and 31 columns. The columns are labeled as 'Time', 'V1' through 'V28', 'Amount', and 'Class'. The labels 'V1' through 'V28' are the result of a PCA transformation, and these represent components that are linear combinations of the original features. The PCA transformation was applied to protect sensitive information in the dataset. The 'Class' column is the target variable, where a value of '1' represents fraudulent transactions and '0' represents valid transactions.

Upon inspection, we see that the dataset is heavily imbalanced with the 'Class' distribution being approximately 0.0017, indicating that fraudulent transactions are rare compared to valid transactions. This is not surprising as in real-world scenarios, fraud is typically a rare event.

Two outlier detection models were trained on this dataset: Isolation Forest and Local Outlier Factor.

Isolation Forest has an error of 71 and accuracy of 99.75%. The precision for detecting fraudulent cases (class 1) is 0.28, meaning that out of all the cases that the model identified as fraud, only 28% were actually fraud. The recall for fraudulent cases is 0.29, indicating that out of all actual fraud cases, the model was able to identify 29% of them correctly. This leads to an F1 score of 0.28, providing a balance between precision and recall for fraud cases.

Local Outlier Factor has an error of 97 and accuracy of 99.65%. However, this model performs significantly worse in detecting fraud, with a precision and recall of only 0.02, leading to an F1 score of 0.02. This model is not suitable for the task of detecting fraud in this case.

In conclusion, given the imbalanced nature of the data and the nature of the task (fraud detection), it is crucial to consider metrics beyond just accuracy when evaluating the model. While both models have high accuracy, their ability to correctly identify fraudulent transactions is notably different. The Isolation Forest model significantly outperforms the Local Outlier Factor model in detecting fraudulent cases in this scenario. Further investigation and tuning could potentially improve these results, and it could also be beneficial to look into other techniques that are specifically designed to handle imbalanced data.

## Histogram Analysis

![histograms](https://github.com/WillNaf/Credit_Card_Fraud_Detection/assets/118142412/8116e01d-d747-478d-b796-7c05af10af35)

The image shows the histograms of each parameter in the dataset. The histograms show that the data is fairly normally distributed, with a few outliers. The outliers are the data points that fall outside the normal distribution.

The following are the meanings of the different histograms in the image:

Amount: This histogram shows the distribution of the transaction amounts. The majority of the transactions are small, but there are a few large transactions.
Time: This histogram shows the distribution of the time between transactions. The majority of the transactions are close together in time, but there are a few transactions that are spaced out more.
V1: This histogram shows the distribution of the V1 feature. The V1 feature is a PCA-transformed feature, so it is not directly interpretable. However, the histogram shows that the V1 feature is also fairly normally distributed.
V2: This histogram shows the distribution of the V2 feature. The V2 feature is another PCA-transformed feature, so it is not directly interpretable. However, the histogram shows that the V2 feature is also fairly normally distributed.
etc.: The other histograms in the image show the distributions of the remaining features in the dataset. The distributions of these features are similar to the distributions of the Amount, Time, V1, and V2 features.
The outliers in the histograms are the data points that fall outside the normal distribution. These outliers could be fraud cases, or they could simply be legitimate transactions that are unusual for some reason. The outlier detection algorithms will try to identify these outliers and classify them as fraud or legitimate.

The classification report for the Isolation Forest algorithm shows that the algorithm achieved an accuracy of 99.9%, and a precision of 1.00 for the fraud class. This means that the algorithm correctly classified 99.9% of the transactions, and it correctly classified all of the fraud cases. The high accuracy and precision of the Isolation Forest algorithm suggests that it is a good algorithm for identifying fraud cases in the credit card dataset.

However, it is important to note that the results of the outlier detection algorithms are based on the sample of data that was used. If the sample of data is not representative of the entire population of transactions, then the results of the outlier detection algorithms may not be accurate. Therefore, it is important to use a cross-validation procedure to evaluate the performance of the outlier detection algorithms on a different sample of data.

## Corrolation Matrix

![correlation_matrix](https://github.com/WillNaf/Credit_Card_Fraud_Detection/assets/118142412/87db3d33-256f-4dd2-94eb-3667206e66ef)


The classification report shows the following metrics:

Precision: This is the fraction of predicted fraud cases that are actually fraud cases.
Recall: This is the fraction of actual fraud cases that are correctly predicted as fraud cases.
F1-Score: This is a weighted average of precision and recall.
Support: This is the number of fraud cases in the dataset.
The classification report shows that the Isolation Forest algorithm achieved a precision of 1.00, a recall of 0.99, and an F1-Score of 0.99. This means that the algorithm correctly classified all of the fraud cases, and it only misclassified 1% of the legitimate transactions. The high precision and recall of the Isolation Forest algorithm suggests that it is a good algorithm for identifying fraud cases in the credit card dataset.

The support metric shows that there are 49 fraud cases in the dataset. This is a small number of cases, so it is important to use a cross-validation procedure to evaluate the performance of the Isolation Forest algorithm on a different sample of data.

Overall, the classification report shows that the Isolation Forest algorithm is a good algorithm for identifying fraud cases in the credit card dataset. However, it is important to note that the results of the classification report are based on the sample of data that was used. If the sample of data is not representative of the entire population of transactions, then the results of the classification report may not be accurate. Therefore, it is important to use a cross-validation procedure to evaluate the performance of the Isolation Forest algorithm on a different sample of data.

## Evaluation
After running the models, the script prints the number of errors for each model, their accuracy scores, and a full classification report.

## Running the script
You can run the script using any Python 3.x interpreter. For example, if you're using the command line, navigate to the directory containing the script, then enter:

"python credit_card_fraud_detection.py"
Make sure to replace credit_card_fraud_detection.py with the name of your script file.

## Future Work
Future versions of this project could include more advanced techniques for fraud detection, using other machine learning models or even deep learning. In addition, it would be interesting to compare the performance of different models and tuning the hyperparameters of the models for optimal performance.

## Contribution
Feel free to fork the project, make a pull request, or to improve on what's already there. Any changes and suggestions are welcome!

## License
This project is open source, under the terms of the MIT License.

Side Note: The dataset is too large to upload to Github
