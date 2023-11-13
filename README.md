# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries.

2.Upload the csv file and read the dataset.

3.Check for any null values using the isnull() function.

4.From sklearn.tree import DecisionTreeRegressor.

5.Import metrics and calculate the Mean squared error.

6.Apply metrics to the dataset, and predict the output.
 
## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: PRADEEPASRI S
RegisterNumber: 212221220038 
*/
import pandas as pd
data=pd.read_csv("/content/Salary.csv")

print("data.head():")
data.head()

print("data.info():")
data.info()

print("isnull() and sum():")
data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
print("data.head() for salary:")
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
mse=metrics.mean_squared_error(y_test,y_pred)
print("MSE value:")
mse

r2=metrics.r2_score(y_test,y_pred)
print("r2 value:")
r2

print("data prediction:")
dt.predict([[5,6]])
```

## Output:
## data.head()
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/ab22b348-773a-4264-b355-9f62b3d1f4b5)
## data info()
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/bc71ef1c-e91a-403b-9d5a-e573d924686e)
## isnull() and sum() function
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/fbd7f42e-6f1e-47b0-b644-8eae03abc50b)
## data.head() for salaery
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/99b444e4-b374-4b85-bf70-370fe249281a)
## MSE value
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/684a98b2-406e-46e2-beeb-ea6f48620a00)
## R2 value
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/bada2635-59df-4683-8f6a-b9517071eba2)
## Prediction value
![image](https://github.com/pradeepasri26/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/131433142/f48e8cfd-9155-48f2-a018-5c67672d2e55)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
