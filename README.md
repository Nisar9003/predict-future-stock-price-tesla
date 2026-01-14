# predict-future-stock-price-tesla


## Objective
The goal of this project is to predict the next day's closing price of Tesla (TSLA) using historical stock data. Linear Regression is used to model the relationship between stock features and the next day's closing price.

---

## Dataset
- **Source:** Yahoo Finance
- **Ticker:** TSLA (Tesla)
- **Date Range:** 2010-01-01 to 2026-01-01
- **Features Used:** Open, High, Low, Volume
- **Target:** Next Day Closing Price

The dataset is fetched using the Python `yfinance` library.

---

## Libraries Used
- `yfinance` → to fetch historical stock data
- `pandas` → data manipulation
- `numpy` → numerical operations
- `scikit-learn` → Linear Regression, train-test split, metrics
- `matplotlib` & `seaborn` → visualization

---

## Workflow

### 1. Data Fetching
Historical Tesla stock data is downloaded using `yfinance`. The `Date` column is preserved for plotting, and the dataset includes Open, High, Low, Close, and Volume.

### 2. Feature & Target Preparation
- **Features:** Open, High, Low, Volume  
- **Target:** Next day's Close price (shifted by one day)  
- Missing values due to shifting are removed.

### 3. Train-Test Split
The dataset is split into training and testing sets (typically 80% train, 20% test) while keeping the time order intact (no shuffling).

### 4. Model Training
A **Linear Regression** model is trained on the training data to learn the relationship between the input features and the next day's closing price.

### 5. Predictions
The trained model predicts the next day's closing prices on the test set.

### 6. Evaluation
Model performance is evaluated using:
- **Mean Squared Error (MSE)**
- **R² Score**

### 7. Visualization
1. **Actual vs Predicted Closing Prices**  
   A line chart to compare the model's predicted prices against actual closing prices over time.
2. **Open vs Close Prices**  
   A line chart showing trends of opening and closing prices.
3. **High vs Low Prices**  
   A line chart showing daily high and low price fluctuations.

---

## Observations
- The Linear Regression model generally follows the trend of Tesla's closing prices.  
- Sudden spikes or drops may not be captured perfectly due to the simplicity of the model.  
- Advanced models like Random Forest or LSTM can be used for improved short-term prediction accuracy.

---

## Skills Demonstrated
- Time series data handling
- Regression modeling (Linear Regression)
- Data fetching via APIs (`yfinance`)
- Data visualization with Matplotlib & Seaborn
- Model evaluation using MSE and R²

---

## Notes
- The workflow can be adapted to other stocks by changing the ticker symbol.  
- Ensure the `Date` column exists in the dataset for visualization purposes.  
- This project focuses on **short-term predictions** and may not reflect long-term trends.
