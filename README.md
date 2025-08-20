# WindCast-AI: Wind Energy Forecasting

WindCast-AI predicts wind energy generation using **LSTM** and **BiLSTM** deep learning models.  
It combines meteorological data (via the Open-Meteo API) and historical wind datasets to forecast output.

---

##  Project Structure
```
Artefact/
├── code.ipynb
├── weather_data.csv              
├── time_series_60min_singleindex.csv  
├── london_nwp_data.csv           # Fetched automatically from API
├── README.md
└── .gitignore
```

---

##  Datasets
- `weather_data.csv` (https://drive.google.com/file/d/1hTtM-adCd2oszPDFQ2OF_MvwoJNbfBHd/view?usp=drive_link)  
- `time_series_60min_singleindex.csv` (https://drive.google.com/file/d/1B2IcAIKTiAhacSn3ve_23h5IrbsCmgmZ/view?usp=drive_link)  

👉 Download them from Drive and place in the same folder as `code.ipynb`.  
Since they exceed GitHub’s 100MB file limit, they are not stored directly in this repository.  

For quick testing, you can also create smaller **sample CSVs** with fewer rows.  

---

## ⚙️ Prerequisites
- **Visual Studio Code** (or Jupyter Notebook)  
- **Python 3.7 – 3.12**  
  - Check version:  
    ```bash
    python --version
    ```
- Internet access (required to fetch NWP data via Open-Meteo API)

---

##  Running the Script
1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn tensorflow shap requests
   ```
2. Open `code.ipynb` in **Jupyter Notebook** or **VS Code**.  
3. Run each cell step by step:
   - Import libraries  
   - Fetch/load datasets (including API call for `london_nwp_data.csv`)  
   - Preprocess data: merge, clean, feature engineering  
   - Train **LSTM** and **BiLSTM** models  
   - Evaluate and visualize results  

---

##  Outputs
The notebook generates:
- Evaluation table (R², RMSE, MAE)  
- Actual vs. Predicted line and scatter plots  
- SHAP explainability plots showing feature importance  

These outputs help measure model accuracy and interpret which features drive predictions.

---

##  Troubleshooting
- Make sure all files are in the same directory as `code.ipynb`.  
- Verify all required packages are installed.  
- If the API call fails, check your internet connection and retry.  

### Windows TensorFlow Install Error
If you see:
```
ERROR: Could not install packages due to an OSError...
```
It may be due to **Windows Long Path** not enabled.

Fix:
1. Press **Win + R**, type `regedit`.  
2. Navigate to:  
   `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem`  
3. Add or set:  
   - Name: `LongPathsEnabled`  
   - Type: `REG_DWORD`  
   - Value: `1`  
4. Restart your computer.  
5. Re-run:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn tensorflow shap requests
   ```

---

##
Developed by **Akash C.**
