---
date: "2020-06-16"
title: "Scientific magazines & reproducibility"
authors: ["Ada Gąssowska", "Mateusz Grzyb", "Elżbieta Jowik"]
tags:
- reproducibility
- magazines
---

One cannot help but notice that science is suffering from a reproducibility crisis. The problem is not only the subject of academic considerations, but much more global. The inability of scientists to recreate and reproduce one anothers' results increases demands on resources and drives up research costs as well as their time consumption. Mikołaj Malec, Maciej Paczóski and Bartosz Rożek explored this subject in their article. 

## First look at the article

The article  titled  *ML Case Studies*: *Ways to reproduce articles in terms of release date and magazine*, describes well some new approach to the issue, taking  under consideration three well known scientific journals: *R Journal*, *JMLR Machine Learning Open Source Software* and *Journal of Statistical Software*. As the main accompanying assumption, the authors concluded that the article is reproducible, if the results published can be independently reproduced by readers. Their article defines features that incense the reproducibility of published results as well as the ones that impede it. The autors also emphasize that their main goal was to create a list of rules that improve and enable reproducibility. They had divided the magazines between themselves, so that each one of them was taking care of one of the journals. While going through them they were looking for the features which would make the articles in them more reproducible, for example the availability of the code, data and packages used to create the examples present in the article. 

## Analysis of the journals

In the subsequent parts of their article, the authors present some of their observations and conclusions about the three journals mentioned before. The first one, *R Journal*,is one of the main journals covering topics which could be of interest to developers and users of R language. As its advantages related to reproducibility, the authors state its clear page, its user-friendly archives, and the fact that each article has its own short description and a list of nescessary CRAN packages. The last one however brings out one of the problems - many of the CRAN packages don't have the current version available, or worse, are permamently removed from there, which obviously makes reproducing of such an article simply impossible. The authors included a plot which shows the mean percentage of the packages available for articles from different years. What came as a surprise for us, was that the articles from recent years, do not come out better than the other ones. The important thing to acknowlage is that the magazine is aware of the reproducibility problem, as it brings out this problem on its main page. As one of the solutions, in 2016 they introduced the possibility to contain supplementary materials in the article, and since that year the number of articles with that kind of additional files grows.


The second journal brought by the authors is the *Journal of Statistical Software*, which even states on its page that its articles are easy to reproduce. Even though it is not true for all of them, the percentage of the CRAN packages still available for each year, turns out to be higher than for *R Journal* articles. For the ones that came out during this year, this number is almost 100% which is a great improvement comparing to the journal that was brought before. However, one of the things that may make the articles more difficult to reproduce is that it is impossible to change the code after the article has been published. Therefore, the journal encourages that the reposiories are linked to each article. The authors also pointed out the interesting fact, that during the years of its exitance the articles about R packages have become the majority. Fortunately it didin't come with lower reproducibility rate. However the thing that actually has worsen since the launching of the journal is the number of days from submission to publication. 

The last journal mentioned in the article  is *The Journal of Machine Learning Research*. Although the magazine adiminstrators encourage authors to include code in their articles, many of them do not apply for it, which automatically makes these articles unreproducible. Fourtunately since 2011 many of them started to link their github repositories, and the number of the articles with code seems to be growing, as shown by the authors on the charts. 

## Conclusions & our opinion

The authors pointed out the most important (in their opinion) features, which can lead to boost of the reproducibility of the articles. This include the availability of the code and data, providing links to the repositories on github, and keeping this repositories current. The other good ideas are to include the contact to the writer. However, in our opinion the best idea proposed by the authors is that the journal administrators should provide the information whether the article is reproducible or not (for example by adding the information if all of the CRAN packages needed in the code are available). If you are R user, you know how often the code found in some article just won't work no matter how many hours you spend trying to find and solve the problem. The information that some of the packages are just not available anymore would make our work so much easier. 

As we stated before, this article brings out many interesting and useful information. The only thing that we would change, is that each of the journals were treated in a slightly different way, and different statistics and numbers were provided. This makes it hard to compare all three of them. However the ideas proposed in the end were very creative, and can really contribute to us making our own articles in the future much more reproducible.




















