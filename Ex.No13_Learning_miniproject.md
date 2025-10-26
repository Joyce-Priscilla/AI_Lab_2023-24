# Ex.No: 10 Learning – Use Supervised Learning  
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 

To predict the power output (kW) of a wind turbine using real-time operational and environmental data such as wind speed, temperature, and turbine parameters, by applying a suitable machine learning algorithm. The prediction helps in optimizing energy production, scheduling maintenance, and improving efficiency in renewable energy systems.

###  Algorithm:

## Algorithm (Random Forest Regressor)

## Step 1: Data Collection

Collect the wind turbine dataset (T1.csv) containing features like wind speed, temperature, rotor speed, and the target column LV ActivePower (kW).

Step 2: Data Preprocessing

Remove irrelevant columns (e.g., Date/Time).

Handle missing values if any.

Split the dataset into features (X) and target (y).

Step 3: Train-Test Split

Divide the dataset into training set (80%) and testing set (20%) to evaluate the model’s performance.

Step 4: Model Selection

Choose Random Forest Regressor because it handles non-linear relationships, is robust to noise, and provides feature importance.

Step 5: Model Training

Train multiple decision trees on different subsets of training data.

At each split, choose a random subset of features to reduce overfitting.

Step 6: Prediction

Predict power output for the test set by averaging predictions from all decision trees.

Step 7: Evaluation

Measure performance using metrics:

R² Score – how well the model explains output variability.

MAE (Mean Absolute Error) – average prediction error.

RMSE (Root Mean Squared Error) – magnitude of prediction error.

Step 8: Feature Importance (Optional)

Identify which features most influence power output (e.g., wind speed, rotor speed).

### Program:


### Output:


### Result:
Thus the system was trained successfully and the prediction was carried out.
