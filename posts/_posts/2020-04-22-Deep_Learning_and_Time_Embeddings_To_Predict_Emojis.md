---
layout: post
title: "Deep Learning and Time Embeddings To Predict Emojis"
author: billy_rick
excerpt: "This paper investigates the usage and semantics of emojis over time to analyze seasonal variation of emoji usage and emoji prediction model based on the time information..."
modified:
comments: true
tags: ""
image:
  thumb: emoji_prediction.png
---

### Overview

Emoji usage has become a new form of social communication, which is important because it can help to improve communication systems, such as chat applications. This paper investigates the usage and semantics of *emojis* over time to analyze *seasonal variation* of emoji usage. In addition, they develop an emoji prediction model based on the time information.

### Contribution

Multiple emoji predictions studies have been carried out in the past (see notable work by [Felbo et al., 2017](https://arxiv.org/abs/1708.00524)), but non have considered *temporal information*. Temporal correlation between emojis and seasonal events are explored and used to disambiguate emoji meanings.

### Example

Consider the leaf clover emoji (🍀), it is usually associated with good luck wishes all year round except in March, where it is mostly used to express event situations related to *parties* and *drinking* (due to St. Patrick day).

### Challenges

- This study demonstrates that temporal information is useful for emoji prediction even for emojis that are not associated with time (💪 and ❤️).
- Emojis are innately subjective, which is why it is difficult to analyze their *semantic meaning*.

### Dataset

Twitter is used to collect a 100 million US tweets corpus and organized as follows:

- *Seasonal Emoji Dataset* — data is divided into four subsets by seasons: Spring, Summer, Autumn, and Winter (see figure below)
- *Emoji Prediction Dataset* — data is reduced to tweets that only contain one frequent emoji (emoji must belong to the 300 frequent emojis)

\\
![](https://miro.medium.com/max/667/0*cY0NhSgVUqnbRvYR.png)

### Seasonal Emoji Semantic and Usage

Skip-gram word embedding models are trained using the four subsets of the seasonal datasets. These models provide information that basically helps to describe emojis in terms of their semantic similarity to each other. (See paper for more details)

\\
By comparing the top 10 emojis associated to each emoji in the embedding space, it was discovered that emojis related to music, animal, sweets, and emotions were not influenced by seasonality (e.g., 🎶, 🎼, 🍦, 🐠, 😂, 🎸). This means that these emojis preserved meaning across seasons.

\\
In contrast, sport-related emojis (e.g., 🏀, 🏆) varied in meaning across seasons, probably due to the high-peak seasons when sports are played. Another interesting emoji related to school (🎓), changed meaning across seasons; during Spring it was associated with party emojis, and during Autumn it was associated with school-related emojis. Check out the top 10 associated emojis per season for the pine emoji (🌲) in the figure below — very season-dependent don’t you think? Can you guess why? (hint: outdoors vs Christmas). (See paper for tons of interesting findings)

\\
![](https://miro.medium.com/max/686/0*HTDh_nso9HotCLBl.png)

### Emoji Prediction

The second dataset, which includes 300 emoji classes and 900,000 tweets total (3,000 tweets per class), is used for emoji prediction. The architecture of the emoji prediction model is as follows: character embeddings, word embeddings, and data embeddings are combined through both an early fusion approach and a late fusion approach. This produces two models (***Early*** and ***Late***). A third model is trained (***W/O***) which completely ignores the date embeddings. (See paper to find out how these embeddings are constructed)

\\
![](https://miro.medium.com/max/737/1*wj6vTSX9Tsg2H6NKAN4mKw.png)

### Results

Precision, Recall, and F1 scores are reported for all models in the table below. We can observe that by combining time information using early fusion, the *Early* model outperforms the other models.

\\
![](https://miro.medium.com/max/373/1*ddC9ymdyY7djnnVUwvr-tg.png)

\\
The emojis that had higher gains in F1 score (without date vs. early date) are presented in the table below. You can definitely observe that many emojis are season-specific (e.g., 🍀, 🌒) and thus benefit from the date embeddings. Even emojis that are not associated to time (e.g., 🖤, ❤️, 💪) benefit from the temporal information.

\\
![](https://miro.medium.com/max/379/1*Pi5d5FTmh8ETasilC8a24g.png)


### Conclusion & Future Work

- A multimodal architecture was proposed to conduct emoji prediction based on deep neural networks.
- More analysis on the emoji semantics and usage over specific time of the day or week may be able to help improve the date embeddings and the overall predictive models.
- This work has a lot of room for improvement and it could be a very interesting topic to combine with emotion recognition, event detection, and computational health studies.

### References

- Ref: [https://arxiv.org/abs/1805.00731](https://arxiv.org/abs/1805.00731) — “Exploring Emoji Usage and Prediction Through a Temporal Variation Lens”
