# Ex.No: 13 Learning – Use Supervised Learning  
### DATE: 24.10.2024                                                                           
### REGISTER NUMBER : 212222060279
### AIM: 
To write a program to train the classifier for Heart Disease Prediction.
###  Algorithm:
1. Import the necessary libraries.
2. Read the dataset.
3. Complete the necessary data preprocessing.
4. Then split the dataset into training and test dataset.
5. Train the classifier with Logistic regression.
6. Print the accuracy score and classification report.

### Program:
```
import numpy as np
import pandas as pd
from sklearn.preprocessing import MinMaxScaler,StandardScaler,LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
import matplotlib.pyplot as plt
from sklearn.metrics import accuracy_score , precision_score , recall_score , f1_score ,classification_report ,confusion_matrix

file_path = "C:/Users/charu/Downloads/Heart_Disease_Prediction.csv"
data = pd.read_csv(file_path)

data.head()
data.describe()
data['Heart Disease'].value_counts()
numerical_columns = ['Age', 'BP', 'Cholesterol', 'Max HR', 'ST depression']

mean_values = data[numerical_columns].mean()
print("Mean values of numerical columns:")
print(mean_values)
le = LabelEncoder()

data['Heart Disease'] = le.fit_transform(data['Heart Disease'])

categorical_columns = ['Chest pain type', 'EKG results', 'Slope of ST', 'Thallium']

for col in categorical_columns:
    data[col] = le.fit_transform(data[col])

data.head()
scaler = MinMaxScaler()

numerical_columns = ['Age', 'BP', 'Cholesterol', 'Max HR', 'ST depression']

data[numerical_columns] = scaler.fit_transform(data[numerical_columns])

data.head()
X = data.drop(columns=['Heart Disease'])  
y = data['Heart Disease']  

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

X_train.shape, X_test.shape, y_train.shape, y_test.shape
scaler = StandardScaler()

X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

(X_train_scaled.shape, X_test_scaled.shape)
print("Scaled training data shape:", X_train_scaled.shape)
print("Scaled testing data shape:", X_test_scaled.shape)
logistic_model = LogisticRegression(random_state=42)
logistic_model.fit(X_train_scaled, y_train)
logistic_y_pred = logistic_model.predict(X_test_scaled)
logistic_accuracy = accuracy_score(y_test, logistic_y_pred)
print("Accuracy: ",logistic_accuracy*100)
report = classification_report(y_test, logistic_y_pred, target_names=['Absence', 'Presence'])
print(report)
```
### Output:
<img width="731" alt="image" src="https://github.com/user-attachments/assets/0ea1dd72-e7e9-48f9-96ed-db53f56cd86f"><br>
<img width="659" alt="image" src="https://github.com/user-attachments/assets/6d018635-c80d-4e70-a40c-3d1f7b3a4de6"><br>
<img width="466" alt="image" src="https://github.com/user-attachments/assets/cbf1fd5c-84c4-4547-b6b2-532f623eef2d">







### Result:
Thus the system was trained successfully and the prediction was carried out.
