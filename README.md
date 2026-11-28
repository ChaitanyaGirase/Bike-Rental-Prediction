# Bike Rental Prediction

## Project Overview

This project analyzes the Bike Sharing dataset to understand bike rental patterns and predict the daily number of bike rentals.

The dataset contains:
- `day.csv`: 731 daily records
- `hour.csv`: 17,379 hourly records

## Objectives

- Understand the factors affecting bike rentals.
- Perform data cleaning and exploratory data analysis.
- Build regression models to predict daily bike rentals.
- Compare and tune models to find the best-performing model.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Structure

```text
Bike-Rental-Prediction/
│
├── data/
│   ├── day.csv
│   └── hour.csv
│
├── model/
│   └── bike_rental_model.pkl
│
├── notebooks/
│   └── bike_rental_analysis.ipynb
│
└── README.md
```

## Data Analysis

The project includes:
- Data quality checks and cleaning
- Missing value and outlier checks
- Rental analysis by season, month, weekday, holiday and weather
- Temperature and humidity analysis
- Casual and registered user analysis
- Daily and hourly rental trends
- Correlation analysis

### Key Findings

- Rentals are highest in summer and lowest in winter.
- Rental demand generally increases with temperature.
- Poor weather reduces bike rentals.
- Working days show peak rental activity around 8 AM and 5 PM.
- Demand increased from 2011 to 2012.

## Machine Learning Models

Four regression models were trained and evaluated:

1. Linear Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting

Hyperparameter tuning was performed using GridSearchCV with 5-fold cross-validation.

## Model Performance

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 616.52 | 830.10 | 0.8282 |
| Decision Tree (Tuned) | 567.71 | 867.34 | 0.8124 |
| Random Forest (Tuned) | 428.69 | 674.38 | 0.8866 |
| Gradient Boosting (Tuned) | 445.73 | 629.66 | 0.9011 |

## Final Model

Gradient Boosting was selected as the best overall model based on its test performance.

- **R² Score:** 0.9011
- **RMSE:** 629.66
- **MAE:** 445.73

Temperature and year were the most important features.

The trained model is saved in the `model/` folder as `bike_rental_model.pkl`.

## How to Run the Project

1. Clone this repository:

```bash
git clone https://github.com/ChaitanyaGirase/Bike-Rental-Prediction.git
```

2. Open the project folder:

```bash
cd Bike-Rental-Prediction
```

3. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

4. Open Jupyter Notebook:

```bash
jupyter notebook
```

5. Open the notebook inside the `notebooks/` folder and run the cells.

## Challenges Faced

- Handling invalid zero humidity values
- Checking windspeed outliers
- Avoiding data leakage
- Handling correlated features
- Applying feature scaling for Linear Regression
- Hyperparameter tuning
- Understanding the time trend in the dataset

## Limitations and Future Scope

A random train-test split was used even though the dataset contains a time trend. This may result in slightly optimistic evaluation scores.

Future improvements:
- Use a date-based train-test split.
- Predict hourly bike rental demand.
- Test the model on newer data.

## Conclusion

This project helped me understand the complete process of data analysis and regression modeling, from data cleaning and visualization to model training, evaluation and tuning.

Gradient Boosting achieved the best overall test performance among the four models.
