# How Media Can Support Early Childhood Learning Outcomes

![PBS logo](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/Pbskids.png)

This project is part of the [Kaggle's 2019 Data Science Bowl](https://www.kaggle.com/c/data-science-bowl-2019)
Started on November 1st, 2019


#### -- Project Status: [Active]

## Project Intro/Objective
The project comes from PBS KIDS, a trusted name in early childhood education for decades, aims to gain insights into how media can help children learn important skills for success in school and life. In this project, the gameplay data, including knowledge of videos watched and games played, from the PBS KIDS Measure Up! the app, a game-based learning tool developed as a part of the CPB-PBS Ready To Learn Initiative with funding from the U.S, is provided. The purpose is to predict scores on in-game assessments and create an algorithm that will lead to better-designed games and improved learning outcomes.

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

![Group distribution](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/dist_group.png)

For more descriptions about the data please visit [2019 Data Science Bowl \| Kaggle](https://www.kaggle.com/c/data-science-bowl-2019/data).

## Some EDA
1) There are 5 different assessments. When **assessments are stacked on the accuracy group distribution** we obtain this interesting graph that can descibe the difficulty of each assessment

![Accuracy group count](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/acc_group_count.png)

2) Data was collected in 3 months span from June to October. The **time series by number of hours spent**  provided us some abnomality in late August and Septemper

![hour per datet](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/game_time_date.png)

3) The time zone for each players are not provided. However, the **total hour spend per hour of the day distribution** suggests that most of the players belong to the same region. A further investigation (compare the graph with dota 2 players count) indicate that this region is in fact belong to North America. More about this in the powerpoint.

![Hour per day hour](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/Time_of_a_day.png)

4) Using a classical approach, **classification on a multi-classification problems**, we obtain a comparison between 4 ensemble models. Light GBM and XGBoosts seems to be the best model. However, when ploting the histogram for the test set output, a extreme skewed distribution occur suggests that this is highly overfitting

![Model](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/model.png)

5) Applying tremendous feature engineerings, oversampling techniques, light gbm regression, and optimization rounder, we obtain a **better result** and scored relatively high (top 30%) on Kaggle leaderboard

![Last attemp](https://github.com/williamhuybui/Predicting-Kids-Learning-Outcome-Through-PBSKidsMeasureUp-app-Flatiron-School-Capstone-Project/blob/master/Picture/last_attempt.png)

For more explaination and EDA, please download and open the **powerpoint file**.
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
