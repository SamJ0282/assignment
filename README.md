Samyak Jain, Macquarie University

# Table of contents
1. [Portfolio 1](#portfolio1)
2. [Portfolio 2](#portfolio2)
3. [Portfolio 3](#portfolio3)
4. [Portfolio 4](#portfolio4)
    
## Technologies Used <a name="4"></a>

Python

- pandas 1.4.4
- matplotlib 3.7.1
- seaborn 0.12
- sklearn 1.2.2
- numpy 1.24.2


## Portfolio1 <a name="portfolio1"></a>
1. [Project Title](#title)
2. [Project Description](#desc)
3. [About Dataset](#3)
4. [Check and remove missing data](#p1_check_remove)
5. [Descriptive statistics on the data output from Q2](#p1_descriptive)

## Project Title <a name="title"></a>

Analysis of Yelp Data

## Project Description <a name="desc"></a>

The Yelp data is used to analyze patterns and trends in consumer behavior, business performance, and geographic locations.

## Dataset <a name="3"></a>

The Yelp dataset is a collection of user-generated reviews and associated data for businesses in various cities. The data includes information such as the business name, category, location, and rating, as well as the user ID and review text for each review.

The dataset used in this project can be viewed and downloaded here -
https://drive.google.com/file/d/1ijl9ZZrOZPr6rE-uIKjHCPxEHLtEbMVN/view?usp=share_link

## Check and remove missing data <a name="p1_check_remove"></a>
Checks for missing values in each column and removing any row if found missing value in any column and also removing that row which contains value equals to #NAME? or #VALUE! in wither business_id or user_id column 
**Outcome** 
Length of dataset after cleaning is = 229124


## Descriptive statistics on the data output from Q2 <a name="p1_descriptive"></a>
In this task, we computed summary statistics for the stars column of the cleaned dataset.







## Portfolio2 <a name="portfolio2"></a>
1. [Project Title](#title)
2. [Project Description](#desc)
3. [About Dataset](#3)
4. [Processing 'business_categories' column](#business_categories)
5. [Outliers](#outliers)
6. [Training a LinearRegression model](#p2_linear_regression_model)



## Project Title <a name="title"></a>

Analysis of Yelp Data

## Project Description <a name="desc"></a>

The Yelp data is used to analyze patterns and trends in consumer behavior, business performance, and geographic locations.

## Dataset <a name="3"></a>

The Yelp dataset is a collection of user-generated reviews and associated data for businesses in various cities. The data includes information such as the business name, category, location, and rating, as well as the user ID and review text for each review.

The dataset used in this project can be viewed and downloaded here -
https://drive.google.com/file/d/1ijl9ZZrOZPr6rE-uIKjHCPxEHLtEbMVN/view?usp=share_link


## Processing 'business_categories' column <a name="business_categories"></a>
i) The 'business_categories' column in a dataset, is a semicolon-separated list of categories (i.e., 'categorie1; categorie2;...;categorieN')
In this task, we accurately extract the last category value (i.e., categorieN)  
and replace the original string with this last category value.
| Before processing | After processing |
| --- | --- |
| Middle Eastern; Restaurants | Restaurants |
| Tattoo; Beauty & Spas | Beauty & Spas |


ii) Then with the help of **nuinque()** method we identified total number of unique business categroies

iii) Finally, we counted the number of occurrences for each category by using **groupby()** and **count()**
and removed the categiry having count less than 200.

**Outcome**
There are total 19 unique business categories that appear fewer than 200 times.


## Outliers <a name="outliers"></a>
An outlier is an observation that lies an abnormal distance from other values in a random sample from a population

We removed outliers for two scenarios - 
- useful column having value more than equal o 6
- users who rate more than 30 times 


## Training a LinearRegression model <a name="p2_linear_regression_model"></a>
We trained two Linear Regression model - 
| 'useful' and 'stars' coulmns. | 'business_review_count' and 'stars' |
| --- | --- |
| MSE: 1.49368 | MSE: 1.45727 |
| R^2: 0.00660 | R^2: 0.02236 |



Finally, we calculated correlations between variables.
The **correlation coefficient** is a statistical measure of the strength of a linear relationship between two variables. Its values can range from -1 to 1.

**Outcome**
i) Correlations between 'useful' with 'stars' is -0.074, impyting that there is a weak negative association between the two variables
ii) Correlations between 'business_review_count' with 'stars' is 0.1495, impyting that there is apositive association between the two variables



## Portfolio3 <a name="portfolio3"></a>
1. [Project Title](#title)
2. [Project Description](#desc)
3. [About Dataset](#3)
4. [Tasks](#task_3)


## Project Title <a name="title"></a>

Analysis of LendingClub Dataset

## Project Description <a name="desc"></a>

The task of the project is to predict whehter a borrower can replay homeloan and interest on time based on a number of features of the borrower.

## Dataset <a name="3"></a>

The dataset contains the homeloan records released from Lending Club. The problem lenders care is that whether a borrower can repay homeloan and interest on time. In addition, the homeloan interest rate is highly related with the loan credit of borrowers. A borrower with a higher credit can easily get homeloan with a lower rate. The task of the project is to predict whehter a borrower can replay homeloan and interest on time based on a number of features of the borrower. This is a typical classification problem and this notebook demonstrate how to use Lending Club dataset to decide whether a homeloan case should be approved based a borrower' features.

The dataset used in this project can be downloaded here -
https://drive.google.com/file/d/1-3xXWtrIUDfT-OlJWSWQoMLZUBERjCPZ/view?usp=share_link


## Tasks <a name="task_3"></a>
1. [Preprocessing and Cleaning](#task_3.1)
2. [Feature selection](#task_3.2)
3. [Train a logistic regression model](#task_3.3)
4. [Evaluate model with cross validation by using 9 folds](#task_3.4)


## Preprocessing and Cleaning] <a name="task_3.1"></a>
In this task, we filled any missing values in data and removed outliers/abnormal data points. For detecting and removing we used Turkeys method which is based on quartile range (Q1 and Q3).

## Feature selection <a name="task_3.2"></a>
In this task, we seleted only meaningful features having strong positive correlation with target variable ('credit.policy'). With the help of heatmap, we built correlation matrix for each feature with respect to 'credit.policy'

Features having extreme low positive and negative correlation were neglected and removed and were not part of model training.


## Evaluate model with cross validation by using 9 folds <a name="task_3.3"></a>
 In this task, the code performs grid search cross-validation to find the best hyperparameters for the logistic regression model and evaluates its performance on the training, validation, and test sets using accuracy scores.

## Results
| Val 1 | Val 2 | Val 3 | Val 4 | Val 5 | Val 6| Val 7 | Val 8 | Val 9 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0.85969739 | 0.8677686 | 0.85399449 | 0.8677686 | 0.8415978 | 0.8553719 | 0.87052342 |0.86501377 |0.871900833 | 

|Accuracy on training set| 
| --- |
| 0.86228 |

|Accuracy on validation set| 
| --- |
| 0.86138 |

|Accuracy on test set| 
| --- |
| 0.87009 |



## Portfolio4 <a name="portfolio4"></a>
1. [Project Title](#title4)
2. [Project Description](#desc4)
3. [About Dataset](#dataset4)
4. [Objective](#obj4)
5. [Model Training and Evaluation](#model_train_eval)
6. [Results](#result4)


## Project Title <a name="title4"></a>
Predicting Term Deposit Suscriptions


## Project Description <a name="desc4"></a>
In this project, we aim to analyze the results of a past marketing campaign for a financial institution to identify patterns and strategies that will help improve the effectiveness of future marketing campaigns. The business goal of this project is to find ways to increase the ROI of future marketing campaigns, and the context of the problem is to understand how the bank performed in the last campaign and what can be done to increase the performance.

The approach we will take to achieve this goal is by using machine learning techniques. We will begin by visualizing the data to gain an understanding of the patterns and trends in the campaign’s results. Next, we will use a machine learning model such as Logisitc, KNN and RandomForest to make predictions about the effectiveness of the campaign


## About Dataset <a name="dataset4"></a>
Dataset used is called 'Bank Marketing Data' and is taken from popular source called Kaggle.
The dataset has 17 features/columns and target variable is 'deposit' which has binary values as 'yes' and 'no'.
'yes' means client has subscribed a term deposit and 'no' means not subscribed. After removing outliers and normalizing the data, we can build classification models.


## Objective <a name="obj4"></a>
Reducing marketing resources by identifying customers who would subscribe to term deposit and thereby direct marketing efforts to them.

## Model Training and Evaluation <a name="model_train_eval"></a>

1.Logisitc 

Classificaiton Report

![](https://github.com/COMP2200-S1-2023/portfolio-47688408/assets/127278814/0df94cba-b8ac-4776-9236-4c2bcd8b8ea4)


RoC Curve

![roc1 (2)](https://github.com/COMP2200-S1-2023/portfolio-47688408/assets/127278814/edfd999d-f87f-4d8c-abbc-3c4f78c86555)




2. KNN

Classificaiton Report

![class4](https://github.com/COMP2200-S1-2023/portfolio-47688408/assets/127278814/4ed3e6fd-ef77-47be-aeba-be90457c9bb0)



RoC Curve

![knn_roc](https://github.com/COMP2200-S1-2023/portfolio-47688408/assets/127278814/408edc85-570f-4eaa-ab48-7c3b78cb0ad5)

3. RandomForest

### Comparision <a name="comparision4"></a>

![c4](https://github.com/COMP2200-S1-2023/portfolio-47688408/assets/127278814/54a451ea-93b3-4a32-b14d-89121afe2f54)


Accuracies - Logisitc: 0.8226 Random Forest: 0.8517 KNN: 0.7463

After building different Models we want to come to better accuracy score and found that Random Forest is doing the slightly better with 85.17% accuracy than Logisitcs of 82.26% and has higher prediction for 0 and 1 of clients who subscribed for the term depoist. We see that RF has prediction of client subscribed a term deposit about 613 correct vs in Logisitcs with 566 clients who did subscribed. That means we have better prediction in Random Forest. KNN model did perform well with 74.63 % although it has some fallbacks due to the amount of variables.

What I am trying to do is to use different models and observe each model accuracy to see which one perfomring despite the imbalance in the dataset. Also, by looking at the precision and recall of each model, we see that the recall on Random Forest is much higher thant Logisitic and KNN. which tell us how the false positive is minimized since we care about poeople who did subscribed.

The data is imbalanced and this the biggest issue we have since its predicting higher % of (0) and very low on (1).
