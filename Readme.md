# How media can support early childhood learning outcomes.

This project is part of the [Kaggle's 2019 Data Science Bowl](https://www.kaggle.com/c/data-science-bowl-2019)
Started on November 1st, 2019

#### -- Project Status: [Active]

## Project Intro/Objective
The project comes from PBS KIDS, a trusted name in early childhood education for decades, aims to gain insights into how media can help children learn important skills for success in school and life. In this project, the gameplay data, including knowledge of videos watched and games played, from the PBS KIDS Measure Up! the app, a game-based learning tool developed as a part of the CPB-PBS Ready To Learn Initiative with funding from the U.S, is provided. The purpose is to predict scores on in-game assessments and create an algorithm that will lead to better-designed games and improved learning outcomes.

This is a multiclassification problem with 4 possible outcomes
3: the assessment was solved on the first attempt
2: the assessment was solved on the second attempt
1: the assessment was solved after 3 or more attempts
0: the assessment was never solved

### Methods Used
* **Metric**: [Quadratic Weighted Kappa](https://www.kaggle.com/c/data-science-bowl-2019/overview/evaluation)

* **Model**: `lightgbm`, `xgboost`, `gcboost`, `random forest`

* **Optimized Rounder**: Threshold optimization to convert from a regression problem to a classification problem. Originated from the discussion [PetFinder.my Adoption Prediction \| Kaggle](https://www.kaggle.com/c/petfinder-adoption-prediction/discussion/76107) and later was improved [here](https://www.kaggle.com/naveenasaithambi/optimizedrounder-improved)

* **Data Visualization**: Tableau, matplotlib.

### Technologies
* **python** and library in python such as `sklearn`, `pandas`, `numpy`, `imbalanced-learn`, ...
* Presentation: keynote, matplotlib, pyplot, seaborns.

## Dataset Description
The dataset provides the game analytics for the PBS KIDS Measure Up! app. In this app, children navigate a map and complete various levels, which may be activities, video clips, games, or assessments. Each assessment is designed to test a child's comprehension of a certain set of measurement-related skills. There are five assessments: Bird Measurer, Cart Balancer, Cauldron Filler, Chest Sorter, and Mushroom Sorter.

The competition intends to use the gameplay data to forecast how many attempts a child will take to pass/fail a given assessment (an incorrect answer is counted as an attempt).

The outcomes in this competition are grouped into 4 groups (labeled accuracy_group in the data):

3: the assessment was solved on the first attempt
2: the assessment was solved on the second attempt
1: the assessment was solved after 3 or more attempts
0: the assessment was never solved

For more descriptions about the data please visit [2019 Data Science Bowl \| Kaggle](https://www.kaggle.com/c/data-science-bowl-2019/data).


## Getting Started

1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/)).

2. Raw Data is being kept [here](https://www.kaggle.com/c/data-science-bowl-2019/data). Download five files at the Data Sources tab and place them in the new folder name `output`. Put `output` to the main folder created in step 1
    
3. When running this notebook on  Kaggle, you do not need to install any package. For local use, simply execute `!pip install <name_of_the_library>` if an error shows up

4. The folder structure should be:
**Input**
* sample_submission
* specs.csv
* test.csv
* train_labels.csv
* train.csv
**output**
* label.csv
* X_test.csv
* X_train.csv
**base_line.ipynb**: stupidly simple approach that gives a very good baseline scores
**Data.ipynb**: Where the raw data (from input) was preprocessed (to output)
**Classification.ipynb**: first attemp on the problem

**Regression.ipynb**: the second attempt using the regression model
**Visualization**: where most of the visual in the powerpoint come from
**Readme.md**
**DataScienceBowl.pptn**: Powerpoint presentation that contain all the result from the start to the latest version.


## Contact
* williamhuybui@gmail.com
