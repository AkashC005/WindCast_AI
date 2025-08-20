# WindCast-AI: Predicting Wind Energy Outputs Using Weather Forecasting

Short, practical project for forecasting wind energy generation from weather features. Built around a Jupyter notebook and reproducible data pipeline. Ideal as a reference or starting point for time-series regression with real-world datasets.

---

## 📦 Project Contents

```
Artefact/
├── code.ipynb                      # Main analysis & modeling notebook
├── readme.md                       # (this file)
├── weather_data.csv                # LARGE – hosted on Drive (see links)
├── time_series_60min_singleindex.csv  # LARGE – hosted on Drive (see links)
└── .gitignore
```

> The large CSVs are **not** committed to GitHub due to the 100 MB limit. See the “Data” section for download links and light “sample” files.

---

## 🧠 What this project does

- Loads time-aligned weather signals (e.g., wind speed, direction, temperature, pressure).
- Engineers lag/rolling features for time-series models.
- Trains and evaluates regression models to predict wind energy output.
- Visualizes predictions vs. actuals and basic error metrics.

---

## 🗂️ Data

**Full datasets (hosted on Google Drive):**

- `weather_data.csv` → [Add your Drive link here]
- `time_series_60min_singleindex.csv` → [Add your Drive link here]

Download both and place them in the project root (same folder as `code.ipynb`).

**Optional: add small “sample” files for quick testing**

If you want the repo to include tiny samples (recommended), create them locally:

```bash
# macOS/Linux
head -n 500 weather_data.csv > weather_data.sample.csv
head -n 500 time_series_60min_singleindex.csv > time_series_60min_singleindex.sample.csv
```

Then update the notebook to use the `*.sample.csv` files by default (with a switch to full data when available).

---

## 🚀 Getting Started

### 1) Clone the repo

```bash
git clone https://github.com/<your-username>/WindCast-AI.git
cd WindCast-AI
```

### 2) Create & activate a virtual environment (recommended)

```bash
# macOS/Linux
python3 -m venv .venv
source .venv/bin/activate

# Windows (PowerShell)
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 3) Install dependencies

If you’re not using a `requirements.txt`, install common packages:

```bash
pip install -U pip
pip install pandas numpy scikit-learn matplotlib jupyter
# Optional (uncomment as needed):
# pip install xgboost lightgbm seaborn catboost
```

> If you have a `requirements.txt`, just do:  
> `pip install -r requirements.txt`

### 4) Start Jupyter

```bash
jupyter notebook
```

Open `code.ipynb` from the Jupyter UI.

---

## ⚙️ Configuration

In the first cells of `code.ipynb`, set paths to the CSVs:

```python
WEATHER_PATH = "weather_data.csv"  # or "weather_data.sample.csv"
SERIES_PATH  = "time_series_60min_singleindex.csv"  # or ".sample.csv"
```

If you’re working with samples by default, point to `*.sample.csv` and document in the notebook how to flip to full data.

---

## 🧪 Workflow (suggested)

1. **EDA** – inspect distributions, correlations, missingness.
2. **Feature Engineering** – create lags/rolling means, time-of-day, day-of-week, wind-vector components (sin/cos of direction), etc.
3. **Split** – time-based train/validation/test split.
4. **Model** – start with baseline (e.g., Linear/ElasticNet), try tree-based (RandomForest, XGBoost/LightGBM).
5. **Evaluate** – MAE, RMSE, MAPE; plots of actual vs. predicted; residual checks.
6. **Iterate** – tune features/hyperparams; compare models.

---

## 📈 Metrics (examples to compute)

- **MAE** (Mean Absolute Error)  
- **RMSE** (Root Mean Squared Error)  
- **R²** (Coefficient of Determination)  
- **MAPE** (Mean Absolute Percentage Error) – if values are strictly positive

Add nice plots (actual vs predicted over time; error distribution). Document results in the notebook.

---

## 🤝 Reproducibility Tips

- Fix a random seed for comparability.
- Use time-aware cross-validation (e.g., `TimeSeriesSplit` in scikit-learn).
- Log your environment:
  ```bash
  pip freeze > requirements.txt
  ```
- Consider exporting trained model artifacts (e.g., `joblib.dump`) with a note on how to load for inference.

---

## 📤 Sharing the large data

Because GitHub blocks files > 100 MB, this repo links to large CSVs on Google Drive:

1. Upload the files to Drive.  
2. Set sharing to “Anyone with the link – Viewer”.  
3. Paste the links above.  
4. (Optional) Also publish a **release** on GitHub and attach the files as release assets.

> If you prefer keeping large files in-repo, use **Git LFS** (be mindful of quotas):  
> ```
> git lfs install
> git lfs track "*.csv"
> git add .gitattributes
> git commit -m "Track CSVs via LFS"
> git push
> ```

---

## 🗺️ Roadmap (ideas)

- Realtime/rolling inference script (`predict.py`).
- Model comparison dashboard (e.g., Streamlit).
- Hyperparameter search (Optuna or scikit-learn `RandomizedSearchCV`).
- Feature importance and SHAP explanations.
- Automated data quality checks.

---

## 📜 License

Add a license of your choice (MIT is common for open projects). Create a `LICENSE` file:

- [Choose a License](https://choosealicense.com)

---

## ✍️ Citation

If you use this work in academic writing:

```
Akash C. (2025). WindCast-AI: Predicting Wind Energy Outputs Using Weather Forecasting. GitHub repository.
```

---

## 🙌 Acknowledgments

- scikit-learn, pandas, numpy, matplotlib
- Any data providers or sources you used

---

### Maintainer

- **Akash C.** – [your GitHub profile link]

---

### Quick Links

- 📄 Notebook: `code.ipynb`  
- 📊 Data: [Drive links here]  
- 🧪 Sample data: `*.sample.csv` (optional)
