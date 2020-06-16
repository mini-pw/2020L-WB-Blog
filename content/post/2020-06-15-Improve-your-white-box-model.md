---
date: "2020-06-15"
title: *Divide et Conquer* - improve your white box model!
authors: ["Paweł Koźmiński", "Anna Urbala", "Wojciech Szczypek"]
---

# *Divide et Conquer* - improve your white box model!
Divide and conquer is a classical algorithmic tool. It proved its usefulness many times (e.g. in sorting algorithms, multiplying large numbers, or discrete Fourier transform). Thanks to the article of Baniecki and Polakowski (Which Neighbours Affected House Prices in the ’90s?) we discovered yet another application of this algorithm. This time in machine learning. 

## Is it expensive? A house?
The estimation of the price of a house is especially crucial for many people for ages. Unfortunately it is a difficult problem. The scientists, economics and statisticians are still looking for the best tools and algorithms solving it. The reason for the difficulty of this problem is its complexity. The price depends on the many, many, many factors eg. the neighborhood, area, the number of rooms, a development plan of a town, the media, an age of the building. Usually researchers used the black-box models for predicting the prices of the houses. But this method has a one tiny disadvantage - it’s impossible to determine the factors that were decisive. Because of that the authors of the article in question used divide-and-conquer method to improve some white-box models to the level of performance of complex black-box models but preserving the possibility of checking the base of the price.

## Explainable model without loss of efficiency
Knowing the most important factors influencing a house's price might have a great impact in the building trade. Suppose that a developer knows exactly which aspects mostly determine his profit. This knowledge could be a real game changer in running his business and actually a highway to success. The development of science and technology, especially machine learning, has made it more available than ever in the history. However, there is one condition: the models explaining the prices must be interpretable. Nowadays the algorithms reaching the highest efficiency don't meet it. The authors of the article tried to solve this problem: they have proposed a competetive 'stacked model' which is both explainable and very effective.

## Stacked model - how does it work?

The idea of the researches was to minimize the mean absolute error between model's predictions and actual prices. To do that, they decided to divide the dataset with various factors and prices into groups basing on the house's expensiveness. This step is actually performed by an unexplainable classifier, anyway it doesn't affect the overall model's transparency. Afterwards, a white-box estimator is trained on every group of data making it clear what is the way to predict the price in given subset. Fitted classifier and estimators can be successfully applied to test data which is a key fact in examining the correctness of the entire model. Stacked model created like this allows the user to find out which values were the most valuable ones in the process of pricing the house with high accuracy.

[!A caption](/2020L-WB-Blog/2020-06-15-Improve-your-white-box-model/3-7-algorithm.png)


## Results

Results of the research made by authors are very satisfying and impressive indeed. Stacked model whose conception was explained earlier performed terrifically. Not only does it a decent job when it comes to comparing MAE (Mean Absolute Error) with other algorithms, but it's still the representative of white-box models family. Thanks to such an approach we can identify the features importance for each observation. For both cheap and expensive houses stacked model manages to achieve more even spread of residuals. It results in estiamtions to be more reliable. What is interesting is the fact that, when it comes to expensive houses black-box model tends to undervalue house prices, while stacked model overestimates them. Additionally we can clearly see the common fact, that "default" white-box algoithms (linear model, raprt, SAFE on ranger) perform much worse than the black-box ones. Yet it is another reason advantage of stacked model - it combines both better scores than black-box models and clarity of the process of the prediction.


## How about reproducibility?

In our opinion the article did quite poorly when it comes to reproducibility. None of the figures used in article have their source codes. In fact there aren't any code chunks in the whole article itself. It is possible that the whole code used in the article is availible in the external repo, but the repo isn't linked anywhere so it is just a wild guess. Luckily the dataset which is used throughout the article is included in references, but it is the only symptom of reproducibilty availible in the article.

## Conclusion

To sum up, we find the article very interesting. The topic is very common and can easily catch reader's attention. The idea behind the approach is very thouroghly and at the same time clearly and understandably described. It's very original and innovative. Moreover the results are very satsifying. The only diadvantage is the article's poor reproducibility, but it can be easily fixed by linking the repo with codes.
