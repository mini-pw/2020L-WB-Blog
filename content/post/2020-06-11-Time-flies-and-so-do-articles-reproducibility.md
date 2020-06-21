---
date: "2020-06-11"
title: "Time flies... and so do articles' reproducibility?"
author: ["Jakub Kosterna", "Dawid Przybyliński", "Hanna Zdulska"]
tags:
  - reproducibility
  - interpretability
  - article
---

### Sometimes we forget about what is really important...

Have you ever stopped for a moment in the course of everyday life and looked better at the reproductivity of the scientific article? Have you ever wondered - can I do what authors did in this article and get the same results? If you are not in technical industry - probably not... and it's perfectly fine. Otherwise - it's about time to start getting interested.

### Reproducibility, like wine? Or vice versa?

When publishing a work, you definitely need to remember about few basic rules: correct documentation, ensuring that files are up-to-date etc. However, not everyone respects these rules and hence - some articles sooner or later lose readability, reproductivity and therefore their value. Time flows and it would seem like a reasonable assumption that the older the text, the harder it is to reproduce in nowday's conditions. Will this intuition be true? The topic has been studied recently by three young data scientists from Warsaw University of Technology: Paweł Morgen, Piotr Sieńko and Konrad Welkier. The final conclusions were presented in a scientific article entitled "Aging articles. How time affects reproducibility of scientific papers". Curious about the results? I guarantee you'll be shocked! 

### How to compare reproducibility?

The young authors set correlations as their distinctive element - as one of them wisely said: "The intention of such research is to find correlations between age of article and its reproducibility". Does it makes sense? I think we can all agree that of course yes! The classic correlation measurement for finding similarity is very informative.

There is some discourse about exact definition of reproducibility in scientific community. Authors decided to use definition suggested 16 years ago by famous researchers Robert Gentleman and Duncan Temple Lang -  “reproducible research are papers with accompanying software tools that allow the reader to directly reproduce methods that are presented in the research paper.”

### I give you a grade of 3 - you are the best!

To analyze large number of scientific articles package CodeExtractorR was used - it allowed to save time and keep results reproducible. Authors used 4-step scale to grade papers - they gave marks in order: 0 for absolute non-reproductiveness, 1 for somewhat reproducible, 2 for generally satisfactory and 3 for just perfect. The three wise men also tried to be as objective as they could - all 3 of them graded each article without to minimize their subjectivity.

### Unexpected results

Two hundred and eighty articles from R Journal were analyzed. This is by far the biggest number of analyzed papers in topic of reproducibility and it’s pretty impressive. The results apply only to articles from 2010-2019, which gives almost a decade of scientific progress.
Codes have been reproduced, points were assigned and now it’s time for reveal! To our annoyance the final result turned out to be quite surprising. Huge differences between 2019 and 2010? Not this time. There is not very big differences between today's times and the long long time ago in early 2010s. Maybe it is true that full reproduction in the latest works was present much more often than in the good old days, but the trend is rather only for the era after Stephen Hawkings. Want play an in-depth analysis of bars with a trend unlike anything? Check out the brilliant article of our three men!

### Now we've all become smarter

I think that after this short lesson, we can all came up wise conclusions: the world has not changed so much in the past 10 years, but the matter of reproducibility began to attract much more needed attention. Hopefully in year to come more and more scientific papers will be reproducible.
