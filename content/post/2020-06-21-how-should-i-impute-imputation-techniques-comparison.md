---
date: "2020-06-21"
title: How should I impute? – imputation techniques comparison.
authors: ["Łukasz Brzozowski", "Wojtek Kretowicz", "Kacper Siemaszko"]
tags:
- imputation
- machine learning
- missing values
---

## Why impute?

When people start their journey with machine learning and data analysis, they show a lot of enthusiasm and desire to learn and create. As they progress they encounter many obstacles, that may strip them of their positive attitude. One of the obstacles is missing values in the dataset they're working on. Authors of the article formulated three main problems that come with missings – substantial amount of trained model's  bias, reduction in data analysis efficiency and inability to use many machine learning models, that were not adjusted to handle missing data. Imputing is a way of dealing with this problems and the premise of the article is to demistify imputing and find the best one.

## How to approach such comparison?

Measuring the imputation techique's effectiveness is not a straightforward task. Because of the nature of real missing values we cannot compare the imputed values with the right values that they replace– the only case when we'd be able to do that would be if we forcibly replaced right values with missing. Unfortunately, the results wouldn't be too reliable, because the missing values were artificial. Hence, authors proposed measuring the imputation technique's effectiveness indirectly, by measuring the effectiveness of machine learnig model trained on imputed data. To make the comparison more reliable, authors decide to compare the techniques on 4 different models (logistic regression, naive Bayesian classificator, binomial regression, random forest), 7 different datasets from OpenML (labor, colic, credit-approval, hepatitis, vote, eucalyptus, echoMonths) with 2 different model efficiency metrics (accuracy, F1-score). The imputation methods will be also compared on the complexity level, by measuring the time needed to impute the values.

## Ok, so what methods are compared?

Finally, when we're familiar with the methodology, we can move to the comparison part. Authors decided to compare the following methods:
* IRMI
* hotDeck
* k nearest neighbours (knn)
* missForest
* mean/median/dominant

These methods vary between themselves in complexity and the idea behind them. The least complex is mean/median/dominant – this method imputes the value in the column based on the most narrow aggregate available based on the column type – mean for numerical, median for ordinal and dominant for the rest. More complex and based on the same principle are hotDeck and knn. They both use some kind of similarity metric to find closest records without missing data. Then based on these records they impute the missing values. The most complex methods are IRMI and missForest. They both are based on the principle of using classification and regression models to predict missing values based on the information from other columns in the dataset. Now as we know what methods we compare, we can dive into the results.

## Finding the best technique

## Authors' conclusions
