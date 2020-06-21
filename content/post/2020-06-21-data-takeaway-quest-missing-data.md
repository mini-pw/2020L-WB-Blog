---
date: "2020-06-20"
title: "Data for Takeaway: A Quest for the Missing Data"
authors: ["Mateusz Bąkała", "Michał Pastuszka", "Karol Pysiak"]
tags:
- imputation
- missing data
- machine learning
- story
- entertainment
---

The weather in Grantue wasn't the most pleasant that day. Mostly misty, but here and there it was raining. No-one could be seen on the streets, though it had more to do with the recent outbreak of a disease and the general reluctance of the Grantue citizens to go out unless absolutely necessary. But I, I actually liked that high humidity, lack of wind and vague temperature.

And there I was, with soaked glasses in the pockets, returning home from the meeting that could have taken place on a videoconference but didn't. I was angry, but every droplet of rain reduced my anger a bit and when I finally got home, I was already calmed, leaving a path of angry droplets behind me.

As soon as I got through the door, I tossed my bag across the room. It landed perfectly in the corner of the sofa, albeit rather ungently. Luckily, I already damaged or broke whatever was inside and could be broken.

"What's up?", I asked.

"A ceiling, a sky, a star or a billion," Alison replied, not trying to mask her discontent with such uninspired greeting. "Be more specific, pretty please?"

"If you say so, I might have a question for you. A challenge, dare I say," I added, to spark her curiosity. Indeed, her curiosity was sparked and immediately proceeded to trace down and exterminate Alison's cat. We left them both alone, we didn't like the cat anyways.

I reached for the laptop, knowing it would be necessary for solving the problem I faced.

"I have some data and some machine learning to put together," I began, "but it just wouldn't work. Those pesky errors just keep appearing and I don't know how to get rid of them. Like, completely and for good."

Alison coughed with impatience. Right, specificity still missing.

"You're good with R, do I remember correctly?" I asked. Alison nodded, so I continued, "Here, I ran this snippet and it says there are some missing values. What would you do?"

Alison shrugged. "Get rid of 'em, as simple as that. I've just read an article on that this mornin', that's gotta help a bit."

"Wow, just as if we were characters in a story and the author needed it to push the plot ahead."

"Oh, c'mon, that's a stupid idea."

I responded by typing and executing:

```r
rm(NA)
```

While my roommate was staring in some kind of weird awe and the kitten was screaming in agony, RStudio threw an error.

"Seems I'll need your ideas, Allie."

"I'm delighted and terrified at the same time," she commented. "Lemme tell ya how it's done. Firstly, ya can't just remove 'em and leave the rest, gotta either delete whole row or column, or replace 'em with some values."

I was all ears already. <!-- The cat as well, curiosity already had eaten the rest of it. -->

"I guess ya'd rather not delete data," she continued, taking over the laptop and some local ship-building company. "A data imputation then. Just have to decide on the method used. And it was all 'bout it in that article. It's even in the title."

"Which is...?" I inquired.

"Quite lengthy," Alison replied. "Comparison of performance of data imputation methods in the context of their impact on the prediction efficiency of classification algorithms. Must've been written by a bunch of hyper-precise minds."

"And which method is the best?"

"It ain't that straighforward."

"Twistbackward then?"

"No, there's no such word."

"Well, I just created it."

"But did ya give it a meaning?"

"Whatever meaning is appropriate here."

"So ya coulda just say 'arquisteiny' and use the same reasoning."

"Do we have a minimum word limit to pass or what?"

Alison gave me an irritated look, but I could see that deep inside she enjoyed this little struggle.

"Well," she said, trying to take the intercourse to where it was just a while ago. "As I almost said, there ain't no way to indicate one best method, but some are better than the others. In this article they compared six methods using several measures." Alison gave me a quick look. "To name a few, AUC, BACC, BBC, OBFS, MCC, and MC Hammer."

"I know you made them up, but all of them or just some?"

"Yeah, the last one made it too obvious," she confessed. "The first two are legit... and the penultimate as well."

"And the measures?" I asked, reaching for an orange juice.

"Oh, those were measures. I did a little switcharoo there."

I changed my mind and decided to go for a grapefruit juice instead.

"These measures are median or mode, dependin' on the type of the variable, mice, missRanger, softImpute, kNN and hotdeck."

My glance spotted an already opened bottle of apple juice, so I suddenly began to hesitate.

"But how they exactly work isn't important there, they're all implemented in R."

There was only half a glass of apple juice, so I took it all and filled the rest of the glass with the remaining juices, creating the ultimate juice mix.

"What we need is which one will be the best in your case. And not too slow."

I took a sip and liked it, so I quickly drank it all.

"They tested 'em on ten datasets and the results are here."

Drinking too much at once made me feel dizzy, so I suggested, "Maybe we could discuss this on the outside? Lightnings are quite rare at the moment, so the probability of being hurt or killed by one is manageable. Also, I need me some humidity."

Alison puffed her lips out, shrugged, donated a few bucks to a charity and agreed to the idea. On our way out she took an umbrella, just in case, and I couldn't blame her. For that at least.

Wandering through misty streets of Grantue we saw an abandoned dog. It was covered in a black, sticky mud, but he smelled sweet, like the cookies my mom always baked on the day before the day before Christmas Eve, as well as the day before Christmas Eve, whenever the former happened to be Thursday. When we came closer little buddy started waving his tail, splashing the dirt all over us. It had been so pleasing to see his happy face in this dark, cold part of the world, but now, drowning in mud, the pleasure was slowly drifting away.

"Shouldn't we've been done talkin' 'bout that imputation already?" marked Alison.

I simply couldn't deny that saying I don't disagree wouldn't be a lie.

"Long story short, basic algorithms were doin' very well."

"Median?" I asked to make sure.

"And mode," she clarified. "For kNN, they were indisputably the best choice. For the others... Well, missRanger performed a bit better. However..."

The dog saw an equally abandoned cat and with a loud growl quickly ran off into the everpresent darkness, taking with itself that poetic mood, provoking to describe everything with a pathos and grandiloquence.

"...however it takes quite a while to compute, about a hundred times as much as median and mode. Is it worth it? Gotta be sceptic."

"So do you recommend... what?"

"The pure simplicity. Unless ya really need your accuracy."

I looked around, thinking intensively about what I just heard.

"So, tell me one thing... Why?"

Confused Alison noises could be heard. They seemed to be saying, "What why?"

"Why do they try and create algorithms that take a lot more time and perform equally good or even worse?"

Suddenly, a freezing wind started blowing, out of nowhere, by some called "East". Dogs, cats, rats hid and pigs stopped flying. The darkess was brightening. The whole world -- or at least the city of Grantue -- held its breath in the anticipation.

Alison took her sweet time to answer.

"Guess they must be mathematicians."
