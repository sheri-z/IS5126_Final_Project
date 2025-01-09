# Car Valuation Tool with Machine Learning

## Overview
This project addresses challenges in the second-hand car market in Singapore, where buyers and sellers face time-consuming processes and privacy concerns during car valuations. Our tool provides quick and indicative car valuations without requiring sensitive personal data.

## Features
- **Indicative Car Valuation:** Estimate car prices efficiently without sharing sensitive personal details.
- **Data-Driven Insights:** Leverages machine learning models trained on over 20,000 car listings scraped from [Sgcarmart](https://www.sgcarmart.com).
- **Streamlit Application:** A user-friendly interface for real-time predictions and interactive visualizations.

## Data Pipeline
### Data Collection
- **Source:** Sgcarmart, a leading car dealer website in Singapore.
- **Method:** Custom web scraping script to collect 20,000 listings.

### Data Cleaning & Preprocessing
- Standardized missing values and removed duplicates.
- Extracted key features from text columns (e.g., engine capacity, type).
- Enhanced dataset with OpenAI API for missing value imputation.

### Data Enhancement
- Added features using NLP techniques (e.g., sentiment scores, word counts).
- Created interaction terms to capture relationships between manufacturing year and fuel type.

## Exploratory Data Analysis (EDA)
- Analyzed correlations to identify multicollinearity and high-impact features.
- Investigated relationships between car price, COE price, manufacturing year, and fuel type.

## Machine Learning Pipeline
### Models Evaluated:
1. Random Forest
2. XGBoost
3. CatBoost
4. LightGBM
5. Gradient Boosting
6. Multi-Layer Perceptron (MLP)

### Final Model:
- **Voting Ensemble Model:** Combines XGBoost, Random Forest, and Stacking Model for superior accuracy.

### Performance Metrics:
- Root Mean Squared Error (RMSE): Best model achieved RMSE of ~31,800.
- R² Score: Top models explained ~94% of variance in car prices.

### Key Features:
- Deregister Value (log-transformed)
- Engine Capacity
- COE Price

## Deployment
### Streamlit Application
- Real-time predictions for car valuations.
- Displays interactive visualizations of inputs and outputs.



### Model Storage
- Saved models using `joblib` for efficient serialization.
- Includes:
  - Label encoders
  - Scaler for input standardization
  - Final Voting Ensemble Model

## Getting Started
### Prerequisites
- Python 3.9+
- Required libraries: `streamlit`, `scikit-learn`, `xgboost`, `lightgbm`, `catboost`, `joblib`, `nltk`, `spacy`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repository-link.git
   cd your-repository
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the application:
   ```bash
   streamlit run app.py
   ```

## Usage
- Enter car details (e.g., brand, model, year) into the Streamlit app.
- View estimated valuations and interactive charts.


## License
This project is licensed under the MIT License. See `LICENSE` for details.

## Acknowledgments
- [Sgcarmart](https://www.sgcarmart.com) for the data source.
- OpenAI API for data enhancement.
