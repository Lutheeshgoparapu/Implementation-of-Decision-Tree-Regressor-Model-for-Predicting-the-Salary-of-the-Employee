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

4.From sklearn.tree inport DecisionTreeRegressor.

5.Import metrics and calculate the Mean squared error.

6.Apply metrics to the dataset, and predict the output.

## Program:
```

Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: G.Lutheesh
RegisterNumber:  212221230029

```
```
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()

data["Position"] = le.fit_transform(data["Position"])

data.head()

x = data[["Position","Level"]]

y = data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)

y_pred = dt.predict(x_test)

from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse

r2 = metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
### Data Head:
![11](https://github.com/Lutheeshgoparapu/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94154531/a35bfeb8-07c4-457e-93f5-3d420b0f23a8)

### Data Info:
![22](https://github.com/Lutheeshgoparapu/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94154531/0dda55ed-a0b8-4416-abfa-feeec0d3e25f)

### Data Head after applying LabelEncoder:
![33](https://github.com/Lutheeshgoparapu/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94154531/3a6bc8c1-f7e6-43d6-866e-5852fdc96b7b)

### MSE
![44](https://github.com/Lutheeshgoparapu/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94154531/41411460-721f-45f6-88e5-50ced9a5c6d1)

### R2
![55](https://github.com/Lutheeshgoparapu/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94154531/b95fbcb5-6cdd-4299-b29b-7f9a08ce2a5b)

### Data Prediction:
![66](https://github.com/Lutheeshgoparapu/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94154531/3cb19f8c-633c-40d2-a441-4a063b3e2fe6)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
