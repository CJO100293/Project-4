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
- Monthly debt
- Monthly debt vs Monthly income (Debt to income ratio)
- Current loan amount
- Current credit balance vs Max Open Credit (credit usage ratio)
- Whether there had been past bankruptcies or not.
- Number of credit problems
- Number of open accounts
- Months since last delinquent

## **Instructions to replicate:**
1. Run the jupyter notebook "/ETL/ETL.ipynb" (or "/ETL/ETL_colab.ipynb" if using google collab. if using google collab then the path to where the CSV file "ETL_credit_data.csv" will be exported in the "Export the newly transformed dataframe into a csv" section will need to be changed to an empty existing directory in your google drive account.) This will clean up the data in "/Resources/credit_data.csv" by removing any unneeded or erroneous data and exports it into a new CSV file called "ETL_credit_data.csv".
2. Run the jupyter notebook "/ML/ML.ipynb" (or "/ML/ML_Colab.ipynb" if using google collab). This will use supervised machine learning to determine if the loan is at risk of default using the "Bankruptcies" column as labels and all of the other columns as features.

**Things To Note:**  \\
**We had removed row numbers 454, 539, 1754, 2682, 5863, 7085 and 9970 from "/output_data/ETL/csv/ETL_credit_data.csv" because it contained what we believe to be erroneous data shared between the "Total Credit" and "Credit Balance" columns. For example row 454 shows a credit balance of 515,261 even though available credit is 0. Due to this when we went to Create a new column named "Credit Usage Ratio" and have its values be equal to "Credit Balance / Total Credit" it caused it to give values of "inf" in these rows since 515261 is not divisible by 0. This in turn was causing trouble with our machine learning.**

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
- The basis for the code used in the "Dropping Rows 452, 537, 1752, 2680, 5861, 7083 and 9968 because we believe it has some erroneous data" section of "/ETL/ETL.ipynb" and "/ETL/ETL_colab.ipynb" came from https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop.html.