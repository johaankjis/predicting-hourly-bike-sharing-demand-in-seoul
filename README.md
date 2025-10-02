# Predicting Hourly Bike Sharing Demand in Seoul

This project involves predicting the hourly demand for bike rentals in Seoul, South Korea, using machine learning techniques. The analysis explores various models including Linear Regression and Neural Networks to forecast bike rental demand based on weather conditions, temporal information, and other environmental factors.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Models and Methodology](#models-and-methodology)
- [Results](#results)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## Overview

Bike-sharing systems have become increasingly popular in urban areas as a sustainable and convenient transportation option. Accurate prediction of bike rental demand helps optimize bike distribution, maintenance scheduling, and overall system efficiency. This project analyzes historical bike rental data from Seoul's public bike-sharing system and develops predictive models to forecast hourly demand.

The goal is to predict the number of bikes rented per hour based on various environmental and temporal factors, enabling better resource allocation and improved service quality.

## Dataset

The dataset (`SeoulBikeData.csv`) contains hourly bike rental data for Seoul's public bike-sharing system with **8,760 records** (approximately one year of hourly data).

### Data Source
The data includes information from December 1, 2017, onwards, capturing various weather conditions and temporal patterns.

### Dataset Attributes
The dataset includes the following 14 attributes:

| Feature | Description | Type |
|---------|-------------|------|
| Date | Date of observation (DD/MM/YYYY) | Temporal |
| Rented Bike Count | Count of bikes rented at each hour (target variable) | Numerical |
| Hour | Hour of the day (0-23) | Temporal |
| Temperature(°C) | Temperature in Celsius | Numerical |
| Humidity(%) | Relative humidity percentage | Numerical |
| Wind speed (m/s) | Wind speed in meters per second | Numerical |
| Visibility (10m) | Visibility in units of 10 meters | Numerical |
| Dew point temperature(°C) | Dew point temperature | Numerical |
| Solar Radiation (MJ/m²) | Solar radiation in MJ/m² | Numerical |
| Rainfall(mm) | Rainfall amount in millimeters | Numerical |
| Snowfall (cm) | Snowfall amount in centimeters | Numerical |
| Seasons | Season of the year (Winter, Spring, Summer, Autumn) | Categorical |
| Holiday | Whether the day is a holiday or not | Categorical |
| Functioning Day | Whether the bike rental system is functioning (Yes/No) | Categorical |

## Features

This project implements the following features:

- **Data Preprocessing**: Data cleaning, feature engineering, and normalization
- **Exploratory Data Analysis**: Visualization of data distributions and correlations
- **Multiple Regression Models**:
  - Simple Linear Regression (temperature-based)
  - Multiple Linear Regression (all features)
  - Neural Network models with TensorFlow/Keras
- **Model Evaluation**: Performance comparison using R² score and Mean Squared Error (MSE)
- **Visualization**: Comprehensive plots showing predictions vs actual values and loss curves

## Installation

### Prerequisites
- Python 3.7 or higher
- pip package manager

### Setup

1. Clone the repository:
```bash
git clone https://github.com/johaankjis/predicting-hourly-bike-sharing-demand-in-seoul.git
cd predicting-hourly-bike-sharing-demand-in-seoul
```

2. Install required packages:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow imbalanced-learn jupyter
```

Or create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow imbalanced-learn jupyter
```

### Required Libraries
- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `matplotlib` - Data visualization
- `seaborn` - Statistical data visualization
- `scikit-learn` - Machine learning algorithms
- `tensorflow` - Deep learning framework
- `imbalanced-learn` - Handling imbalanced datasets
- `jupyter` - Interactive notebook environment

## Usage

### Running the Notebook

1. Start Jupyter Notebook:
```bash
jupyter notebook
```

2. Open `Bike_Sharing_in_Seoul,_South_Korea_Model.ipynb` in your browser

3. Run all cells sequentially to:
   - Load and preprocess the data
   - Perform exploratory data analysis
   - Train multiple models
   - Evaluate model performance
   - Visualize results

### Quick Start

The notebook follows this workflow:
1. **Data Loading**: Import the Seoul bike-sharing dataset
2. **Data Preprocessing**: Clean and prepare data for modeling
3. **Train-Validation-Test Split**: Split data into 60-20-20 ratio
4. **Model Training**: Train Linear Regression and Neural Network models
5. **Evaluation**: Compare model performance using MSE and R² metrics
6. **Visualization**: Plot predictions and analyze results

## Models and Methodology

### 1. Simple Linear Regression (Temperature-based)
- **Features**: Temperature only
- **Purpose**: Baseline model to understand temperature's impact on bike rentals
- **R² Score**: ~0.25

### 2. Multiple Linear Regression
- **Features**: All available features (temperature, humidity, rainfall, snowfall, solar radiation, hour)
- **Purpose**: Capture complex relationships between multiple variables
- **R² Score**: ~0.45

### 3. Neural Network Models (TensorFlow/Keras)
- **Architecture**: 
  - Input normalization layer
  - Multiple dense layers with activation functions
  - Output layer for regression
- **Optimizer**: Adam optimizer
- **Loss Function**: Mean Squared Error (MSE)
- **Features**: All available features
- **Purpose**: Capture non-linear relationships and complex patterns

### Data Preprocessing
- Removed less predictive features (wind, visibility, functioning day)
- Applied feature normalization for neural network models
- Split data randomly into training (60%), validation (20%), and test (20%) sets

## Results

The models achieved the following performance on the test set:

| Model | R² Score | MSE |
|-------|----------|-----|
| Simple Linear Regression (Temperature) | 0.252 | - |
| Multiple Linear Regression (All Features) | 0.448 | - |
| Neural Network | - | 96,563 |

### Key Findings
- Temperature is a significant predictor of bike rental demand
- Multiple features improve prediction accuracy substantially
- Neural networks can capture non-linear patterns in the data
- Seasonal variations and hour of day are important temporal factors

## Project Structure

```
predicting-hourly-bike-sharing-demand-in-seoul/
│
├── Bike_Sharing_in_Seoul,_South_Korea_Model.ipynb  # Main Jupyter notebook with analysis
├── SeoulBikeData.csv                                # Dataset file
└── README.md                                         # Project documentation
```

## Technologies Used

- **Python 3.x** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing and array operations
- **Matplotlib & Seaborn** - Data visualization
- **Scikit-learn** - Machine learning library for traditional ML algorithms
- **TensorFlow/Keras** - Deep learning framework for neural networks
- **Imbalanced-learn** - Tools for handling imbalanced datasets
- **Jupyter Notebook** - Interactive development environment

## Contributing

Contributions are welcome! Here's how you can contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add new feature'`)
5. Push to the branch (`git push origin feature/improvement`)
6. Create a Pull Request

### Areas for Improvement
- Add more sophisticated feature engineering
- Implement additional models (Random Forest, XGBoost, LSTM)
- Perform hyperparameter tuning
- Add cross-validation
- Create a web interface for predictions
- Add more comprehensive evaluation metrics

## License

This project is available for educational and research purposes. Please check with the repository owner for specific licensing terms.

## Acknowledgments

- Dataset sourced from Seoul's public bike-sharing system
- Inspired by the need for efficient urban transportation planning
- Thanks to the open-source community for the amazing tools and libraries

---

**Note**: This project is for educational and demonstration purposes. For production use, additional validation, testing, and optimization would be required.