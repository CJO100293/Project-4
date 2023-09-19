# Project-4
## **Group Members:**
- Cody Osieczonek
- Tyler White
- Lauren Amoroso

## **Background:**
We are taking data from a bank loan status dataset taken from https://www.kaggle.com/datasets/zaurbegiev/my-dataset?select=credit_test.csv and using it to predict the probability of a loan defaulting using machine learning algorithms.

## **Objectives:**
- We will train a model with machine learning using the bank loan status dataset to predict the probability of a loan defaulting based on the following data:
 - Credit score
 - Annual income
 - Monthly income
 - Monthly debt
 - Monthly debt vs monthly income (debt to income ratio)
 - Current loan amount
 - Current credit balance
 - Total credit
 - Current credit balance vs max open credit (credit usage ratio)
 - Whether there had been past bankruptcies or not.
 - Number of credit problems
 - Number of open accounts
 - Months since last delinquent
 - Credit history (years)

- We experimented using various different supervised machine learning algorithms such as logistic regression, kneighbors and random forest to see which one could train the data with the best accuracy.
- The "Bankruptcies" columns will be used as our labels and all other columns will be used as our features of each of the models.

## **Instructions to replicate:**
1. Run the jupyter notebook "/ETL/ETL.ipynb" (or "/ETL/ETL_colab.ipynb" if using google collab. if using google collab then the path to where the CSV file "ETL_credit_data.csv" will be exported in the "Export the newly transformed dataframe into a csv" section will need to be changed to an empty existing directory in your google drive account.) This will clean up the data in "/Resources/credit_data.csv" by removing any unneeded or erroneous data and exports it into a new CSV file called "ETL_credit_data.csv".
2. Run the jupyter notebook "/ML/ML.ipynb" (or "/ML/ML_Colab.ipynb" if using google collab). This will use various supervised machine learning algorithms to determine if the loan is at risk of default.
3. You can then see the visualizations we made using "/output_data/ETL/csv/ETL_Visualizations_credit_data.csv" by opening "/Visualizations/Project-4-Visualizations.twbx" in Tableau or by visiting https://public.tableau.com/app/profile/cody.osieczonek/viz/Project-4-Visualizations/BankruptciesPieGraph.

**Things To Note:**  \
  \
**We had removed row numbers 454, 539, 1754, 2682, 5863, 7085 and 9970 from "/output_data/ETL/csv/ETL_credit_data.csv" because it contained what we believe to be erroneous data shared between the "Total Credit" and "Credit Balance" columns. For example, row 454 shows a credit balance of 515,261 even though available credit is 0. Due to this when we went to Create a new column named "Credit Usage Ratio" and have its values be equal to "Credit Balance / Total Credit" it caused it to give values of "inf" in these rows since 515261 is not divisible by 0. This in turn was causing trouble with our machine learning.**

## **Presentation**
- Our project presentation can be viewed from either https://docs.google.com/presentation/d/1q3cAmkjD_Ox3ueyW58Ho7ot7wyKV6vFjrObQKJ35iT0/edit?usp=sharing or from the powerpoint file "/Presentation/Probability of Loan Defaults - Presentation.pptx".

## **Files:**
- **README.md File and Original Dataset File:**
  - **README.md** - This readme file.
  - **/Resources/credit_data.csv** - The original dataset that is used in our project before any ETL work was performed.
- **ETL Files:**
  - **/ETL/ETL.ipynb** - This jupyter notebook takes the data from "/Resources/credit_data.csv" and performs some cleanup (ETL) work of the data and then exports it to a new CSV file located at "/output_data/ETL/csv/ETL_credit_data.csv".
  - **/ETL/ETL_colab.ipynb** - This jupyter notebook does the same as "/ETL/ETL.ipynb" except this version can be ran in the cloud using Google Colab
  - **/ETL/ETL_Visualizations.ipynb** - This jupyter notebook takes the data from "/output_data/ETL/csv/ETL_credit_data.csv" and changes the values of the "bankruptcies" column from "0" to "No" and from "1" to "Yes" then exports it to a new CSV file located at "/output_data/ETL/csv/ETL_Visualizations_credit_data.csv". This data will specifically be used only in our Tableau visualizations.
  - **/ETL/ETL_Visualizations_Colab.ipynb** - This jupyter notebook does the same as "/ETL/ETL_Visualizations.ipynb" except this version can be ran in the cloud using Google Colab
  - **/output_data/ETL/csv/ETL_credit_data.csv** - This CSV file is what is created after ETL work is performed on the original data using "/ETL/ETL.ipynb". This data will specifically be used only in our Tableau visualizations.
  - **/output_data/ETL/csv/ETL_Visualizations_credit_data.csv** - This CSV file is what is created after "/output_data/ETL/csv/ETL_credit_data.csv" has its values of the "bankruptcies" column changed from "0" to "No" and from "1" to "Yes". 
- **Supervised Machine Learning Files:**
  - **/ML/ML.ipynb** - This jupyter notebook performs supervised machine learning on the cleaned-up data that was generated from "/ETL/ETL.ipynb".
  - **/ML/ML_colab.ipynb** - This jupyter notebook does the same as "/ML/ML.ipynb" except this version can be ran in the cloud using Google Colab.
- **Tableau Visualization Files:**
  - **/Visualizations/Project-4-Visualizations.twbx** - This file contains our tableau visualizations created using "/output_data/ETL/csv/ETL_Visualizations_credit_data.csv".
- **Project-Presentation Files:**
  - **/Presentation/Probability of Loan Defaults - Presentation.pptx** - This file is the powerpoint file to our project presentation.

## **Sources:**
- Our dataset located in "/Resources/credit_data.csv" originated from https://www.kaggle.com/datasets/zaurbegiev/my-dataset?select=credit_test.csv. We renamed it from "credit_test.csv" to "credit_data.csv".
- The basis for the code used in the "Mounting Google Drive Account" section of "/ETL/ETL_colab.ipynb" was found from https://saturncloud.io/blog/exporting-dataframe-as-csv-file-from-google-colab-to-google-drive/.
- The basis for the code used in the "Un-Mounting Google Drive Account" section of "/ETL/ETL_colab.ipynb" was found from https://stackoverflow.com/questions/54837135/how-to-unmount-drive-in-google-colab-and-remount-to-another-drive.
- The basis for the code used in the "Dropping Rows 452, 537, 1752, 2680, 5861, 7083 and 9968 because we believe it has some erroneous data" section of "/ETL/ETL.ipynb" and "/ETL/ETL_colab.ipynb" came from https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop.html.