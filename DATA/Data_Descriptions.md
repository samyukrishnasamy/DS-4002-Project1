# Data Descriptions

## Clean
The **sms_clean.csv** file is a cleaned and standardized version of the dataset.  
In this file, the column names are more descriptive (`Label` and `SMS_Message`), and the contents have been lightly processed to remove inconsistencies such as duplicate entries or formatting errors. This cleaned version has fewer rows than the raw set, reflecting the effort to prepare it for model training and evaluation.

## Original Dataset
The **SMSSpamCollection.txt** file is the original raw dataset.  
It is a tab-separated text file with two columns: one indicating whether a message is spam or ham (non-spam), and the other containing the actual text message. It is the classic format in which this dataset is shared publicly, preserving all of the original rows and labels as they were first released.

## Original Dataset (CSV)
The **SMSSpamCollection.csv** file is essentially the same dataset as the TXT version, but saved in a CSV format.  
This makes it easier to load into tools such as Python’s pandas library without having to specify custom delimiters. It keeps the same structure of label and message, but in a spreadsheet-friendly form.

## Splits
Alongside these datasets, there are also three important split datasets stored in the **splits/** folder: **train**, **validation**, and **test**.  

- **Train set**: The portion of the data used to teach the model patterns from examples.  
- **Validation set**: Used during development to fine-tune decisions like hyperparameter choices and to help prevent overfitting.  
- **Test set**: Held out until the end and used once to provide an unbiased measure of how well the model performs on unseen messages.  

Together, these three splits ensure the machine learning process is structured, fair, and reliable.
