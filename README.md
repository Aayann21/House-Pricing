# House Price Prediction

## Project Description
This project predicts house prices using a **machine learning model**.
The dataset is loaded from an online source and a regression model is trained to predict house prices based on selected features.

## Libraries Used
The following Python libraries are used in this project:
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn

Imports used in the notebook:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
```
## Dataset
The dataset is loaded from the following URL:
```
https://raw.githubusercontent.com/selva86/datasets/master/BostonHousing.csv
```
The data is loaded using:
```python
data = pd.read_csv(url)
```

## Steps by step process


### 1. Import Libraries

Required libraries for data analysis, visualization, and machine learning are imported.


### 2. Load Dataset

The Boston Housing dataset is loaded using pandas.


### 3. Display Data

The first few rows of the dataset are displayed using:

```python
data.head()
```

### 4. Check Missing Values
The dataset is checked for null values using:
```python
data.isnull().sum()
```

### 5. Select Features and Target
Selected input features:
* rm
* lstat
* ptratio
Target variable:
* medv (house price)
```
x = data[['rm','lstat','ptratio']]
y = data['medv']
```

### 6. Split Dataset
The dataset is divided into **training and testing data** using:
```python
train_test_split()
```
Test size used: **20%**

### 7. Train Model
A **Linear Regression** model is created and trained.
```python
model = LinearRegression()
model.fit(X_train, y_train)
```

### 8. Make Predictions
Predictions are made on the test dataset.
```python
y_pred = model.predict(X_test)
```

### 9. Model Evaluation
The model is evaluated using:

* Mean Squared Error
* Root Mean Squared Error (RMSE)
* R² Score

### 10. Visualization
A scatter plot is created to compare **Actual Prices vs Predicted Prices**.
```python
plt.scatter(y_test, y_pred)
plt.xlabel("Actual Prices")
plt.ylabel("Predicted Prices")
plt.title("Actual vs Predicted House Prices")
```
