---
layout: post
title: "Detecting Sarcasm with Deep Convolutional Neural Networks"
author: "Elvis"
excerpt: ""
modified:
comments: true
tags: [Artificial Intelligence,Technology,Deep Learning,Machine Learning,NLP]
image:
  thumb: lm-progress.png
---

\\
_ **Overview** _
 This paper addresses a key NLP problem known as _sarcasm detection_ using a combination of models based on convolutional neural networks (CNNs). Detection of sarcasm is important in other areas such as affective computing and sentiment analysis because such expressions can flip the polarity of a sentence.
 
\\
_ **Example** _
 Sarcasm can be considered as expressing a _bitter gibe_ or _taunt_. Examples include statements such as &quot;Is it time for your medication or mine?&quot; and &quot;I work 40 hours a week to be this poor&quot;. (Find more fun examples [here](http://examples.yourdictionary.com/examples-of-sarcasm.html))
 
\\
_ **Challenges** _
 To understand and detect sarcasm it is important to understand the _facts_ related to an event. This allows for _detection of contradiction_ between the objective polarity (usually negative) and the _sarcastic characteristics_ conveyed by the author (usually positive).

\\
Consider the example, &quot;I love the pain of breakup&quot;, it is difficult to extract the knowledge needed to detect if there is sarcasm in this statement. In the example, &quot;I love the pain&quot; provides knowledge of the sentiment expressed by the author (in this case positive), and &quot;breakup&quot; describes a contradicting sentiment (that of negative).

\\
Other challenges that exist in understanding sarcastic statements is the reference to multiple events and the need to extract a large amount of facts, commonsense knowledge, anaphora resolution, and logical reasoning. The authors avoid automatic feature extraction and rely on CNNs to automatically learn features from a sarcasm dataset.

\\
_ **Contributions** _

- Apply deep learning to sarcasm detection
- Leverage user profiling, emotion, and sentiment features for sarcasm detection
- Apply pre-trained models for automatic feature extraction

\\
_ **Model** _
_Sentiment shifting_ is prevalent in sarcasm-related communication; thus, the authors propose to first train a sentiment model (based on a CNN) for learning sentiment-specific feature extraction. The model learns local features in lower layers which are then converted into global features in the higher layers. The authors observe that sarcastic expressions are user-specific — some users post more sarcasm than others.

\\
In the proposed framework, personality-based features, sentiment features, and emotion-based features are incorporated into the sarcasm detection framework. Each set of features are learned by separate models, becoming pre-trained models used to extract sarcasm-related features from a dataset.

\\
_ **CNN Framework** _
 CNNs are effective at modeling hierarchy of local features to learn more global features, which is essential to _learn context_. Sentences are represented using word vectors (embeddings) and provided as input. Google&#39;s word2vec vectors are employed as input. Non-static representations are used, therefore, parameters for these word vectors are learned during the training phase. Max pooling is then applied to the feature maps to generate features. A fully connected layer is applied followed by a softmax layer for outputting the final prediction. (See diagram of the CNN-based architecture below)
 
\\
![](https://miro.medium.com/max/903/0*GVbW_tOQMN1F1lcw.)

\\
To obtain the other features — sentiment (S), emotion (E), and personality (P) — CNN models are pre-trained and used to extract features from the sarcasm datasets. Different training datasets were used to train each model. (Refer to paper for more details)

\\
Two classifiers are tested — a pure CNN classifier (_CNN_) and CNN-extracted features fed to an SVM classifier (_CNN-SVM_).

\\
A separate baseline classifier (B) — consisting of only the CNN model without the incorporation of the other models (e.g., emotion and sentiment) — is trained as well.

\\
_ **Experiments** _
**Data** — Balanced and imbalanced sarcastic tweets datasets were obtained from ([Ptacek et al., 2014](https://pdfs.semanticscholar.org/0c27/64756299a82659605b132aef9159f61a4171.pdf)) and [The Sarcasm Detector](http://thesarcasmdetector.com/). Usernames, URLs, and hashtags are removed, and the NLTK Twitter Tokenizer was used for tokenization. (See paper for more details)

\\
The performances of both the CNN and CNN-SVM classifier, when applied to all datasets, are shown in the table below. We can observe that when the models (specifically CNN-SVM) combine sarcasm features, emotion features, sentiment features, and personality traits features, it outperforms all the other models with the exception of the baseline model (B).

\\
![](https://miro.medium.com/max/910/0*7C9n-YwbYTcdyjWn.)

\\
The table below shows comparison results of the the state-of-the-art model (method 1), other well-known sarcasm detection research (method 2), and the proposed model (method 3). The proposed model consistently outperforms all the other models.

\\
![](https://miro.medium.com/max/913/0*nEZQfG6A-0jFJSTp.)

\\
Generalizability capabilities of the models were tested and the main finding was that if the datasets differed in nature, this significantly impacted the results. (See visualization of the datasets rendered via PCA below). For instance, training was done on Dataset 1 and tested on Dataset 2; the F1-score of the model was 33.05%, significantly dropping in accuracy.

\\
![](https://miro.medium.com/max/917/0*XMsGxMm3GiHfJ2sz.)

\\
_ **Conclusion and Future Work** _

\\
- Overall, the authors found that sarcasm is very _topic-dependent_ and _highly contextual_, therefore, sentiment and other contextual clues help to detect sarcasm from text. Pre-trained sentiment, emotion, and personality models are used to capture contextualized information from text.
- Hand-crafted features (e.g., n-grams), though somewhat useful for sarcasm detection, will produce very sparse feature vector representations. For those reasons, word embeddings are used as input features.

\\
_ **References** _
 Ref: [https://arxiv.org/abs/1610.08815](https://arxiv.org/abs/1610.08815) — &quot;A Deeper Look into Sarcastic Tweets Using Deep Convolutional Neural Networks&quot;

\\
You can find an interesting discussion of this post on Reddit [here](https://www.reddit.com/r/MachineLearning/comments/8fzkwc/r_detecting_sarcasm_with_deep_convolutional/).


------------

\\

👋_Wait! Here is more if you want to continue reading similar research:_ [Detecting Emotions with CNN Fusion Models](https://medium.com/dair-ai/detecting-emotions-with-cnn-fusion-models-b066944969c8)