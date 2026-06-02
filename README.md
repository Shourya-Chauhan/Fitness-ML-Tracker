# Fitness ML Tracker

A comprehensive end-to-end platform for processing real-world, noisy time-series biometrics captured directly from personal device telemetry, combined with intelligent machine learning for predictive health insights.

## 🎯 Core Highlight

**Real-World Biometric Processing**: This project specializes in ingesting, cleaning, and transforming raw, noisy time-series data from personal health devices (smartwatches, fitness trackers, health apps) into meaningful predictive signals. The pipeline handles the inherent challenges of real-world data—missing values, sensor drift, sampling irregularities, and temporal inconsistencies—to extract reliable features for weight prediction and health trend analysis.

## 📂 Project Structure

```
fitness-ml-tracker/
├── src/                              # Application layer
│   └── app.py                        # Streamlit dashboard for real-time monitoring
│
├── scripts/                          # Data processing & analysis
│   ├── build_features.py            # Feature engineering from raw telemetry
│   └── Visualized_changes.py        # Visualization utilities & trend analysis
│
├── data/
│   ├── raw/                         # Raw device telemetry
│   │   ├── health_wide_full.csv     # Complete multi-source biometric data
│   │   ├── health_modeling_ready.csv # Cleaned, validated dataset
│   │   └── cleaning_data.py         # Data cleaning pipeline
│   └── processed/                   # Feature-engineered data
│       └── health_features_engineered.csv
│
├── model/                            # ML artifacts & training
│   ├── artifacts/
│   │   └── weight_predictor.joblib  # Trained predictive model
│   ├── train_model.py               # Model training pipeline
│   └── health_modeling_ready.csv    # Training data snapshot
│
├── notebooks/                        # Exploratory analysis (if any)
├── config/                           # Configuration files
├── requirements.txt                  # Python dependencies
└── README.md                         # This file
```

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip

### Installation

```bash
pip install -r requirements.txt
```

### Usage

**Launch the Dashboard**
```bash
streamlit run src/app.py
```
Opens an interactive web interface for real-time biometric monitoring and trend analysis.

**Run the Feature Engineering Pipeline**
```bash
python scripts/build_features.py
```
Processes raw telemetry data and derives predictive features.

**Generate Visualizations**
```bash
python scripts/Visualized_changes.py
```
Produces temporal analysis charts and trend visualizations.

## 📊 Core Features

### 1. **Time-Series Biometric Processing**
- End-to-end ingestion of personal device telemetry (calories, basal energy, active energy, weight, etc.)
- Robust data cleaning and imputation strategies for real-world noise
- Temporal alignment and feature engineering from raw sensor streams
- Handling of missing values, outliers, and sensor inconsistencies

### 2. **Intelligent Feature Engineering**
- Automated feature extraction pipeline (`build_features.py`)
- Derivation of meaningful signals from noisy telemetry
- 7-day rolling averages and statistical transformations
- Energy balance calculations and caloric deficit metrics

### 3. **Predictive Modeling**
- Machine learning model for weight prediction based on energy balance
- Trained on real biometric data with temporal dependencies
- Joblib-serialized model artifacts for production deployment

### 4. **Interactive Dashboard**
- Real-time visualization of health metrics and trends
- Streamlit-based web interface for easy exploration
- Plotly interactive charts for temporal analysis
- Calorie, macronutrient, and weight tracking

## 🔄 Data Pipeline

### Ingestion → Cleaning → Feature Engineering → Prediction

The project demonstrates a complete real-world ML pipeline:

1. **Raw Telemetry Input**: Multi-source biometric data from personal devices
   - Caloric intake and expenditure
   - Basal and active energy metrics
   - Body weight measurements
   - Temporal gaps and inconsistencies

2. **Data Cleaning & Preparation** (`data/raw/cleaning_data.py`)
   - Temporal sorting and alignment
   - Missing value imputation (linear interpolation for continuous metrics)
   - Outlier detection and handling
   - Data validation and integrity checks

3. **Feature Extraction** (`scripts/build_features.py`)
   - Rolling window statistics (7-day averages)
   - Net calorie balance calculations
   - Thermodynamic representations
   - Mathematical signals for ML ingestion

4. **Predictive Inference** (`model/weight_predictor.joblib`)
   - Weight trajectory forecasting
   - Energy balance correlation analysis
   - Model evaluation and backtesting

5. **Visualization & Dashboarding** (`scripts/Visualized_changes.py`, `src/app.py`)
   - Interactive trend analysis
   - Real-time metric tracking
   - Decision support visualization

## 💡 Key Technical Insights

### Handling Real-World Biometric Noise
- **Data Sparsity**: Devices may miss readings or have irregular sampling intervals
- **Sensor Drift**: Systematic biases in scale measurements or energy calculations
- **Multi-Source Heterogeneity**: Aggregating data from multiple devices with different calibrations
- **Temporal Gaps**: Days or weeks without data entries
- **Solution**: Interpolation strategies, rolling window aggregation, and temporal alignment

### Feature Engineering for Predictive Power
- **Caloric Balance**: Net daily energy (intake - expenditure)
- **Rolling Averages**: Smoothing noise with 7-day windows
- **Lag Features**: Historical patterns to capture momentum
- **Statistical Moments**: Mean, variance, skewness of telemetry signals

### Production Considerations
- Model serialization with Joblib for reproducibility
- Scalability to multi-user scenarios
- Real-time dashboard updates
- Extensibility to new data sources

## 🎓 Learning Value

This project demonstrates:
✓ Complete data science workflow: ETL → Feature Engineering → Modeling → Visualization  
✓ Practical challenges in real-world time-series analysis  
✓ Python best practices in ML pipelines  
✓ Interactive visualization and dashboard development  
✓ Production-ready code organization
