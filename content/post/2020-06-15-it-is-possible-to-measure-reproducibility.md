---
date: "2020-06-15"
title: It is possible to measure reproducibility?
authors: ["Jakub Pingielski","Paulina Przybyłek","Renata Rólkiewicz","Jakub Wiśniewski"]
tags:
- ML
- reproducibility
- article rating
- The R Journal
---

# It works on my machine
Have you ever founds some great pieces of software only to realize that the code provided by the developer does not work anymore? \
The problem of software reproducibility in scientific research is becoming more and more important as number of new packages increases exponentially.
But the problem is even more complex - there are not only strictly reproducible or irreproducible projects but also some that fall in between.
That is why a zero-one rating, which is common approach to measure reproducibility, may be misleading. 

# One metric to rule them all
To enable comparison between different software, in [this](https://mini-pw.github.io/2020L-WB-Book/how-to-measure-reproducibility-classification-of-problems-with-reproducing-scientific-papers.html) article group of students from the Warsaw University of Technology analyzed packages
published in `The R Journal` and developed a 6-point scale to measure reproducibility of the article based on six main categories of problems
that can be faced while trying to reproduce scientific paper results:

* no access to external resources
* no compatibility with current versions of used packages
* code vulnerable to user settings
* additional configuration required
* randomness problems
* no access to source codes

# It is harder than you think
Most of the analyzed articles were reproducible to some extent, but many suffer because of the fact that the whole package depended on one specific function that was causing problems. Moreover, some developers didn't provide any source code for the figures used in the article. 
Fortunately in the majority of the articles outdated code didn't have a big impact on core results, but was merely an inconvenience.

# 404 Code Not Found

![Summary of marking articles](/2020L-WB-Blog/2020-06-15-it-is-possible-to-measure-reproducibility/Summary_of_marking_articles.png)

Interestingly, it turns out that the most common problem with reproducibility was code availability. One might only guess that it was caused by
developers' sloppiness, not malice. Less surprising is the fact that many packages were heavily dependent on specific versions of software and required
additional configuration to work properly. On the other hand, dependency on external resources turned out to be the least common problem.

# Small step in the right direction
Even though the sample size was small - only 16 scientific papers were analyzed, and points were assigned subjectively (but were assigned independently but at least two people), survey carried out amongst fellow students suggests that proposed metric is more suitable for curious researchers that want to try and use some obscure software.











