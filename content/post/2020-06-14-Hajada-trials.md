---
date: "2020-06-14"
title: Hajada trials
authors: ["Olaf Werner","Bogdan Jastrzębski"]
tags:
- imputation
- ML
- OpenML
- dataset
- missings
---

## Our story begins
The story of Hajada is perhaps not an Arabian epic, but still, but just like one of Shecherezade's stories, it'll keep you, dear Reader, on your toes. Sometimes, the data is incomplete and we need to cope with that. There are many methods of so-called "imputation'', i.e. filling gaps in the data. Hanna Zdulska, Jakub Kosterna, Dawid Przybyliński took an effort to compare those methods. Here's what they found out.

## Challengers approach
What kinds of imputation did they compare? The most popular ones, namely "Bogo replace", a simple method of replacing missing values with random values from different observations, replacing with the mode of a median of a given column, MICE imputation, where each incomplete variable is imputed by a separate model, missForest - an intelligent imputation based on fandom forest and VIM's k-NN - an imputation based on the k-NN classifier. All of those methods have been compared with rows removal.

## Battlefields full of gaps
What datasets did they use to test those methods? Unfortunately, the variety of problems in statistical modelling is great and therefore, it's difficult to choose a representative set of examples. Datasets used to test imputation methods concern only binary classification and they all come from "openml" website.

## The Judges will be...
How to measure imputation correctness? It's not a trivial question, but the team has found a brilliant solution. The idea is simple. Imputation methods are compared based on the post-imputation performance of several classification algorithms. If an imputation method produced greater performance gain than another, it's considered the better one.

What classification algorithms should be used to compare those imputation techniques? The team chose rather popular ones: classification tree, k-Nearest Neighbours, Naive Bayes, Ranger and SVM.

The performance of the models has been measured in MCC and F1 score. The team also compared the times required to impute data.

## The True King
It turned out that imputation with mode or median and rows removal are the fastest methods (no surprise). Most importantly, VIM having very low median time has also the biggest variance of all.

![Comparison of imputation times](/2020L-WB-Blog/2020-06-14-Hajada-trials/imputationTimesBoxplot.png)

What about performance gain? Well, the best is for sure VIM, achieving the best median rank overall,  and missForest the second after it. The worst methods turned out to be MICE, imputing with random values and imputing with mode/mean, achieving worst scores in F1 and MCC. The results of other methods differ if we choose to include failed imputations in our benchmark. With failed imputations, median scores of all methods are very similar.

![Imputation rankings of different methods](/2020L-WB-Blog/2020-06-14-Hajada-trials/rankingAll.png)

##   Epilogue
As we can see, the best imputation method overall turned out to bo VIM, among the fastest - replacing with the mode or the median and among the slowest - missForest. 