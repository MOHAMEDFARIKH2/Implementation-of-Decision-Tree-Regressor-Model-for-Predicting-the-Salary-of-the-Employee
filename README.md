# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step-1:
Import the required libraries .

Step-2:
Read the data frame using pandas.

Step-3:
Get the information regarding the null values present in the dataframe.

Step-4:
Apply label encoder to the non-numerical column inoreder to convert into numerical values.

Step-5:
Determine training and test data set.

Step-6:
Apply decision tree regression on to the dataframe.

Step-7:
Get the values of Mean square error, r2 and data predictio
## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: H MOHAMED FARIKH
RegisterNumber: 212223080032
*/
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])

```

## Output:

data.head()
![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/4983a6fd-c626-4d01-8077-23d05a53b382)


data.info()

![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/f4df8708-4b46-49fc-bbd3-66660e2dfa84)


Isnull() & sum() function

![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/2e2bad2c-fb83-4b28-89f6-300b8266ac9a)

data.head() for position

![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/6ad21881-bd9d-4345-9a3d-e67c5aaeda42)


MSE value

![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/f75a937a-2f64-440c-9875-d1dbe524676c)


R2 value

![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/3a6369fa-d35d-4659-a688-f1d6323a4b5c)


Prediction value

![image](https://github.com/MOHAMEDFARIKH2/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/168570140/6ca9b89b-5cc6-47f8-b12c-144d4bf340d2)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
