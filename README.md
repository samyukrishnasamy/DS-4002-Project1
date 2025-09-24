## Repository Structure

DS-4002-PROJECT1
├── DATA
│ ├── original_dataset
│ │ └── SMSSpamCollection
│ ├── original_dataset_csv
│ │ └── SMSSpamCollection.csv
│ ├── clean
│ │ └── sms_clean.csv
│ └── splits
│ ├── train.csv
│ ├── val.csv
│ └── test.csv
│
├── OUTPUT
│ ├── 01_Exploratory_Plots
│ │ ├── Class_Distribution.png
│ │ ├── Duplicates_By_Category.png
│ │ ├── Message_Length_Distribution.png
│ │ └── Missing_Values.png
│ │
│ ├── 04_Training_Results
│ │ ├── logreg.joblib
│ │ └── train_report.json
│ │
│ └── 05_Test_Eval
│ ├── confusion_matrix.png
│ └── test_report.json
│
├── SCRIPTS
│ ├── 01_exploratory_data_clean.ipynb
│ ├── 02_data_clean.ipynb
│ ├── 03_splitting_dataset.ipynb
│ ├── 04_train.ipynb
│ └── 05_eval_tests.ipynb
│
├── requirements.txt
└── .gitignore