# zeng-Kaggle_JobSalaryPrediction


## Introduction
This is the repo for **B3155 - PROJECT WORK IN MACHINE LEARNING AND DATA MINING** in UNIBO with professor Sartori.  
I chosed a comepetition from Kaggle which approved by professor,  
The name of this project is **Job Salary Prediction**, which was launched under the Kaggle Startup Program.  
The link to this competition: *https://www.kaggle.com/competitions/job-salary-prediction/overview* .  
In this project, we delve into a comprehensive analysis of the salary of any UK job ad, by using a large datset with mostly unstructured text, with a few structured data fields. We performed it as a NLP task.

The evaluation metric for this competition is Mean Absolute Error.

## Dataset Previw

The main dataset consists of a large number of rows representing individual job ads, and a series of fields about each job ad.  These fields are as follows:  
**Features:**
1. Id - A unique identifier for each job ad.
2. Title - A freetext as the Title of the job ad.
3. FullDescription - The full text of the job ad.
4. LocationRaw - The freetext location.
5. LocationNormalized - Adzuna's normalised location from a different file "Location_Tree.csv".
6. ContractType - full_time or part_time.
7. ContractTime - permanent or contract.
8. Company - the name of the employer.
9. Category - which of 30 standard job categories this ad fits into.

  
**Targets:**
1. SalaryRaw - the freetext salary field.
2. SalaryNormalised - **This is the value we are trying to predict.**


## Methods

1. For improving the interpretability of location information, we used the geonames API to update each 'LocationRaw' column to 'Country, County, City' respectly.
2. For missing values of 'ContractTime', besides 'permanent' and 'contract', we filling 'unknown' as a new type for missing rols.
3. Then we combine all text features to a fulltext with a little cleaning.
4. We used a Transformer model to embed the text for better capture the semantic similarity between vocabulary and the complex characteristics of the learning text.
5. We training a MLP on top for predicting our target 'SalaryNormalised' value.

## Results

I got final result at around 6300 MAE loss, which would be around 46th on the leaderboard. However, claiming that is not completely valid cause competition does not allow submissions now nor does it give out the true labels of the test data, the loss which I get is split 20% of train data as test data at the start.



