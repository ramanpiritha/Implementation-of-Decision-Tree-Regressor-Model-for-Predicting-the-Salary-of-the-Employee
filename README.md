# Ex.No-09-Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas
2. Calculate the null values present in the dataset and apply label encoder.
3. Determine test and training data set and apply decison tree regression in dataset.
4. calculate Mean square error,data prediction and r2.
## Program:
Developed by: Piritharaman R

RegisterNumber:  212223230148
```
import pandas as pd
data=pd.read_csv("Salary.csv")
data
```

## Output:
![image](https://github.com/user-attachments/assets/2b520c69-a854-441b-bb5e-db96d881a607)

```
df.info()
```
## Output:

![image](https://github.com/user-attachments/assets/58aa7a60-946e-4e85-8bf8-346a3884c3fa)

```
data.isnull().sum()
```
## Output:
![image](https://github.com/user-attachments/assets/06abc2bb-cb24-4261-9ec7-1d18d05c3e4b)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
## Output:

![image](https://github.com/user-attachments/assets/dc92b56a-75e5-4e59-b66e-08362f0ed304)

```
x = data[["Position", "Level"]]
y = data["Salary"]
```
```
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2)
```
```
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train, y_train)
y_pred = dt.predict(x_test)
```
```
from sklearn import metrics
mse = metrics.mean_squared_error(y_test, y_pred)
mse
```
## Output:

![image](https://github.com/user-attachments/assets/e2903830-9e03-4cff-b953-66a367f76699)

```
r2 = metrics.r2_score(y_test, y_pred)
r2
```
## Output:

![image](https://github.com/user-attachments/assets/38deb4a0-2c48-4a36-8179-52284e44e670)
```
dt.predict([[5,6]])
```
## Output:
![image](https://github.com/user-attachments/assets/8e7c1075-72b2-45e1-ae1c-d8fb9b30fa6d)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
