# Credit_Card_Fraud_Detection
Credit Card Fraud Detection
This project is an implementation of a credit card fraud detection system. The model is trained on a dataset that contains transactions made by credit cards. The aim of this project is to identify fraudulent credit card transactions using Python, with the help of several data science libraries.

Requirements
This project requires the following Python libraries:

numpy
pandas
matplotlib
seaborn
sys
scipy
sklearn

You can install these libraries using pip:
pip install numpy pandas matplotlib seaborn scipy scikit-learn

#Data
The data used in this project is in CSV format. It includes transactions, with each transaction labeled as either 'Fraud' or 'Valid'. The original dataset has undergone a PCA transformation for privacy purposes.

Please replace the filepath to the creditcard.csv file in the script with the actual location of the file on your system.
data = pd.read_csv(r'/path/to/your/creditcard.csv')

#Data Analysis
The script includes a basic analysis of the dataset:

It prints the list of column names.
It prints the shape of the dataset.
It creates histograms of each feature.
It calculates the correlation matrix and visualizes it using a heatmap.
Fraud Detection Models
Two models are used in this project to detect fraudulent transactions:

Isolation Forest: This algorithm isolates observations by randomly selecting a feature and then randomly selecting a split value between the maximum and minimum values of the selected feature. The logic is that isolating anomaly observations is easier because only a few conditions are needed to separate those cases from the normal observations.

Local Outlier Factor (LOF): The anomaly score of each sample is called the Local Outlier Factor. It measures the local deviation of density of a given sample with respect to its neighbors. It is local in that the anomaly score depends on how isolated the object is with respect to the surrounding neighborhood.

#Evaluation
After running the models, the script prints the number of errors for each model, their accuracy scores, and a full classification report.

#Running the script
You can run the script using any Python 3.x interpreter. For example, if you're using the command line, navigate to the directory containing the script, then enter:

"python credit_card_fraud_detection.py"
Make sure to replace credit_card_fraud_detection.py with the name of your script file.

#Future Work
Future versions of this project could include more advanced techniques for fraud detection, using other machine learning models or even deep learning. In addition, it would be interesting to compare the performance of different models and tuning the hyperparameters of the models for optimal performance.

#Contribution
Feel free to fork the project, make a pull request, or to improve on what's already there. Any changes and suggestions are welcome!

#License
This project is open source, under the terms of the MIT License.

Side Note: The dataset is too large to upload to Github
