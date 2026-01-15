# 🌍 Spatio-Temporal Regression Modeling of Global Earthquake Magnitudes

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18243337.svg)](https://doi.org/10.5281/zenodo.18243337)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

## 📌 Overview

Predicting earthquake magnitude is a critical challenge in seismology that enhances disaster risk evaluation and mitigation strategies. This research develops a spatio-temporal regression model to predict the magnitude of major earthquakes globally using a comprehensive historical dataset spanning **200 years (1826–2026)** with **102,799 earthquake records**.

The project evaluates four ensemble machine learning models to identify the most effective approach for magnitude estimation, with **Random Forest** emerging as the top performer.

---

## 📖 Abstract

This study presents a spatio-temporal regression framework for earthquake magnitude prediction based on historical seismic data. Key predictors include:

- **Spatial features**: Latitude, longitude, depth
- **Temporal features**: Year, month, day, hour, weekday, seasonal patterns, day/night variance
- **Auxiliary seismic parameters**: RMS, azimuthal gap
- **Tectonic zone classification**: Heuristically determined regional categorization

Four ensemble machine learning models were evaluated:
- 🌲 **Random Forest**
- ⚡ **LightGBM**
- 🚀 **XGBoost**
- 🐱 **CatBoost**

All models were trained using a chronological 80/20 train-test split to preserve temporal integrity.

---

## 🏆 Results

### 🔹 Model Performance (Test Set)

| Model | MAE | RMSE | R² |
|-------|-----|------|-----|
| 🌲 **Random Forest** | **0.2377** | **0.3472** | **0.2635** |
| ⚡ LightGBM | - | - | - |
| 🚀 XGBoost | - | - | - |
| 🐱 CatBoost | - | - | - |

✅ **Best Model**: Random Forest achieved the lowest error metrics and highest predictive power.

### 🔹 Key Findings

- **Top predictive features**: Depth, geographic position (latitude/longitude), and long-term temporal characteristics
- **Consistent with seismological patterns**: Feature importance aligns with established domain knowledge
- **Moderate predictive performance**: Highlights systematic constraints including historical data biases and lack of explicit geophysical constraints

---

## 📂 Dataset

- **Source**: Global earthquake catalog (1826–2026)
- **Records**: 102,799 earthquakes
- **Temporal span**: 200 years
- **Features**:
  - **Spatial**: Latitude, Longitude, Depth
  - **Temporal**: Year, Month, Day, Hour, Weekday, Seasonal indicators, Day/Night classification
  - **Seismic**: RMS (Root Mean Square), Azimuthal Gap
  - **Regional**: Tectonic zone classification

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Temporal feature engineering (seasonality, cyclical patterns)
- Spatial encoding of geographic coordinates
- Tectonic zone classification based on geological domain knowledge
- Handling missing values and outliers

### 2. Feature Engineering
- Cyclical encoding of temporal features (month, hour, day of week)
- Binary classification of day/night periods
- Depth normalization and scaling
- Interaction features between spatial and temporal dimensions

### 3. Model Training
- Chronological train-test split (80/20) to maintain temporal integrity
- Cross-validation on training set
- Hyperparameter tuning via grid search/random search
- Ensemble methods: Random Forest, LightGBM, XGBoost, CatBoost

### 4. Evaluation
- **Metrics**: Mean Absolute Error (MAE), Root Mean Square Error (RMSE), R² Score
- Feature importance analysis
- Model interpretability assessment

---

## 🛠️ Tech Stack

**Language**: Python 3.9+

**Libraries**:
- `pandas` - Data manipulation
- `numpy` - Numerical computing
- `scikit-learn` - Machine learning models and preprocessing
- `xgboost` - Gradient boosting
- `lightgbm` - Light gradient boosting
- `catboost` - Categorical boosting
- `matplotlib` - Data visualization
- `seaborn` - Statistical plotting
- `plotly` - Interactive visualizations

---

## 📂 Repository Structure

```
├── data/
│   └── earthquake_catalog.csv          # Historical earthquake dataset (1826-2026)
├── notebooks/
│   └── earthquake_analysis.ipynb       # Jupyter notebook with full analysis
├── src/
│   ├── preprocessing.py                # Data cleaning and feature engineering
│   ├── models.py                       # Model implementations
│   └── evaluation.py                   # Evaluation metrics and visualization
├── results/
│   ├── model_performance.csv           # Performance metrics for all models
│   └── visualizations/                 # Generated plots and figures
├── requirements.txt                    # Python dependencies
├── README.md                           # Project documentation
└── LICENSE                             # Creative Commons BY 4.0 License
```

---

## ▶️ How to Run

### 🔹 Option 1: Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/)
2. Upload the `.ipynb` file from the `notebooks/` directory
3. Install dependencies:
   ```python
   !pip install -r requirements.txt
   ```
4. Run cells sequentially

### 🔹 Option 2: Run Locally

1. **Clone the repository**:
   ```bash
   git clone https://github.com/YourUsername/earthquake-magnitude-prediction.git
   cd earthquake-magnitude-prediction
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

4. Open `notebooks/earthquake_analysis.ipynb` and execute cells

---

## 📈 Visualizations

The project includes comprehensive visualizations:

- 📊 Temporal distribution of earthquakes over 200 years
- 🗺️ Geographic distribution of seismic events
- 🔥 Feature correlation heatmap
- 📉 Model performance comparison
- 🌲 Feature importance rankings (Random Forest)
- 📈 Learning curves for all models
- 🎯 Actual vs. Predicted magnitude scatter plots
- 📊 Residual analysis

---

## ✨ Key Contributions

1. **Comprehensive historical analysis**: 200-year dataset spanning 1826–2026
2. **Domain-driven feature engineering**: Incorporation of seismological knowledge into model design
3. **Reproducible ML pipeline**: Standardized methodology for earthquake magnitude estimation
4. **Ensemble model comparison**: Systematic evaluation of four state-of-the-art algorithms
5. **Temporal integrity**: Chronological splitting to avoid data leakage

---

## 🔮 Future Work

- Incorporate **real-time seismic data streams** for dynamic prediction
- Develop **deep learning models** (LSTM, Transformers) for temporal sequence modeling
- Add **explicit geophysical constraints** (plate tectonics, fault line proximity)
- Address **historical data biases** through advanced imputation techniques
- Implement **uncertainty quantification** for prediction intervals
- Create **interactive web dashboard** for real-time magnitude forecasting

---

## 📚 Citation

If you use this work in your research, please cite:

```bibtex
@article{abbas2026earthquake,
  title={Spatio-Temporal Regression Modeling of Global Earthquake Magnitudes: A 200-Year Historical Analysis and Predictive Evaluation (1826–2026)},
  author={Abbas, Agha Wafa},
  journal={Zenodo},
  year={2026},
  doi={10.5281/zenodo.18243337},
  url={https://doi.org/10.5281/zenodo.18243337}
}
```

---

## 👨‍💻 Author

**Agha Wafa Abbas**

- 🎓 Lecturer, School of Computing, University of Portsmouth, Winston Churchill Ave, Southsea, Portsmouth PO1 2UP, United Kingdom
- 🎓 Lecturer, School of Computing, Arden University, Coventry, United Kingdom
- 🎓 Lecturer, School of Computing, Pearson, London, United Kingdom
- 🎓 Lecturer, School of Computing, IVY College of Management Sciences, Lahore, Pakistan

📧 **Emails**: 
- [agha.wafa@port.ac.uk](mailto:agha.wafa@port.ac.uk)
- [awabbas@arden.ac.uk](mailto:awabbas@arden.ac.uk)
- [wafa.abbas.lhr@rootsivy.edu.pk](mailto:wafa.abbas.lhr@rootsivy.edu.pk)

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **Creative Commons Attribution 4.0 International License** - see the [LICENSE](LICENSE) file for details.

The Creative Commons Attribution license allows redistribution and reuse of the licensed work on the condition that the creator is appropriately credited.

---

## 🙏 Acknowledgments

- Global seismological data providers
- Open-source machine learning community
- University of Portsmouth, Arden University, Pearson, and Roots IVY College

---

## 📊 Keywords

`Earthquake magnitude prediction` · `Spatio-temporal regression` · `Machine learning ensembles` · `Historical seismic catalog` · `Tectonic zone classification` · `Random Forest` · `Predictive seismology` · `Disaster risk assessment`

---

<p align="center">
  Made with ❤️ for advancing seismological research
</p>
