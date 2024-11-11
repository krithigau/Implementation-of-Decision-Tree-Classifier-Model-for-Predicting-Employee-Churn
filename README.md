# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries. 
2.Upload and read the dataset.
3.Check for any null values using the isnull() function.
4.From sklearn.tree import DecisionTreeClassifier and use criterion as entropy.
5.Find the accuracy of the model and predict the required values by importing the required module from sklearn.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Krithiga U
RegisterNumber: 212223240076
*/
import pandas as pd
data = pd.read_csv("Employee.csv")
data.head()
data.info()

data.isnull().sum()

data["left"].value_counts

from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()

x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]

x.head()
y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)

from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)

y_pred = dt.predict(x_test)
from sklearn import metrics

accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```
## Output:
##HEAD() & INFO():

![image](https://github.com/user-attachments/assets/ea967636-3019-4b34-8e78-35768d4deee4)

![image](https://github.com/user-attachments/assets/cbfb6fe8-5f39-4d0d-b977-b97e2a51af55)

data.isnull().sum()

![image](https://github.com/user-attachments/assets/99bb5c13-ec29-492a-8f32-b6dfe354743c)

data.value.counts()

![image](https://github.com/user-attachments/assets/024e96b5-ac87-4252-a025-b8157834ebf7)

x.head()

![image](https://github.com/user-attachments/assets/04df92d2-fe0a-443b-915c-78971b3c106b)

##ACCURACY SCORE: 

![image](https://github.com/user-attachments/assets/c75dd1b2-4688-4447-8f08-4df16abf0a73)

prediction:

![image](https://github.com/user-attachments/assets/c326e790-6f08-43e6-b079-42b93cbda270)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
