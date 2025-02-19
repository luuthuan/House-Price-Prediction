# House Price Prediction Project

Automatically generated by Colab.

Original file is located at [this Colab link](https://colab.research.google.com/drive/1Tm4PDXHjL8QDmJFLq_miJMMMklQ8NVzh?usp=sharing).

---

## 1. Problem Definition

* **Goal**: Predict the sales price for each house.

## 2. Feature Selection

* Choose features to train ML Model.
* Need to use `Feature Engineering` to identify necessary features.

## 3. Splitting the Dataset

### 3.1. Dataset -> X, y

* `data`: original dataset.
* `X`: `data[features]`.
* `y`: target variable `SalePrice`.

### 3.2. `X and y` -> `X_train`, `y_train` and `X_valid`, `y_valid`

* `X`: `data[features]` split into training (`X_train`, `y_train`) and validation (`X_valid`, `y_valid`) sets to predict `SalePrice`.

## 4. Training Machine Learning Model

### 4.1 Using Decision Tree

#### Create DecisionTreeModel variable

```python
from sklearn.tree import DecisionTreeRegressor
dt_model = DecisionTreeRegressor(random_state=1)
``` 

#### Fit training data into model

```
dt_model.fit(X_train, y_train)
```

#### Prediction

```commandline
y_predict = dt_model.predict(X_valid.head())
```

### 4.2. Using Random Forest
#### Create RandomForestModel variable
```commandline
from sklearn.ensemble import RandomForestRegressor
rf_model = RandomForestRegressor(random_state=1)
```

#### Fit training data into model
```commandline
rf_model.fit(X_train, y_train)
```

#### Prediction
```commandline
rf_val_preds = rf_model.predict(X_valid)
```

#### Predict with a new input
```commandline
rf_model.predict([[6969, 2021, 1000, 800, 4, 5, 8]])
```

## 5. Model Evaluation
### Evaluation Metrics
```commandline
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

# Predict on the training data
y_pred = rf_model.predict(X_train)

# Calculate evaluation metrics
mae = mean_absolute_error(y_train, y_pred)
mse = mean_squared_error(y_train, y_pred)
rmse = np.sqrt(mse)
r2 = r2_score(y_train, y_pred)

print("Model Evaluation Metrics:")
print(f"Mean Absolute Error (MAE): {mae}")
print(f"Mean Squared Error (MSE): {mse}")
print(f"Root Mean Squared Error (RMSE): {rmse}")
print(f"R-squared (R²): {r2}")
```
<hr>

```commandline
This readme provides an overview of the House Price Prediction project, including problem definition, feature selection, dataset splitting, model training using Decision Tree and Random Forest, and model evaluation metrics.
```

