# Moroccan Car Price Prediction

## Overview

An end-to-end machine learning solution for predicting vehicle prices in the Moroccan automotive market. This project implements a complete data engineering pipeline—from web scraping and ETL processes to model training and deployment—delivering real-time price predictions through an interactive web application.

## Table of Contents

- [Architecture](#architecture)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Data Pipeline](#data-pipeline)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Model Performance](#model-performance)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Architecture

```
Data Source (Avito) → Web Scraping → Data Storage → EDA & Preprocessing → ML Model → Web Application
```

This project follows a standard data engineering workflow:
1. **Data Ingestion**: Automated web scraping using Selenium
2. **Data Storage**: CSV-based data lake for raw and processed data
3. **Data Transformation**: ETL processes with Pandas for cleaning and feature engineering
4. **Model Development**: Scikit-learn pipeline for training and validation
5. **Model Deployment**: Streamlit-based web application for inference

## Features

- **Automated Data Collection**: Dynamic web scraping from Avito marketplace with configurable pagination
- **Robust ETL Pipeline**: Data cleaning, validation, and transformation processes
- **Feature Engineering**: Extraction and encoding of categorical and numerical features
- **ML Model**: Regression model for price prediction with serialization support
- **Interactive UI**: User-friendly Streamlit interface for real-time predictions
- **Scalable Architecture**: Modular design supporting easy maintenance and updates

## Technology Stack

### Data Engineering & Processing
- **Python 3.x**: Core programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing

### Web Scraping & Automation
- **Selenium WebDriver**: Browser automation for dynamic content scraping
- **BeautifulSoup4**: HTML parsing and data extraction
- **WebDriver Manager**: Automated driver management

### Machine Learning
- **Scikit-learn**: Model training, evaluation, and preprocessing
- **Pickle**: Model serialization and persistence

### Application & Deployment
- **Streamlit**: Web application framework
- **Requests**: HTTP library for API calls

## Data Pipeline

### 1. Data Extraction
```python
# Automated scraping from Avito marketplace
- Target: Vehicle listings with detailed specifications
- Method: Selenium + BeautifulSoup for dynamic content handling
- Output: Raw data stored in data.csv
```

### 2. Data Transformation
```python
# Feature extraction and engineering
- Cleaning: Handle missing values, outliers, and data type conversions
- Encoding: Categorical variable transformation (One-Hot Encoding)
- Features: Fiscal Power, Model Year, Mileage, Fuel Type, Transmission, Condition
```

### 3. Model Training & Evaluation
```python
# Supervised learning for price prediction
- Algorithm: Regression (configured in analyse.ipynb)
- Validation: Train-test split with performance metrics
- Persistence: Serialized model using pickle
```

## Installation

### Prerequisites
- Python 3.8 or higher
- Chrome/Chromium browser
- pip package manager

### Setup

1. **Clone the repository**
```bash
git clone <repository-url>
cd "Moroccan Car Price Prediction"
```

2. **Create a virtual environment** (recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirement.txt
```

4. **Verify installation**
```bash
python -c "import streamlit; import selenium; import sklearn; print('All dependencies installed successfully')"
```

## Usage

### Running the Complete Pipeline

#### 1. Data Collection (Optional - if updating dataset)
```bash
python scrap.py
```
This will scrape vehicle data from Avito and update `data.csv`.

#### 2. Data Analysis & Model Training
Open and execute `analyse.ipynb` in Jupyter Notebook or JupyterLab:
```bash
jupyter notebook analyse.ipynb
```
This notebook contains:
- Exploratory Data Analysis (EDA)
- Data preprocessing and feature engineering
- Model training and evaluation
- Model serialization

#### 3. Launch the Web Application
```bash
streamlit run app.py
```
Access the application at `http://localhost:8501`

### Using the Prediction Interface

1. Enter the vehicle name or model
2. Provide vehicle characteristics:
   - Fiscal Power (Puissance fiscale)
   - Model Year (Année Modèle)
   - Mileage (Kilométrage)
   - Condition (État)
   - Fuel Type (Carburant)
   - Transmission (Boîte de vitesses)
   - First Owner Status (Première main)
3. Click "Calculate" to get the predicted price

## Project Structure

```
Moroccan Car Price Prediction/
│
├── analyse.ipynb          # EDA, preprocessing, and model training notebook
├── app.py                 # Streamlit web application
├── scrap.py               # Web scraping module for data collection
├── data.csv               # Dataset (raw/processed vehicle data)
├── requirement.txt        # Project dependencies
├── README.md              # Project documentation
└── model.pkl              # Serialized ML model (generated after training)
```

## Model Performance

The model's performance metrics are documented in `analyse.ipynb`. Key evaluation criteria include:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

*(Note: Update this section with actual metrics after model training)*

## Future Enhancements

- [ ] Implement automated data pipeline scheduling (Apache Airflow)
- [ ] Add data quality monitoring and validation
- [ ] Integrate cloud storage (AWS S3/Azure Blob Storage)
- [ ] Implement model versioning and experiment tracking (MLflow)
- [ ] Deploy to cloud platforms (AWS/Azure/GCP)
- [ ] Add API endpoints for programmatic access
- [ ] Implement real-time price tracking and alerts
- [ ] Expand to additional vehicle marketplaces
- [ ] Add advanced feature engineering (NLP for descriptions)
- [ ] Implement ensemble methods for improved accuracy

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is available for educational and demonstration purposes. Please ensure compliance with Avito's Terms of Service and robots.txt when scraping data.

## Contact

**Soukaina El Hadifi**
- Email: medsaberelguelta@gmail.com
- LinkedIn: [Add your LinkedIn profile]
- GitHub: [Add your GitHub profile]

---

*Built with Python, Streamlit, and Scikit-learn 
