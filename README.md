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

The following steps recreate the exact outputs in `OUTPUT/` starting from the raw dataset in `DATA/`.

### 1. Set up environment
```bash
git clone https://github.com/<your-username>/DS-4002-Project1.git
cd DS-4002-Project1

# (Optional but recommended) create a virtual environment
python3 -m venv .venv
source .venv/bin/activate       # Windows (PowerShell): .venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt


