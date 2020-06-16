---
date: "2020-06-16"
title: Improving glass-box models with various variables transformations
authors: ["Piotr Piątyszek", "Marcin Łukaszyk", "Ngoc Anh Nguyen"]
tags:
- glass-box
- black-box
- features importance
- features transformations
- features engineering
---

Choosing between interpretability and model performance dilemma is gaining popularity. Authors of [this article](https://mini-pw.github.io/2020L-WB-Book/interpretable-non-linear-feature-engineering-techniques-for-linear-regression-models-exploration-on-concrete-compressive-strength-dataset-with-a-new-feature-importance-metric-.html) tested various variables' transformations to increase the performance of glass-box models. To test all things they used the Concrete_Data dataset from the OpenML database. The data is technical, about different proportions of ingredients in building materials and the model aims to predict the compressive strength of created material.

After getting to know our dataset that we want to work on we need to use feature engineering techniques to improve our model. Sometimes, we do it by hand, tweaking it until we get satisfying results, but we can also leave it to automated function that we call, to handle it for us. There are different approaches to do it. The article examined 4 methods:

* by-hand transformations using expert knowledge and experience and via trial and error
* brute forcing many transformations to every variable
* Bayesian optimization (for each variable adding its x-th power, where x is optimized for each variable)
* genetic programming - method proposed by authors, examines simple operations like addition, root, multiplication on random subsets of variables.

# Model Performance
But how to check if transformations of data are indeed helping us? To be sure we need to compare effects with black-box models. Let's check two measures Mean Absolute Error and Mean Squared Error.

![](/2020L-WB-Blog/2020-06-16-Improving-glass-box-models-with-various-variables-transformations/mse.png)
![](/2020L-WB-Blog/2020-06-16-Improving-glass-box-models-with-various-variables-transformations/mae.png)

For linear models, **all of the transforms significantly decreased errors**.  Decision Tree seems untouched and black-box models are affected but without any order. Although brute force beats the other methods it produces 5-7 times more variables and errors are only slightly better.

# Variables importance
In the end which column matters? Generally, after creating and adjusting parameters of our model we can check which parts of our data that we use in training play an important role in the prediction of a model and which not. Authors provide us with a way of finding the importance of each original variable even when the transformed columns are convolutions of two or more variables. Ok sounds fine, but how it works in practical use?

The first image shows the feature importance of black-box models. And the next of glass-box models using introduced measure DFI. Results are similar for models if we consider, that deviations are common in feature importance plots.
![](/2020L-WB-Blog/2020-06-16-Improving-glass-box-models-with-various-variables-transformations/fi1.png)
![](/2020L-WB-Blog/2020-06-16-Improving-glass-box-models-with-various-variables-transformations/global.png)

Check the article for more information about this fascinating DFI method of calculation feature importance of linear models.
