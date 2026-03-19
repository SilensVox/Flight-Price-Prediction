# ✈️ Flight Price Prediction

A comprehensive data science project for predicting flight ticket prices using exploratory data analysis (EDA), feature engineering, and machine learning techniques.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Analysis Highlights](#analysis-highlights)
- [Technologies Used](#technologies-used)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project aims to predict flight ticket prices based on various factors such as airline, route, travel class, duration, booking time, and number of stops. The project includes extensive exploratory data analysis (EDA), outlier detection and treatment, feature engineering, machine learning model training, and comparative evaluation.

### Key Objectives:
- Understand the factors affecting flight prices
- Perform comprehensive exploratory data analysis
- Handle outliers and ensure data quality
- Engineer relevant features for better predictions
- Train and compare multiple regression models
- Save the best model and preprocessing pipeline for reuse

## ✨ Features

The analysis covers multiple aspects of flight pricing:

1. **Airline Analysis** - Price variations across different airlines
2. **Route Analysis** - Source and destination impact on pricing
3. **Stops Analysis** - Effect of layovers on ticket prices
4. **Class Analysis** - Business vs Economy price comparison
5. **Duration Analysis** - Relationship between flight duration and price
6. **Booking Time Analysis** - Optimal booking window identification
7. **Time-based Analysis** - Departure and arrival time effects
8. **Multivariate Analysis** - Complex interactions between features
9. **Model Benchmarking** - Comparative evaluation of regression models
10. **Model Persistence** - Saved model and preprocessing bundle for deployment

## 📊 Dataset

The dataset contains flight booking information with the following features:

### Categorical Features:
- **airline** - Name of the airline
- **flight** - Flight code
- **source_city** - Origin city
- **destination_city** - Destination city
- **departure_time** - Time of departure
- **arrival_time** - Time of arrival
- **stops** - Number of stops (non-stop, 1-stop, 2+-stops)
- **class** - Travel class (Economy, Business)

### Numerical Features:
- **duration** - Flight duration in hours
- **days_left** - Days remaining until departure
- **price** - Ticket price in INR (Target variable)

### Dataset Statistics:
- **Total Records**: ~300,000 flight bookings
- **Train Set**: 80% (240,122 samples)
- **Test Set**: 20% (60,031 samples)
- **Missing Values**: None
- **Data Quality**: Clean after preprocessing

## 📁 Project Structure

```
project-datascience/
│
├── Clean_Dataset.CSV                      # Original cleaned dataset
├── Flight_Data_After_EDA.csv             # Dataset after EDA processing
├── Flight_Data_Train_Clean.csv           # Training dataset (80%)
├── Flight_Data_Test_Clean.csv            # Testing dataset (20%)
├── Outlier_Before_After_Summary.csv      # Outlier analysis summary
├── Outlier_Detection_Report.csv          # Detailed outlier report
├── project_comprehensive_eda.ipynb       # Main Jupyter notebook with complete analysis
├── model_training_results/
│   ├── best_model.pkl                     # Best-performing trained model
│   ├── preprocessing_bundle.pkl           # Saved preprocessing objects
│   └── model_results.csv                  # Training and test metrics across models
│
└── Flight price prediiction/             # Virtual environment
    ├── Scripts/                          # Python executable and packages
    ├── Lib/                              # Installed libraries
    └── Include/                          # Header files
```

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Setup Steps

1. **Clone the repository**
```bash
git clone https://github.com/SilensVox/Flight-Price-Prediction.git
cd Flight-Price-Prediction
```

2. **Create and activate virtual environment**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python -m venv venv
source venv/bin/activate
```

3. **Install required packages**
```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
```

### Required Libraries:
```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
scipy>=1.10.0
scikit-learn>=1.3.0
jupyter>=1.0.0
```

## 💻 Usage

### Running the Analysis

1. **Start Jupyter Notebook**
```bash
jupyter notebook
```

2. **Open the main notebook**
   - Navigate to `project_comprehensive_eda.ipynb`
   - Run all cells sequentially

3. **Review outputs**
   - Visualizations are displayed inline
   - Processed datasets are saved automatically
   - Analysis reports are generated in CSV format

### Quick Start Example

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv("Clean_Dataset.CSV")

# Display basic information
print(df.info())
print(df.describe())

# Check for missing values
print(df.isnull().sum())
```

## 📈 Analysis Highlights

### 1. Data Preparation
- ✅ No missing values detected
- ✅ Duplicate records removed
- ✅ Feature types properly classified
- ✅ Train-test split (80-20) implemented

### 2. Exploratory Data Analysis
- **Price Distribution**: Right-skewed with outliers identified
- **Airline Impact**: Significant price variations across carriers
- **Route Analysis**: Popular routes command premium pricing
- **Class Effect**: Business class 2-3x more expensive than Economy
- **Duration Correlation**: Moderate positive correlation with price
- **Booking Time**: Last-minute bookings show price surge
- **Stops Impact**: Direct flights generally more expensive

### 3. Outlier Treatment
- **Method**: IQR (Interquartile Range) method
- **Approach**: Computed thresholds on training data only
- **Result**: Prevented data leakage, maintained model integrity
- **Reports**: Generated detailed before/after comparison

### 4. Feature Engineering
- Created `duration_category` (Short, Medium, Long, Very Long)
- Generated `urgency_ratio` = days_left / (duration + 1)
- Computed `total_time` = duration + days_left
- Applied Label Encoding to categorical variables
- Removed highly correlated features (threshold: 0.85)

### 5. Correlation Analysis
- Identified multicollinearity among features
- Removed redundant features
- Generated correlation heatmaps
- Optimized feature set for modeling

### 6. PCA Analysis
- Analyzed principal components
- Identified components explaining 95% variance
- Prepared for dimensionality reduction if needed
- Reserved for model optimization phase

### 7. Model Training and Evaluation
- Trained and compared 4 regression models:
   - Random Forest
   - Gradient Boosting
   - Ridge Regression
   - Linear Regression
- Evaluated using R², RMSE, MAE, MAPE, and Accuracy within 10%
- Ranked models by generalization performance on held-out test data
- Saved best model and preprocessing artifacts for downstream use

## 🛠️ Technologies Used

### Programming & Tools:
- **Python 3.x** - Core programming language
- **Jupyter Notebook** - Interactive development environment

### Data Processing:
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations

### Visualization:
- **Matplotlib** - Static plotting
- **Seaborn** - Statistical visualization

### Machine Learning:
- **Scikit-learn** - ML algorithms and preprocessing
- **SciPy** - Statistical analysis

## 📊 Results

### Key Findings:

1. **Most Influential Factors**:
   - Travel class (Business vs Economy)
   - Airline carrier
   - Booking time (days_left)
   - Flight duration
   - Number of stops

2. **Price Patterns**:
   - Business class: ₹15,000 - ₹50,000
   - Economy class: ₹3,000 - ₹15,000
   - Direct flights command 20-30% premium
   - Last-minute bookings (< 7 days): 40-50% price increase

3. **Optimal Booking Strategy**:
   - Book 30-60 days in advance for best prices
   - Avoid booking less than 7 days before departure
   - Early morning and late-night flights are cheaper

4. **Dataset Quality**:
   - Clean data with no missing values
   - Outliers properly handled
   - Features engineered for better predictive power
   - Successfully used for model training and comparison

### Model Performance Summary

Based on `model_training_results/model_results.csv`:

| Model | Test R² | Test RMSE | Test MAE | Test MAPE | Accuracy Within 10% |
|-------|---------|-----------|----------|-----------|----------------------|
| Random Forest | 0.9888 | 2397.93 | 923.21 | 6.24% | 81.08% |
| Gradient Boosting | 0.9573 | 4689.50 | 2782.01 | 20.43% | 37.41% |
| Ridge Regression | 0.9073 | 6911.65 | 4536.78 | 44.63% | 24.04% |
| Linear Regression | 0.9073 | 6911.65 | 4536.78 | 44.63% | 24.04% |

### Best Model
- **Selected Model**: Random Forest
- **Why it was selected**: Highest test R², lowest test errors, and strongest within-10% prediction accuracy

### Saved Artifacts
- `model_training_results/best_model.pkl`
- `model_training_results/preprocessing_bundle.pkl`
- `model_training_results/model_results.csv`

### Project Status:
✅ Data cleaned and preprocessed  
✅ Outliers detected and treated  
✅ Features engineered and encoded  
✅ Train-test split completed  
✅ Multiple models trained and evaluated  
✅ Best model and preprocessing pipeline saved

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Areas for Contribution:
- Machine learning model implementation (Random Forest, XGBoost, etc.)
- Hyperparameter tuning and optimization
- Feature engineering improvements
- Additional visualizations
- Model deployment pipeline
- Web application interface

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**SilensVox**
- GitHub: [@SilensVox](https://github.com/SilensVox)
- Repository: [Flight-Price-Prediction](https://github.com/SilensVox/Flight-Price-Prediction)

## 🙏 Acknowledgments

- Dataset sourced from flight booking platforms
- Inspired by real-world pricing optimization challenges
- Thanks to the open-source community for amazing tools and libraries



**⭐ If you find this project helpful, please consider giving it a star!**

---

*Last Updated: March 2026*
