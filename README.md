# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.

2.Upload the csv file and read the dataset.

3.Check for any null values using the isnull() function.

4.From sklearn.tree inport DecisionTreeRegressor.

5.Import metrics and calculate the Mean squared error.

6.Apply metrics to the dataset, and predict the output.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Mangari Deeraj
RegisterNumber:212223100031  
*/
```
```
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
x.head()

y=data[["Salary"]]

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
Initial Dataset:

![318789424-33faca45-0c8f-49fd-905d-954838a675ce](https://github.com/user-attachments/assets/a0000721-1b56-4dac-aed8-083551674cf2)

Data Info:

![318789438-daed8dfd-55c0-4e58-bf3a-d62c3dfdffdd](https://github.com/user-attachments/assets/8684366f-3fe8-4ec2-938b-1b0f0d6f01ef)

Optimization of null values:

![318789457-005453a7-304b-48ee-8716-be3417e266c8](https://github.com/user-attachments/assets/363196cf-f076-48ac-8ac8-f1f97ce906b0)

Converting string literals to numerical values using label encoder:

![318789472-49c1c499-bda8-47b6-b395-56bf36923a9d](https://github.com/user-attachments/assets/7a33043a-180e-4322-bb22-32bc1adeffe8)

Mean Squared Error:

![318789492-b36bf828-7382-4275-91d4-190ff0d2ed14](https://github.com/user-attachments/assets/9177fa3d-2ff9-414b-9b51-c9ccef0e0dbf)

R2 (Variance):

![318789505-6b239db9-34f5-4051-8c48-cbed92f83de9](https://github.com/user-attachments/assets/86761ab0-8f00-42de-9007-0e08eacb8bc3)

Perdicition:

![318789518-77e886b1-2968-4027-a2ce-6582665fa16a](https://github.com/user-attachments/assets/bed0a88d-c763-4b05-bffa-27532ac737c7)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
