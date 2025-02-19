# Optimizing Used Car Inventory with Machine Learning

This repository contains a practical machine learning project designed to identify key drivers of used car prices, enabling dealers to fine-tune their inventory and pricing strategies. The project follows the CRISP-DM methodology and leverages advanced data preparation and modeling techniques to deliver actionable insights.

## Project Overview

- **Objective:**  
  Identify the primary factors affecting used car prices and build predictive models to optimize inventory pricing.

- **Dataset:**  
  A Kaggle dataset (`vehicles.csv`) containing over 400K entries with features such as `year`, `odometer`, `manufacturer`, and more.

- **Approach:**  
  1. **Data Preparation:**  
     - **Outlier Detection & Removal:** Used IQR-based methods to eliminate extreme values.  
     - **Missing Value Imputation:** Applied median and mode imputation strategies.  
     - **Feature Engineering:** Created new features (e.g., `age`, `price_per_mile`) and transformed existing ones (e.g., log transformation of `odometer`).

  2. **Modeling:**  
     - Built regression models using **Ridge** and **Lasso** regression.  
     - Employed **GridSearchCV** and **RandomizedSearchCV** for hyperparameter tuning.
     - Evaluated models using Mean Squared Error (MSE) and Mean Absolute Error (MAE).

## Key Results

- **Ridge Regression:**  
  - Best Parameters (GridSearchCV): `{'alpha': 1, 'max_iter': None, 'solver': 'auto'}`
  - Test MSE: ~4.46e-06  
  - Test MAE: ~0.00161

- **Lasso Regression:**  
  - Best Parameters (GridSearchCV): `{'alpha': 0.001, 'max_iter': 1000, 'selection': 'cyclic', 'tol': 0.0001}`
  - Test MSE: ~5.72e-06  
  - Test MAE: ~0.00199

Based on these metrics, Ridge Regression slightly outperformed Lasso, suggesting that all features contribute valuable information in predicting car prices.

## How to Use This Repository

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/pabloriveraw/practical_application_II.git
   cd practical_application_II
   ```

2. **Install Dependencies:**

   Ensure you have Python 3.7+ installed. Then, install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

3. **Prepare the Data:**

   - Place the `vehicles.csv` file in the `data/` directory.
   - Run the data preparation script to clean and transform the data:

     ```bash
     python data_preparation.py
     ```

4. **Train and Evaluate Models:**

   - Use the modeling script to train Ridge and Lasso regression models, perform hyperparameter tuning, and evaluate performance:

     ```bash
     python modeling.py
     ```

5. **Dashboard and Daily Operations:**

   - The models can be integrated into a dashboard for day-to-day inventory and pricing adjustments.
   - Use the model predictions to compare against current listing prices and make informed decisions about price adjustments and inventory management.

## Actionable Insights for Dealers

- **Daily Inventory Checks:**  
  Run the model on your current inventory every morning to compare predicted vs. listed prices. Adjust prices or run promotions accordingly.

- **Dynamic Pricing:**  
  Use the predicted pricing ranges (e.g., within ±5% of the model’s prediction) as a guide for setting competitive prices.

- **Inventory Optimization:**  
  Identify high-potential vehicles (low mileage, favorable age) to prioritize in marketing and acquisition.

- **Continuous Improvement:**  
  Regularly update your data and re-train models to keep pace with market changes, ensuring that your pricing strategy remains optimal.

## Contributing

Contributions and suggestions are welcome! Feel free to open issues or submit pull requests.

## License

This project is licensed under the [MIT License](LICENSE).

---

By integrating these tools into your daily operations, you can transform raw data into actionable strategies that optimize your used car inventory and boost profitability.

Happy optimizing!

---
