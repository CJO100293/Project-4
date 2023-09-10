# Project-4
## **Group Members:**
- Cody Osieczonek
- Tyler White
- Lauren Amoroso

## **Background:**
We are taking data from a bank loan status dataset taken from https://www.kaggle.com/datasets/zaurbegiev/my-dataset?select=credit_test.csv and using it to predict the probababilty of a loan defaulting using machine learning algorithms.

## **Objectives:**
We will train a model with machine learning using the bank loan status dataset to predict the probababilty of a loan defaulting based on the following data:
- Credit score
- Annual income
- Monthly income
- Montly debt
- Monthly debt vs Monthly income (Debt to income ratio)
- Current loan amount
- Current credit balance vs Max Open Credit (credit usage ratio)
- Number of past bankrupcies
- Number of credit problems
- Number of open accounts
- Months since last delinquent

## **Instructions to replicate:**

## **Files:**
- **README.md** - This readme file.
- **/Resources/credit_data.csv** - The original dataset that is used in our project before any ETL work was performed.
- **/ETL/ETL.ipynb** - This jupyter notebook takes the data from "/Resources/credit_data.csv" and performs some cleanup (ETL) work of the data anbd then exports it to a new CSV file located at "/output_data/ETL/csv/ETL_credit_data.csv".
- **/ETL/ETL_colab.ipynb** - This jupyter notebook does the same as "/ETL/ETL.ipynb" except this version can be ran in the cloud using Google Colab
- **/output_data/ETL/csv/ETL_credit_data.csv** - This CSV file is what is created after ETL work is performed on the original data using "/ETL/ETL.ipynb".
- **/ML/ML.ipynb** - This jupyter notebook performs supervised machine learning on the cleaned up data that was generated from "/ETL/ETL.ipynb".
- **/ML/ML_colab.ipynb** - This jupyter notebook does the same as "/ML/ML.ipynb" except this version can be ran in the cloud using Google Colab.

## **Sources:**
- Our dataset located in "/Resources/credit_data.csv" originated from https://www.kaggle.com/datasets/zaurbegiev/my-dataset?select=credit_test.csv. We renamed it from "credit_test.csv" to "credit_data.csv".
- The basis for the code used in the "Mouting Google Drive Account" section of "/ETL/ETL_colab.ipynb" was found from https://saturncloud.io/blog/exporting-dataframe-as-csv-file-from-google-colab-to-google-drive/.
- The basis for the code used in the "Un-Mouting Google Drive Account" section of "/ETL/ETL_colab.ipynb" was found from https://stackoverflow.com/questions/54837135/how-to-unmount-drive-in-google-colab-and-remount-to-another-drive.