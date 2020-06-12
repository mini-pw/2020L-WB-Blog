---
date: "2020-06-11"
title: Beat the Black Box!
authors: ["Kacper Staroń, Jakub Szypuła"]
tags:
- interpretability
- XAI
- automated regression
---


## Understanding things is good for your health

There is no doubt we live in a world defined by data. In fact, we always were, only now we've got a wider variety of tools at our disposal to store and process all this information. We no longer need to search for structures in data by hand, we've got models and AI for this. However, we still want, or rather feel urge to, understand how all those analysis work. Especially when we're talking about our health data, and that is what authors of ["Can Automated Regression beat linear model?"](https://mini-pw.github.io/2020L-WB-Book/can-automated-regression-beat-linear-model.html) are talking about.


## This model's great, why would I want another one?

There is no clear definition of interpretability when it comes to ML models. The one used in Granat's and Maksymiuk's work essentially means that we call the model interpretable if it is possible to determine what contributed to the model's answer. This definition is without a doubt met by Automated Regression, a solution presented in the article as an alternative to H20 AutoML Model. But why would we seek an alternative for based on GBM and performing quite nicely linear regression model?
Because it's the so called black-box. We know the model works for certain data, yet there are crucial parts of the process we can't fully explain while analyzing the model's output. It does not have to be troubling, and it often is accepted as just a part of the solution, however there are times when understanding how every variable contributes to final answer is just as important as the solution itself. I think we can all agree that when it comes to keeping tabs on our health condition, automated diagnosis systems and such, we'd like to know that all those complicated algorithms "do their job" rather than "seem to work just fine". 
That's why authors decided to compare their model with a black box one to check if interpretable Automated Regression can beat mysterious H20. And what's better dataset for this friendly competition than "real high stakes" medical data concerning liver disorders?  


## Improve your model in 4 ~~simple~~ steps

The authors went on to explain how they could increase the efficiency of their model. It consisted of 4 separate stages, that we won't describe. After all, it's already been written in the article, so there's little point in repeating what has already been said.
Their 4 stage improvement included measuring score with two different loss functions, $$L_{0}$$ and $$L_{R}$$. What it means is pretty much "the lower the score, the better". Other than that, they further subdivided the results with regard to feature concatenation. At first, it wasn't much of a difference, but boy, did it make difference in latter stages.
[14:54]

## But were they able to Beat the Black Box?

Yes, they were! But was it a complete victory? Well, for the most part.
The aforementioned loss function showed, that their baseline had already been better than the black box. There's one important question though. Is this loss that is the sole metric by which we can measure success? Well, not exactly, as mentioned by the authors, there's also the variance explained by the model. Also, there's no reason to just say "ah yes, it's 1.7% better" and call it a day. So they did the 4-stages improvement and the results are below. 

|            Model           | Baseline | Stage 1 | Stage 2 | Stage 3 | Stage 4 | Black-Box | R squared |
|:--------------------------:|:--------:|:-------:|:-------:|:-------:|:-------:|:---------:|:---------:|
|   $$L_{0}$$ \| With concat.  |   2.680  |  2.660  |  2.613  |  2.594  |  2.533  |   2.727   |   0.193   |
|   $$L_{R}$$ \| With concat.  |   2.680  |  2.660  |  2.613  |  2.670  |  2.734  |   2.727   |   0.231   |
| $$L_{0}$$ \| Without concat. |   2.680  |  2.660  |  2.613  |  2.594  |    -    |   2.727   |   0.171   |
| $$L_{R}$$ \| Without concat. |   2.680  |  2.660  |  2.613  |  2.670  |    -    |   2.727   |   0.193   |





The score going down can be described with a scientific term "nice", and it going up as "bad", while it going up again to surpass the black-box would be "pretty bad". But it's hard to tell how "bad" it actually is, since it somewhat balances with the "pretty nice" score of the $$L_{0}$$ function for stage 4. This trade-off is pretty complicated and probably it depends whether it's "nice" or "bad"
But none the less, save for one score being 0.25% worse, the Automated Regression proves to be better than the black box for this task. As authors note, it's still unproven for the larger datasets, but they look forward to large dataset extension. In my opinion, it's good that the interpretable model won with the non-interpretable one, especially when it comes to the medical field. It just feels safer, since, unlike the black box, we know *why* it diagnosed the patient. Imagine if the patient would ask "doctor, why was I diagnosed", and the doctor said "well I don't know I'm not the algorithm haha".
To sum it all up:
Yes, they beat the black box. And I hope they beat it again in the future.
