# Nowcasting-the-monthly-UK-HPI-Growth
This repository contains the code and analysis for my MSc Research Project on the topic: "Nowcasting of UK House Prices using High-Frequency Data and Machine Learning Models". 
# PROJECT OBJECTIVE
The UK HPI suffers from a fundamental limitation of a substantial publication delay of approximately seven weeks for each month's figure. This project aims to reduce this publication delay though the development of a robust nowcasting framework. The project uses a wide arrary of machine learning models, along with high-frequency data sources, such as Google Trends search indices and GDELT news sentiment index and conventional macroeconomic predictors in a rolling window framework to generate timely estimates of HPI growth each month. 
# DATA SOURCES
1. Official UK House Price Index
2. Macroeconomic predictors: Bank Rate, Mortgage Rate, Mortgage Approval, Inflation Rate, Unemployment Rate, Average Earnings, Consumer Confidence Index, Construction Cost Index
3. High-Frequency predictors: Google Trends search indices, GDELT news sentiment index
All the variables have been aggregated to a monthly frequency.
The link to the datasets can be found here: https://drive.google.com/drive/folders/1d6ATixigVlxfTZA8u_zpTlaasrfCY3_4?usp=sharing
# REPOSITORY STRUCTURE
The notebooks have been numbered to reflect the order of execution. 
## Data Preparation
**01. Cleaning_Macro_variables_and_target_variable.ipynb** 
This cleans the eight macroeconomic variables and prepares the target variable: HPI

**02. GDELT_Data_Extraction_and_Processing.ipynb**  
This file extracts, aggregates, and constructs the GDELT news sentiment index.

**03. Google_Trends_Data_Extraction_and_Processing.ipynb**  
This file extracts, aggregates, and constructs the five theme-based Google Trend indices.

**04. Merge_1(_GT_keywords_+_HPI_+_macro_variables).ipynb**  
This file merges the macroeconomic predictors and HPI data with the Google Trend indices.

**05. Merge_2(GDELT+_GT_+_HPI+_macrovariables).ipynb** 
This file combines the already merged file developed in Point 4 with the GDELT news sentiment index to produce the final dataset called the "Master file". This is a regional panel dataset containing the target variable, macroeconomic and high-frequency indicators.

## Exploratory Analysis, Preprocessing, and Modelling
**06. MODIFIED_Data_Preprocessing,_Exploratory_analyses_and_Modelling.ipynb** 
This file uses the Master file developed from notebook 5 to conduct preprocessing, exploratory analysis and modelling. The econometric models and machine learning models have all been implemented in this notebook. 

## Robustness Checks  
**07. MODIFIED_Robustness_checks.ipynb** 
This file contains the various robustness checks that have been conducted to establish the validity of the model results.

**08. Robustness_Check_(Running_Models_from_2015_to_2025).ipynb** 
This file contains another robustness check to account for different data versions in GDELT data extraction. It re-estimates all the models on a shorter timeline of 2015 to 2025.

**09. TFT- Final.ipynb** 
This file implements a deep learning model called Temporal Fusion Transformer as an additional robustness check.

# MODELS IMPLEMENTED
Traditional benchmark models:
1. ARIMA
2. SARIMA
3. VAR
Machine Learning models:
1. Ridge Regression
2. Lasso Regression
3. XGBoost
4. Random Forest
# ADDITIONAL NOTES
1. The notebooks have been designed to be executed sequentially from 01 to 09.
2. Some of the data extraction steps, particularly GDELT sentiment index and model implementation such as XGBoost and Random Forest are quite time-consuming to run.

# AUTHOR
**Tasnim Momtaz Nodee**  
MSc Data Science and Analytics  
University of Westminster  
