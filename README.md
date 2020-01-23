# Project: Write a data science blog post

## Table of contents
1. [Installation](#Installation)
1. [Project motivation](#Project-motivation)
1. [File descriptions](#File-descriptions)
1. [Analysis techniques](#Analysis-techniques)
1. [Results](#Results)
1. [Licensing, authors, acknowledgements](#Licensing,-authors,-acknowledgements)

## Installation
There should be no necessary libraries to run the code here beyond the Anaconda distribution of Python. The code, which is in the file Analysis.ipynb, should run with no issues using Python versions 3.*.

The zip file, survey_results_public.zip, is the dataset. Because of its large size, it has been uploaded to GitHub as a zip file. It should be unzipped before running Analysis.ipynb, and placed in the same directory as the code, and the schema file, survey_results_schema.csv.

## Project motivation
As someone learning coding and data science in order to further my career, I was interested to use the Stake Overflow Developer Survey of 2019 to understand what factors affect income, working horus and job satisfaction for developers today. I wanted to find out the answers to the following questions:
Q1. In Western Europe, is there a link between what languages you work with and earning a higher income?
Q2. Which developer types have the longest working hours per week?
Q3. What are the most important job factors associated with job satisfaction?



## File descriptions
There is one notebook available here, Analysis.ipynb, to showcase work related to the above questions, and is exploratory in searching through the data pertaining to the questions showcased by the notebook title. Markdown cells were used to assist in walking through the thought process for individual steps. 

The zip file, survey_results_public.zip, is the dataset. Because of its large size, it has been uploaded to GitHub as a zip file. It should be unzipped before running Analysis.ipynb.

The associated schema is survey_results_schema.csv. A pdf file of the original survey as it appeared on Stack Overflow is so_survey_2019.pdf.

The dataset, schema and original survey were obtained from the Kaggle page linked in the section [Licensing, authors, acknowledgements.](#Licensing,-authors,-acknowledgements)


## Analysis techniques
The choices I made to wrangle and analyse the data are documented in detail in the code Analysis.ipynb. A summary is below:

### Data
I selected the factors (columns in the dataframe) that I judged to be likely to influence income, working horus and job satisfaction. I removed all NaN values, either by replacing these by mean values, or by removing the entire row from the dataset. A number of factors were categorical or mixed data. I re-coded the categorical data into numerical data. One other issue was that for some questions, multiple answers could be given. E.g. for developer type, the respondent could give several answers if he or she had several roles at work. I one-hot encoded this so that each developer type had a dedicated column in the dataframe. For selected factors, I also inspected the range of values to remove outliers that were likely to be invalid responses, e.g. where people put their age to be close to 100 years old. The choices made are explained in the code.

### Analysis
For Q1 I filtered the dataset for responses where the survey respondent was from Western Europe and compared the profile of languages used by the respondents who earned the top 10% of income against all respondents from Western Europe. For Q2, I plotted the mean working hours for each developer type. For Q3, I instantiated a linear regression model, with job satisfaction as the target variable. Then use a ridge penalty, I identified the coefficients (which correspond to the factors) that had most impact on the target variable. 


## Results
The main findings of the code are also discussed in the post available here: 


## Licensing, authors, acknowledgements
Credit is given to Stack Overflow for the data. You can find the Licensing for the data and other descriptive information at the Kaggle link available here: [link.](https://www.kaggle.com/mchirico/stack-overflow-developer-survey-results-2019#so_survey_2019.pdf)


