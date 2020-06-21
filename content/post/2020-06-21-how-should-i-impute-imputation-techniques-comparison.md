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

When people start their journey with machine learning and data analysis, they show a lot of enthusiasm and desire to learn and create. As they progress, they encounter many obstacles, that may strip them of their positive attitude. One example of such obstacles is missing data in the dataset they're working on. Authors of the article titled "Imputation techniques' comparison in R programming language" formulated three main problems that come with missing values – substantial amount of trained model's  bias, reduction in data analysis efficiency and inability to use many machine learning models, that were not adjusted to handle missing data. Imputing is a way of dealing with this problems and the premise of the article is to demistify imputing and find the best method.

## How to approach such comparison?

Measuring the imputation techique's effectiveness is not a straightforward task. Because of the nature of real missing values we cannot compare the imputed values with the right values that they replace – the only case when we'd be able to do that would be if we forcibly replaced right values with missing. Unfortunately, the results wouldn't be too reliable, because the missing values were artificial. Hence, authors proposed measuring the imputation technique's effectiveness indirectly, by measuring the effectiveness of machine learnig model trained on imputed data. To make the comparison more reliable, the authors decide to compare the techniques on 4 different models (logistic regression, naive Bayesian classificator, binomial regression, random forest), 7 different datasets from OpenML (labor, colic, credit-approval, hepatitis, vote, eucalyptus, echoMonths) with 2 different model efficiency metrics (accuracy, F1-score). The imputation methods will be also compared on the complexity level, by measuring the time needed to impute the values.

## Ok, so what methods are compared?

Finally, when we're familiar with the methodology, we can move to the comparison part. Authors decided to compare the following methods:
* IRMI
* hotDeck
* k nearest neighbours (knn)
* missForest
* mean/median/dominant

These methods vary in complexity and the idea behind them. The least complex is mean/median/dominant – this method imputes the value in the column based on the most narrow aggregate available based on the column type – mean for numerical, median for ordinal and dominant for the rest. More complex and based on the same principle are hotDeck and knn. They both use some kind of similarity metric to find closest records without missing data. Then based on these records they impute the missing values. The most complex methods are IRMI and missForest. They both are based on the principle of using classification and regression models to predict missing values based on the information from other columns in the dataset. Now as we know what methods we compare, we can dive into the results.

## Finding the best technique

The results and conclusions that authors came up are not straightforward. Depending on the task different methods perform better. The authors considered two measures -  accuracy and F1 score (it is a harmonic mean of precision and recall). Below, in the chart, are presented final, aggregated results:

![Overall method effectiveness](overall.png)

![Legend](Legenda.png)

Naturally, the bigger the values of accuracy and F1, the better each model performed. We may notice that when it comes to F1 score, *MissForest* package yielded undeniably best results. While the differences in accuracy are not as significant, the same package seems to perform best overall. However, we wish the authors did not use the jitter effect on the plot, as it seems to decrease the readability of the plots greatly.

### Authors' conclusions

Depending on the size of the data set and the amount of missing data, authors concluded that in presented groups the best algorithms are:

|             |   small  |   medium   |         big        |
|-------------|:--------:|:----------:|:------------------:|
| tiny        | -        | -          | hotdeck/MissForest |
| middling    | IRMI     | MissForest | IRMI               |
| significant | IRMI/kNN | -          | IRMI/kNN           |

where *tiny* means that less than 1% of all values are missing, *middling* means ~5% missing data and *significant* means that over 15% of the data is missing.

Authors suggest that the safest method to choose is MissForest. Interesingly, there was no task where *mean*, *median* or *dominant* performed the best, which shows that the simplest imputation methods don't perform well compared to more complex algorithms.

Another considered aspect is time. *IRMI* needed much more time on average to make calculations. However, authors the stated that none of these algorithms is highly time consuming. Nonetheless, if you are dealing with a huge dataset and need to calculate things quickly, *IRMI* may not be the best choice, perhaps *MissForest* would perform better.

### Things to improve

While we enjoyed the article greatly, we noticed some parts of the article which could be improved to make it even better. 
First of all, we wish there was some info on the models' hyperparameters available - while we deduce from the article that the models used default hyperparameters from the *mlr* package, we suspect that changing hyperparameters could be used to perform a more extensive comparison of the models, as we don't really know that an imputation method would still perform alike after tuning the hyperparameters.

Secondly, the authors didn't explicitly provide us with information what fraction of the dataset was missing data. We were able to calculate the percentage of missing data in the dataset, but we believe that including that piece of information would increase the article's readability greatly - especially if the authors propose various methods of imputation depending on the percentage of missing data. We therefore present here the calculated fractions for each dataset:

  * *labor* - 33.6% of missing data
  * *colic* - 16.3% of missing data
  * *credit-approval* - 0.6% of missing data
  * *hepatitis* - 5% of missing data
  * *vote* - 5% of missing data
  * *eucalyptus* - 4% of missing data
  * *echoMonths* - 7% of missing data
  
Having that data presented directly, we are a bit surprised the authors decided to divide the datasets into groups having <1%, 1-15%, >15% of missing data, while only one dataset has less than one percent of missing data and only two datasets have more than 15% of missing data, while they differ greatly in the fraction (16.3% and 33.6%). We wish that the authors divided the datasets differently or presented the results on more datasets, as some results may be quite unreliable.

Finally, the authors unfortunately did not inform us which datasets are *medium* in size - the only bit of information we found was that the datasets were *big* if they contained at least 10000 values. We wish that the rule of such division was presented explicitly. 

### Summary

The article presents quality suggestions which imputations methods to use when we deal with missing data in machine learning tasks, adn we reckon it a great comparison of the presented imputation methods. While we are not entirely convinced of reliability of the results when the fraction of missing data is *tiny* or *significant* (<1% and >15%), we value the extensive analysis performed on the datasets having a *middling* fraction of missing data and we will incorporate the suggested tools in our own works in the future.
