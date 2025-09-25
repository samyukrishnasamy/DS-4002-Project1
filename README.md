# DS-4002 Project 1
Spam classification using Logistic Regression on the UC Irvine SMS Spam Collection dataset.
---

## Software & Platform
**Languages / Tools**
- Python 3.11
- Jupyter Notebook (exploration, cleaning, training, and evaluation)

**Key Packages**
- `pandas` – data loading, cleaning, and manipulation
- `scikit-learn` – model building, splitting, evaluation
- `imblearn` (imbalanced-learn) – RandomOverSampler for class imbalance
- `joblib` – saving and loading trained models
- `matplotlib` / `seaborn` – visualizations (class distribution, confusion matrix)

**Platform**
- Development: Jupyter Notebook on macOS
- Runs on macOS, Windows, or Linux (as long as packages are installed)

**Dependencies**
```bash
pip install -r requirements.txt



## Repository Structure


DS-4002-PROJECT1
├── DATA         # All datasets 
│ ├── original_dataset     # Raw UC Irvine SMS Spam text
│ │ └── SMSSpamCollection
│ ├── original_dataset_csv
│ │ └── SMSSpamCollection.csv 
│ ├── clean     # Transformed CSV version (with labels)
│ │ └── sms_clean.csv
│ └── splits    # Train, validation, and test splits
│ ├── train.csv
│ ├── val.csv
│ └── test.csv
│
├── OUTPUT    # Generated outputs
│ ├── 01_Exploratory_Plots    # EDA figures
│ │ ├── Class_Distribution.png
│ │ ├── Duplicates_By_Category.png
│ │ ├── Message_Length_Distribution.png
│ │ └── Missing_Values.png
│ │
│ ├── 04_Training_Results  # Training artifacts
│ │ ├── logreg.joblib
│ │ └── train_report.json
│ │
│ └── 05_Test_Eval      # Test results
│ ├── confusion_matrix.png
│ └── test_report.json
│
├── SCRIPTS             # Workflow notebooks (run in order)
│ ├── 01_exploratory_data_clean.ipynb
│ ├── 02_data_clean.ipynb
│ ├── 03_splitting_dataset.ipynb
│ ├── 04_train.ipynb
│ └── 05_eval_tests.ipynb
│
├── requirements.txt   # Required packages
└── .gitignore  # Ignore patterns
```

## Reproducing the Results

### Data locations (already in the repo)
- `DATA/original_dataset/SMSSpamCollection` → raw text  
- `DATA/original_dataset_csv/SMSSpamCollection.csv` → raw CSV  

> All scripts expect columns: **Label, SMS_Message**

---

### Reproduction steps (run in this order)

**1. 01_exploratory_data_clean.ipynb**  
- Quick EDA (class balance, duplicates, length distribution, missing values).  
- Outputs → `OUTPUT/01_Exploratory_Plots/*.png`  
- Not required for later steps, but documents data characteristics.  

**2. 02_data_clean.ipynb**  
- Cleans and normalizes dataset: lowercases labels, trims whitespace, normalizes quotes, removes duplicates.  
- Output → `DATA/clean/sms_clean.csv`  
- Prints: row count, null counts, class distribution.  

**3. 03_splitting_dataset.ipynb**  
- Splits clean dataset into Train/Validation/Test (70/15/15) with stratification.  
- Uses `random_state=42` for reproducibility.  
- Outputs → `DATA/splits/train.csv`, `DATA/splits/val.csv`, `DATA/splits/test.csv`  
- Prints: number of rows and spam ratio per split.  

**4. 04_train.ipynb**  
- Trains Logistic Regression classifier with TF-IDF → RandomOverSampler → LogisticRegression.  
- Uses GridSearchCV (5-fold, f1 score on spam).  
- Outputs →  
  - `OUTPUT/04_Training_Results/logreg.joblib`  
  - `OUTPUT/04_Training_Results/train_report.json`  

**5. 05_eval_tests.ipynb**  
- Final evaluation on held-out test set.  
- Loads trained pipeline and computes metrics + confusion matrix.  
- Outputs →  
  - `OUTPUT/05_Test_Eval/test_report.json`  
  - `OUTPUT/05_Test_Eval/confusion_matrix.png`  

---

### How to verify
- Compare `OUTPUT/04_Training_Results/train_report.json` and `OUTPUT/05_Test_Eval/test_report.json`.  
- Validation and test metrics should be very close.  
- Large differences suggest mistakes (e.g., missing stratification or oversampling outside training).  

---

### Clean run (optional)
- Delete `DATA/clean/`, `DATA/splits/`, and `OUTPUT/`.  
- Re-run Steps **2 → 5** in order.  

---

### Important notes
- `random_state=42` used throughout (splits, oversampling, Logistic Regression).  
- Oversampling applies **only** to training data.  
- Validation/test remain untouched to avoid leakage.  
- Results assume the package versions pinned in `requirements.txt`.  
