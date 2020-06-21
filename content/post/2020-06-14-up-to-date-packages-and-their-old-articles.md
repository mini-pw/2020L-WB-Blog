---
date: "2020-06-14"
title:  Up-to-date packages and their old articles
authors: ["Jan Borowski", "Filip Chrzuszcz", "Piotr Fic"]
tags:
- reproducibility
- R packages
- scientific papers
---

### Intro

The reproducibility of science paper is a huge and important problem. Today we will not talk about one part of that problem. What if after publishing article researchers still develop their packages changing function, optimize, etc. In the discussed article researcher focused on this particular situation. They selected articles where used package was still developed until today and check reproducibility. Thay use code in the selected article and check if it is possible to run it today. You will be surprised at how many levels of reproducibility can be distinct.

### Methodology

In order to fully understand the topic authors decided to analyze 13 articles which use 16 different R packages.
The aim is to check whether code used in these articles still can be used and does it give good results. To categorize efforts, authors proposed 5 categories ranging from 'FULLY REP', which means that this chunk can be used without any troubles and give the expected result, up to 'NO REP', what obviously means that code is not working.
During practical work with the data, authors have stumbled upon a few problems, because not all cases could have fit into their categories. For example, if some chunks were dependant on other parts of code, which was already deprecated or unable to reach, they decided to mark this as 'NO REP'. If needed changes were not significant, ex. changing names of columns or replacing a few rows, then that article was marked as 'HAD TO CHANGE STH', or even 'FULLY REP', which meant that it can be easily used.

### What have we learned?

After presenting the research methodology, the authors present its result. The most informative summary is the plot shown below.  

![Wyniki badania](/2020L-WB-Blog/2020-06-14-up-to-date-packages-and-their-old-articles/plot2.png)  

We can clearly see that most of the examined articles are fully or mostly reproducible. This is very good news. We are informed that 93.4% of code chunks worked well enough to not throw errors. On the other hand, only 6.6% of them were completely irreproducible. Let's remind that all articles are at least 10 years old! Authors highlighted that their research concerns only packages that are still updated. We cannot say that all 10 years old articles are reproducible. Evolution of packages usually haven't changed their main aims of usage but rather added new features or functions. The biggest troubles were caused by missing of external data or changes in R language itself. To sum up authors claim that examined packages were mostly fully backwards compatible, what should make us happy.