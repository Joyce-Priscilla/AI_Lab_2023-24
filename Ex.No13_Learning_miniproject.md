# Ex.No: 13 Machine Learning
### DATE: 26.10.2025                                                                           
### REGISTER NUMBER : 212223060107
### AIM: 

To predict the power output (kW) of a wind turbine using real-time operational and environmental data such as wind speed, temperature, and turbine parameters, by applying a suitable machine learning algorithm. The prediction helps in optimizing energy production, scheduling maintenance, and improving efficiency in renewable energy systems.

###  Algorithm:

### Algorithm (Random Forest Regressor)

### Step 1: Data Collection

Collect the wind turbine dataset (T1.csv) containing features like wind speed, temperature, rotor speed, and the target column LV ActivePower (kW).

### Step 2: Data Preprocessing

Remove irrelevant columns (e.g., Date/Time).

Handle missing values if any.

Split the dataset into features (X) and target (y).

### Step 3: Train-Test Split

Divide the dataset into training set (80%) and testing set (20%) to evaluate the model’s performance.

### Step 4: Model Selection

Choose Random Forest Regressor because it handles non-linear relationships, is robust to noise, and provides feature importance.

### Step 5: Model Training

Train multiple decision trees on different subsets of training data.

At each split, choose a random subset of features to reduce overfitting.

### Step 6: Prediction

Predict power output for the test set by averaging predictions from all decision trees.

### Step 7: Evaluation

Measure performance using metrics:

R² Score – how well the model explains output variability.

MAE (Mean Absolute Error) – average prediction error.

RMSE (Root Mean Squared Error) – magnitude of prediction error.

### Step 8: Feature Importance (Optional)

Identify which features most influence power output (e.g., wind speed, rotor speed).

### Program:

```


# Step 1: Import required libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import r2_score, mean_absolute_error, mean_squared_error
from google.colab import files

# Step 2: Upload your dataset (T1.csv)
print("Please upload your T1.csv file:")
uploaded = files.upload()

# Get uploaded filename dynamically
filename = list(uploaded.keys())[0]
print(f"File uploaded: {filename}")

# Step 3: Load dataset
data = pd.read_csv(filename)
print("Dataset Loaded Successfully!\n")

# Step 4: Display basic info
print("First 5 rows:")
print(data.head(), "\n")

print("Columns in dataset:")
print(list(data.columns), "\n")

printa("Missing values per column:")
print(data.().sum(), "\n")

# Step 5: Define target and features
target_column = "LV ActivePower (kW)"   # The column to predict
drop_columns = ["Date/Time"]            # Columns to ignore (non-numeric)

# Select features and target
X = data.drop

 WIND TURBINE POWER PREDICTION MODEL

# Step 5: Define target and features
target_column = "LV ActivePower (kW)"   # what we want to predict
drop_columns = ["Date/Time"]            # ignore this (non-numeric)

# Features and target selection
X = data.drop(columns=drop_columns + [target_column])
y = data[target_column]

# Step 6: Split into training/testing sets
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Step 7: Train the Random Forest model
from sklearn.ensemble import RandomForestRegressor
model = RandomForestRegressor(n_estimators=200, random_state=42)
model.fit(X_train, y_train)

# Step 8: Make predictions
y_pred = model.predict(X_test)

# Step 9: Evaluate model
from sklearn.metrics import r2_score, mean_absolute_error, mean_squared_error
import numpy as np

r2 = r2_score(y_test, y_pred)
mae = mean_absolute_error(y_test, y_pred)
rmse = np.sqrt(mean_squared_error(y_test, y_pred))  # Compatible with all sklearn versions

print("Model Trained Successfully!\n")
print("Model Evaluation Metrics:")
print(f"R² Score : {r2:.4f}")
print(f"MAE      : {mae:.4f}")
print(f"RMSE     : {rmse:.4f}")

# Step 10: Visualization - Actual vs Predicted
import matplotlib.pyplot as plt

plt.figure(figsize=(7,7))
plt.scatter(y_test[:200], y_pred[:200], color='green', alpha=0.6, edgecolor='k')
plt.xlabel("Actual LV ActivePower (kW)")
plt.ylabel("Predicted LV ActivePower (kW)")
plt.title("Wind Turbine Power Prediction (Random Forest)")
plt.grid(True)
plt.show()

# Step 11: Optional - Feature importance
import pandas as pd

importances = pd.Series(model.feature_importances_, index=X.columns)
plt.figure(figsize=(6,4))
importances.sort_values().plot(kind='barh', color='skyblue')
plt.title("Feature Importance in Prediction")
plt.xlabel("Importance Score")
plt.show()


```

### Output:

![Screenshot 2025-10-26 184642](https://github.com/user-attachments/assets/1e71f860-4fcb-4059-b859-87022e47b009)


<img width="626" height="624" alt="image" src="https://github.com/user-attachments/assets/4d1d8e54-f187-4698-bc69-630d5ae7c7cc" />


<img width="715" height="393" alt="image" src="https://github.com/user-attachments/assets/36dd4a21-0f8a-4b11-9e84-92dd044735ac" />


### Result:

The system was trained successfully using a Random Forest Regressor, and predictions for wind turbine power output were carried out. The model performed well, achieving an R² score of 0.95, MAE of 15.32 kW, and RMSE of 22.87 kW. The predicted values closely matched the actual outputs, and feature importance analysis showed that wind speed was the most influential factor. This system can effectively assist in optimizing energy production and improving wind turbine efficiency.
