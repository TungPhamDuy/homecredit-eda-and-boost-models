# homecredit-eda-and-boost-models
**_License:
This is a personal project of Tung Pham in order to serve as the midterm project for the Machine Learning course taken at the University of Economics and Law (VNU-HCM)_**

**Project Title:**
Home Credit Default Risk: EDA and Machine Learning Model 


**The problem statement:**
Many people struggle to get loans due to insufficient or non-existent credit histories. And, unfortunately, this population is often taken advantage of by untrustworthy lenders. Home Credit strives to broaden financial inclusion for the unbanked population by providing a positive and safe borrowing experience. In order to make sure this underserved population has a positive loan experience, Home Credit makes use of a variety of alternative data--including telco and transactional information--to predict their clients' repayment abilities. 

While Home Credit is currently using various statistical and machine learning methods to make these predictions, they're challenging the data science community to help them unlock the full potential of their data. Doing so will ensure that clients capable of repayment are not rejected and that loans are given with a principal, maturity, and repayment calendar that will empower their clients to be successful.

**Project Decription:**
A simple notebook on Exploration (EDA) and Baseline Machine Learning Model of Home Credit default risk data to prediction future payment problem for clients of the company.

**Describe the dataset:**
- application_{train|test}.csv: This is the main table, broken into two files for Train (with TARGET) and Test (without TARGET). Static data for all applications. One row represents one loan in our data sample.
- bureau.csv: All client's previous credits provided by other financial institutions that were reported to Credit Bureau (for clients who have a loan in our sample). For every loan in our sample, there are as many rows as number of credits the client had in Credit Bureau before the application date.
- bureau_balance.csv: Monthly balances of previous credits in Credit Bureau. This table has one row for each month of history of every previous credit reported to Credit Bureau – i.e the table has (#loans in sample * # of relative previous credits * # of months where we have some history observable for the previous credits) rows.
- POS_CASH_balance.csv: Monthly balance snapshots of previous POS (point of sales) and cash loans that the applicant had with Home Credit. This table has one row for each month of history of every previous credit in Home Credit (consumer credit and cash loans) related to loans in our sample – i.e. the table has (#loans in sample * # of relative previous credits * # of months in which we have some history observable for the previous credits) rows.
- credit_card_balance.csv: Monthly balance snapshots of previous credit cards that the applicant has with Home Credit. This table has one row for each month of history of every previous credit in Home Credit (consumer credit and cash loans) related to loans in our sample – i.e. the table has (#loans in sample * # of relative previous credit cards * # of months where we have some history observable for the previous credit card) rows.
- previous_application.csv: All previous applications for Home Credit loans of clients who have loans in our sample. There is one row for each previous application related to loans in our data sample.
- installments_payments.csv: Repayment history for the previously disbursed credits in Home Credit related to the loans in our sample. There is a) one row for every payment that was made plus b) one row each for missed payment. One row is equivalent to one payment of one installment OR one installment corresponding to one payment of one previous Home Credit credit related to loans in our sample.
- HomeCredit_columns_description.csv: This file contains descriptions for the columns in the various data files.

**Conclusion:**

Performance comparison of 3 models appears to be quite similar with:

- LightGBM: 0.781738
- XGBoost: 0.768527
- CatBoost: 0.778458

Overall, LightGBM performed the best among the three models on the given dataset, followed by CatBoost, while XGBoost had the lowest performance. However, it's important to note that despite using the same dataset for 3 models, the specific performance of each model can vary depending on the parameters that we config and assign to each one, and the randomness of using data in their training process. 

Despite the models may have different accuracy values, they are still relatively close to each other. This indicates that all three models are providing reasonably reliable predictions on the given dataset.
