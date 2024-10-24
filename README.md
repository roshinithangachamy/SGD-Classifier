# SGD-Classifier
## AIM:
To write a program to predict the type of species of the Iris flower using the SGD Classifier.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1. Import Libraries: Load required libraries (NumPy, Pandas, Scikit-learn, Matplotlib, Seaborn).
2. Load Dataset: Use load_iris() to obtain the Iris dataset.
3. Prepare Data: Create a DataFrame and split it into features (X) and target (y); then split into training and testing sets.
4. Initialize Classifier: Create an instance of SGDClassifier.
5. Train Model: Fit the classifier on training data.
6. Make Predictions: Predict the species using test data.
7. Evaluate: Calculate accuracy and display the confusion matrix.
8. Output Results: Print accuracy and visualize the confusion matrix.

## Program:
```
Program to implement the prediction of iris species using SGD Classifier.
Developed by: T.Roshini
RegisterNumber: 212223230175


import pandas as pd
from sklearn.datasets import load_iris
from sklearn.linear_model import SGDClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix
iris = load_iris()
df=pd.DataFrame(data=iris.data,columns = iris.feature_names)
df['target']=iris.target
print(df.head())
X=df.drop('target',axis=1)
y=df['target']
X_train, X_test, y_train, y_test = train_test_split(X,y,test_size=0.2,random_state = 0)
sgd_clf = SGDClassifier(max_iter = 1000, tol = 1e-3)
sgd_clf.fit(X_train,y_train)
y_pred = sgd_clf.predict(X_test)
accuracy = accuracy_score(y_test,y_pred)
print(f"Accuracy: {accuracy:.3f}")
cm = confusion_matrix(y_test, y_pred)
print("Confusion Matrix: ")
print(cm)
```

## Output:

#### Head:

![369318176-42c2c25f-b995-4ea4-a740-146df4243967](https://github.com/user-attachments/assets/de8a552f-f7a0-4493-a49a-666f244f7819)

#### Accuracy and Confusion matrix:

![369318348-7c84dade-7112-4300-9d6e-fe26f737b7c6](https://github.com/user-attachments/assets/972ad491-5bed-4f4e-b68e-bd96f321d789)


## Result:
Thus, the program to implement the prediction of the Iris species using SGD Classifier is written and verified using Python programming.
