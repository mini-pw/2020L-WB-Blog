---
date: "2020-06-09"
title: Update or not to update - this is the question!
authors: ["Martyna Majchrzak", "Agata Makarewicz", "Jacek Wiśniewski"]
tags:
- reproducibility
- active development
- package
- updating
- article
- R journal
- version control
---

Once researchers public a piece of software and publish a paper about it, should they continue to update the package, resolving users' issues and adding more features or just leave it be? This question might seem trivial, but turns about to be a bit more complex than you may think.
We recently read an artice, written by Ngoc Anh Nguyen, Piotr Piątyszek and Marcin Łukaszyk from Warsaw University of Technology, that covers the subject of how active development of an R package affects the reproducibility of the article that introduced it.


## What is reproducibility and how it was measured?


Reproducibility is a highly desirable quality of a science article, that allows a different research team to attain the identical results using the same methods. This can be negatively affected by changes between package versions, for example different function names or changes in API used inside the article. However, widely used version control system is said to be a key feature in creating reproducible research. So which one is it?

The authors compared the reproducibility of 18 articles introducing packages from R journal, using two versions of the described package - the current one and one that was first published (simmulating what would happen, if the author have never updated it). The articles were given marks from 1 (highly reproducible) to 3 (not reproducible). In all articles it was also marked what was the cause of the problem (function/variable names, API or achieved results). Auxiliary variables of the package from GitHub (such as number of stars, subscribers or contributors) were also taken into consideration.

## Results

It turned out, that packages in both versions tend to have the same class of reproducibility. Only 3 out of 18 packages lost their reproducibility rate with updates.

![Feature Correlation Plot](/2020L-WB-Blog/2020-06-09-to-update-or-not-to-update/corPlot.png)

Furthermore, analysing correlation plot above can lead to more conclusions. For instance, number of github stars, subscribers and contributors is strongly negatively correlated with number of result issues. That link might mean, that popular packages do not have problems with results - which explains, why they are popular. On the other hand, the plot shows weaker, but still significant, correlation between these 3 variables and API issues, which may hamper access to the results.

## Conclusions

The research shows, that in most cases, reproducibility is not affected updates, so there is no need to stop actively developing the packages. However, there are some advices, that authors should bear in mind, changing their code. First of all, they should avoid changing names of functions, as it might lead to reproducibility issues. Additionally, when the article gains popularity and authors decide to change it's API, they should carefully rethink the changes, as it may affect reproducibility of not only theirs, but also other researchers work.

## References
1. Ngoc Anh Nguyen, Piotr Piątyszek and Marcin Łukaszyk from Warsaw University of Technology. (2020) How active development affects reproducibility. Warsaw University of Technology

([Link to article](https://mini-pw.github.io/2020L-WB-Book/how-active-development-affects-reproducibility.html))

