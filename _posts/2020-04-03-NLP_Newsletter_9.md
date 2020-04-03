---
layout: post
title: "NLP Newsletter #9: Illustrated GNN Guide, TextVQA and TextCaps, KeraStroke, SyferText, torchlayers,…"
author: billy_rick
excerpt: "This issue includes topics that range from a privacy-preserving NLP tool to interactive tools for searching COVID-19 related papers to an illustrated guide to graph neural networks."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_9.png
---


![](https://cdn-images-1.medium.com/max/1200/1*Vq-bFSTjqYjDGAR4Ja1abw.png)

\\
Welcome to the 9th issue of the NLP Newsletter. We hope that you and your loved ones are well and staying safe. This issue includes topics that range from a privacy-preserving NLP tool to interactive tools for searching COVID-19 related papers to an illustrated guide to graph neural networks.


# Research and Publications 📙

***Neuroevolution of Self-Interpretable Agents***

\\
Tang et al. (2020) present an interesting and creative [work](https://attentionagent.github.io/) that aims to evolve an agent to take a fraction of its visual input with the goal to survive a task (e.g. avoid crashing on a curve and dodging fireballs, as seen in the figure below). Using [neuroevolution](https://en.wikipedia.org/wiki/Neuroevolution) to train *self-attention architectures,* the authors were able to train reinforcement learning agents to perform different tasks while only allowing a fraction of the input. The benefits of the model include a substantial reduction in the size of parameters, policy interpretability, and enabling the model to attend to only the t*ask-critical visual hints.*

\\
![](https://cdn-images-1.medium.com/max/800/1*Gm8jlCUvP_JECEPspDypWg.png)

\\
***Introducing RONEC — the Romanian Named Entity Corpus***

\\
[RONEC](https://arxiv.org/abs/1909.01247) is a named entity corpus for the Romanian language that contains over 26000 entities in ~5000 annotated sentences, belonging to 16 distinct classes. The sentences have been extracted from a copy-right free newspaper, covering several styles. This corpus represents the first initiative in the Romanian language space specifically targeted for named entity recognition. It is available in BIO and CoNLL-U Plus formats, and it is free to use and extend [here](https://github.com/dumitrescustefan/ronec).

\\
***Scaling Laws for Neural Language Models***

\\
Researchers from John Hopkins and OpenAI have conducted an empirical [study](https://arxiv.org/abs/2001.08361) to understand the scaling laws for language model performance. This type of study can be used as a guide to making better decisions on how to more effectively use resources. Overall, it was found that larger models are significantly more sample-efficient; if there is limited compute and data, it is better to train a large model with a few steps of training as opposed to training a smaller model until it converges (see results summarized in the figure below). Authors provide more findings and recommendations when training large language models (e.g. Transformers) in the aspects of overfitting, choosing the optimal batch size, fine-tuning, architecture decisions, etc.

\\
![](https://cdn-images-1.medium.com/max/800/1*plbjqswVe4Cq8UVggqPH1w.png)

[*Kaplan et al. (2020)*](https://arxiv.org/abs/2001.08361)

\\
***Calibration of Pre-trained Transformers***

\\
With pre-trained Transformers being used increasingly in real-world applications, it is important to understand how *trustworthy* their outputs are. Recent [work](https://arxiv.org/abs/2003.07892) by UT Austin shows BERT and RoBERTa’s posterior probabilities are relatively calibrated (i.e., consistent with empirical outcomes) on three tasks (natural language inference, paraphrase detection, commonsense reasoning) with both in-domain and challenging out-of-domain datasets. Results show that: (1) when used out-of-the-box, pre-trained models are calibrated in-domain; and (2) temperature scaling is effective at further reducing calibration error in-domain, while label smoothing to increase empirical uncertainty helps calibrate posteriors out-of-domain.

\\
![](https://cdn-images-1.medium.com/max/800/1*ose0s-G0WfPFoleZJ1htrQ.png)

[*Desai and Durrett (2020)*](https://arxiv.org/pdf/2003.07892.pdf)

\\
***Statistical Mechanics of Deep Learning***

\\
A recent [paper](https://www.annualreviews.org/doi/abs/10.1146/annurev-conmatphys-031119-050745) takes a closer look at the connection between physical/mathematical topics and deep learning. The authors aim to discuss deeper topics intersecting statistical mechanics and machine learning with the objective of answering questions that help to understand the theoretical side of deep neural networks and why they have been successful.

\\
***Towards an ImageNet Moment for Speech-to-Text***

\\
In a new [article](https://thegradient.pub/towards-an-imagenet-moment-for-speech-to-text/) published in The Gradient, Alexander Veysov explains why they believe that the ImageNet moment for Speech-to-Text (STT) has arrived in the context of the Russian Language. In the last couple of years, researchers have also made this claim about NLP. However, in order to achieve such a moment in STT, Alexander claims that many pieces have to come together, such as making models widely available, minimize computational requirements and improve the accessibility of pre-trained large models.


# Creativity, Ethics, and Society 🌎

***Browsing and searching COVID-19 related articles***

\\
Last week we featured a public dataset called [CORD-19](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) which contains COVID-related papers. Gabriele Sarti wrote an [interactive tool](https://github.com/gsarti/covid-papers-browser) that allows you to more efficiently search and browse through these papers by leveraging a [SciBERT fine-tuned model](https://huggingface.co/gsarti/scibert-nli).

\\
![](https://cdn-images-1.medium.com/max/800/0*tu8nzUIEuSizuW5-.gif)

\\
reciTAL has also released a project called [COVID-19 Smart Search Engine](https://covidsmartsearch.recital.ai/) to help improve search and browse on COVID-19 related articles with the goal to help researchers and healthcare professionals to quickly and efficiently find and discover information related to COVID-19.

\\
![](https://cdn-images-1.medium.com/max/800/1*Y5W3sib4y6UxSr3YkQSu5Q.png)

\\
***SyferText***

\\
OpenMined releases [SyferText](https://github.com/OpenMined/SyferText), a new privacy-preserving NLP library that aims to enable secure and private NLP and processing of text for private datasets. It is in its early stages but we believe this is a very important effort towards safer and ethical AI systems. Here are some [tutorials](https://github.com/OpenMined/SyferText/tree/master/tutorials) to get started.

\\
***David over Goliath: towards smaller models for cheaper, faster, and greener NLP***

\\
Is bigger always better? When looking at the evolution of language model size in the past few years, one may think the answer is yes. Yet, the financial and environmental cost of training such monsters is very high. Also, bigger in this case usually means slower, but speed is critical in most applications. This motivates the current trend in NLP pushing for smaller, faster, and greener models while preserving performance. In this blog post, [Manuel Tonneau](https://www.linkedin.com/in/ACoAABs605YB_jMmGA0iLFongpVm1iKjFmKLSts/) presents this new trend favoring smaller models focusing on three recent and popular models, DistilBERT from [Hugging Face](https://www.linkedin.com/company/huggingface/), PD-BERT from [Google](https://www.linkedin.com/company/google/) and BERT-of-Theseus from [Microsoft](https://www.linkedin.com/company/microsoft/).

\\
***A Survey of Deep Learning for Scientific Discovery***

\\
Many of the large companies today that have focused efforts in AI research believe that deep learning can be used as a tool for scientific discovery. This [paper](https://arxiv.org/abs/2003.11755) provides a comprehensive overview of the commonly used deep learning models for different scientific use cases. The paper also shares implementation tips, tutorials, other research summaries, and tools.


# Tools and Datasets ⚙️

***TextVQA and TextCaps***

\\
In an effort to encourage building models that can better detect and read the text in images and further reason about it to answer questions and generate captions, Facebook AI is hosting two separate competitions. The competitions are called [TextVQA](https://textvqa.org/challenge) Challenge and [TextCaps](https://textvqa.org/textcaps/challenge) Challenge to address the visual question answering and caption generation tasks, respectively.

\\
***KeraStroke***

\\
One of the largest hurdles to overcome while designing neural nets is overfitting. Current generalization-improvement techniques such as Dropout, Regularization, and Early Stopping are very effective for most use cases, however, they can tend to fall short when using large models or smaller datasets. In response to this, Charles Averill has developed [KeraStroke](https://pypi.org/project/kerastroke/#description), a novel generalization-improvement technique suite useful for large models or small datasets. By altering weight values in certain cases during training, models dynamically adapt to the training data they’re being fed.


\\
***torchlayers***

\\
[torchlayers](https://github.com/szymonmaszke/torchlayers) is a new tool built on top of PyTorch that allows for automatic shape and dimensionality inference of layers available in the torch.nn module such as convolutional, recurrent, transformer, etc. This means that you don’t need to explicitly define the shape of input features which has to be specified manually in the layers. This simplifies a model’s definition in PyTorch. See an example of a basic classifier implemented with torchlayers below:

\\
![](https://cdn-images-1.medium.com/max/800/1*tHOme2pZ39sNziqdUCsn4g.png)

*We can see from the code snippet that the Linear layer only requires the size of output features as opposed to both the output and input size. This is inferred by the torchlayers based on the input size.*

\\
***Haystack: Open-Source Framework for Question Answering at Scale***

\\
[Haystack](https://github.com/deepset-ai/haystack/) allows you to use transformer models at scale for question-answering. It uses a Retriever-Reader-Pipeline, where the Retriever is a fast algorithm to find candidate documents and the Reader is a Transformer that extracts the granular answer. It’s building upon Hugging Face’s Transformers and Elasticsearch. It’s open-source, highly modular and easy to extend.

\\
***Teaching an AI to summarise news articles: A new dataset for abstractive summarisation***

\\
Curation Corp is open-sourcing 40,000 professionally-written summaries of news articles. This [article](https://medium.com/curation-corporation/teaching-an-ai-to-abstract-a-new-dataset-for-abstractive-auto-summarisation-5227f546caa8) provides a nice introduction to text summarisation and challenges that exist with this particular task. In addition, it introduces the dataset, the problems that can be addressed with it, including a discussion around fine-tuning methods and evaluation metrics for text summarization, and wrapping up with a discussion for the future work. Instructions for how to access the dataset can be found in this [Github repository](https://github.com/CurationCorp/curation-corpus), along with [examples](https://github.com/CurationCorp/curation-corpus/tree/master/examples) of using the dataset for fine-tuning.

\\
On the topic of text summarization, the HuggingFace team has added both [BART](https://github.com/pytorch/fairseq/blob/master/examples/bart/README.md) and [T5](https://github.com/dair-ai/nlp_paper_summaries/blob/master/Language%20Modeling/t5-text-to-text-transformer.md) as part of their [Transformers](https://github.com/huggingface/transformers/releases) library. These additions allow for all sorts of NLP tasks such as abstractive summarization, translation, and question-answering, among others.


# Articles and Blog posts ✍️

***An Illustrated Guide to Graph Neural Networks***

\\
Graph neural networks have recently seen more adoption for tasks such as enhancing computer vision models and predicting side-effects due to drug interactions. In this [overview](https://dair.ai/An_Illustrated_Guide_to_Graph_Neural_Networks/), Rish presents an intuitive and illustrated guide to GNNs. (*Featured on* [*dair.ai*](https://dair.ai/))

\\
![](https://cdn-images-1.medium.com/max/800/1*Ru3CizrB14hvpZQ7ZtgIag.png)

\\
***Finetuning Transformers with JAX + Haiku***

\\
Just last month DeepMind open-sourced Haiku, the JAX version of their TensorFlow neural network library Sonnet. This [post](https://www.pragmatic.ml/finetuning-transformers-with-jax-and-haiku/) walks through the full source of a port of the RoBERTa pre-trained model to JAX + Haiku, then demonstrates finetuning the model to solve a downstream task. It’s intended to be a practical guide to using the utilities Haiku exposes for allowing the use of light object-oriented “modules” within the context of JAX’s functional programming constraints.

\\
***A small journey in the valley of Natural Language Processing and Text Pre-Processing for German language***

\\
Flávio Clésio wrote a very detailed [article](https://flavioclesio.com/2020/02/17/a-small-journey-in-the-valley-of-natural-language-processing-and-text-pre-processing-for-german-language/) about the challenges of dealing with NLP problems in the German language. He shares many lessons learned, what worked and didn’t work, discusses several state-of-the-art methods, common issues to avoid, and a ton of learning resources, papers and blog posts.

\\
***French language keeping pace with AI: FlauBERT, CamemBERT, PIAF***

\\
Over the last few months, interesting French NLP resources were developed. We are talking about CamemBERT, FlauBERT, and PIAF (Pour une IA Francophone, For a French Speaking AI). The first two are pre-trained language models and the last one is a native French Question-Answering (QA) dataset. This [blog post](https://piaf.etalab.studio/francophonie-ia-english/) discusses all these three projects and some of the challenges presented along the way. This is a nice read and guide for those people working on different models in their own language.

\\
***Custom classifier on top of BERT-like language model***

\\
Marcin wrote another excellent [guide](https://zablo.net/blog/post/custom-classifier-on-bert-model-guide-polemo2-sentiment-analysis/) showing how to build your own classifier (e.g. sentiment classifier) on top of BERT-like language models. It’s a great tutorial because it also shows how to use other modern libraries for the different parts of the model such as HuggingFace Tokenizer and PyTorchLightning. Find the Google Colab notebook [here](https://colab.research.google.com/drive/1sajgpLTrTJDzRSlxycy8aE6ysxGqaT18).

\\
![](https://cdn-images-1.medium.com/max/800/0*66IKvwYU2Lq1kjyn.png)

[*Source*](https://zablo.net/blog/post/custom-classifier-on-bert-model-guide-polemo2-sentiment-analysis/)


# Education 🎓

***Exploratory Data Analysis for Text Data***

\\
In this [code walkthrough](https://dair.ai/Exploratory_Data_Analysis_for_Text_Data/), Yonathan Hadar goes through several methods for exploratory analysis of textual data with various code examples. We featured this tutorial at dair.ai because it is a very comprehensive tutorial that uses standard methods for analyzing data that any data scientist will find useful. It’s a good starting point for anyone starting to play with textual data.

\\
***Embeddings in Natural Language Processing***

\\
Mohammad Taher Pilehvar and Jose Camacho-Collados publicly released their first draft of an upcoming [book](https://medium.com/r/?url=http%3A%2F%2Fjosecamachocollados.com%2Fbook_embNLP_draft.pdf) called "Embeddings in Natural Language Processing". The idea with this book is to discuss the concept of embeddings which represent some of the most widely used techniques in NLP. As [stated](https://medium.com/r/?url=https%3A%2F%2Ftwitter.com%2FCamachoCollados%2Fstatus%2F1246013768074747906%3Fs%3D20) by the authors, the book includes "basics in vector space models and word embeddings to more recent sentence and contextualized embedding techniques based on pre-trained language models."

\\
***A Brief Guide to Artificial Intelligence***

\\
Dr. James V Stone recently published his new [book](https://jim-stone.staff.shef.ac.uk/AIGuide/) on “A Brief Guide to Artificial Intelligence” with the goal to provide a comprehensive overview of current AI systems and their achievement to perform a series of tasks. As stated in the summary, the book is “written in an informal style, with a comprehensive glossary and a list of further readings, which makes it an ideal introduction to the rapidly evolving field of AI.”

\\
![](https://cdn-images-1.medium.com/max/800/0*I2YYXTCQTBmk_YiF.jpg)

\\
***ML and Deep Learning Courses***

\\
Sebastian Raschka has released two recorded [episodes](https://www.youtube.com/watch?time_continue=1&v=QQD9Y2FiotQ&feature=emb_logo) for his course on “Introduction to Deep Learning and Generative Models”. You can find lecture notes and other materials in this [repo](https://github.com/rasbt/stat453-deep-learning-ss20).

\\
Here is another excellent set of [lectures](https://www.youtube.com/watch?v=e-erMrqBd1w&feature=youtu.be) on the topic of “Discrete Differential Geometry”.

\\
Peter Bloem has released the full [syllabus](https://mlvu.github.io/), including videos and lecture slides, for their introductory course on Machine Learning delivered at the VU University Amsterdam. Topics range from linear models and search to probabilistic models to models for sequential data.

\\
***CNN Architecture — Implementations***

\\
Dimitris Katsios provides a set of excellent [tutorials](https://github.com/Machine-Learning-Tokyo/CNN-Architectures/tree/master/Implementations) that provide guidance on how to implement convolutional neural network (CNN) architectures from original papers. He proposes a recipe on how to go about implementing these while sharing the step-by-step that includes diagrams and code with the ability to infer the structure of the model. There is a lot to learn from these guides in terms of guiding others to more efficiently implementing papers.


# Noteworthy Mentions ⭐️

You can find the previous newsletter [here](https://dair.ai/NLP_Newsletter_8/). You can also find the translated versions of the previous issues of the NLP Newsletter [here](https://github.com/dair-ai/nlp_newsletter).

\\
A couple of months back we featured Luis Serrano’s excellent book on Grokking Machine Learning. [Listen](https://content.alegion.com/podcast/grokking-machine-learning-with-luis-serrano) to Luis discuss a bit more about his book and his journey to becoming a successful educator in the field of ML.

\\
Here are several newsletters that may be worth your attention: [Sebastian Ruder’s NLP News](http://newsletter.ruder.io/), [Made With ML](https://madewithml.com/blog/newsletter/2020-03-25/), [SIGTYP’s newsletter](https://sigtyp.github.io/sigtyp-newsletter-Mar-2020.html), [MLT Newsletter](https://mailchi.mp/c70ebcf424b2/mlt-newsletter-6), [Nathan’s AI newsletter](http://newsletter.airstreet.com/issues/your-guide-to-ai-in-q1-2020-part-1-2-212335), etc…

\\
Jupyter now comes with a [visual debugger.](https://blog.jupyter.org/a-visual-debugger-for-jupyter-914e61716559) This will allow this popular data science framework to be used more easily for general purposes.

\\
![](https://cdn-images-1.medium.com/max/800/0*FE5Fj5DFb0U9565a.gif)

\\
Abhishek Thakur has a great YouTube [channel](https://www.youtube.com/channel/UCBPRJjIWfyNG4X-CRbnv78A) where he walks through code showing how to use modern methods in machine learning and NLP. Some of his videos range from fine-tuning BERT models to performing handwritten grapheme classification to building a machine learning framework.

\\
David Silver, a renowned reinforcement learning professor and researcher, is [awarded](https://awards.acm.org/about/2019-acm-prize) the ACM Prize in Computing for breakthrough advances in computer game-playing. Silver lead the Alpha Go team that beat Lee Sedol in Go.

\\
For those interested to learn the differences and the inner working behind popular methods for NLP such as BERT and word2vec, Mohd [provides](https://www.analyticsvidhya.com/blog/2019/09/demystifying-bert-groundbreaking-nlp-framework/) an excellent, approachable, and detailed overview of these approaches.

\\
TensorFlow 2.2.0-rc-1 has been [released](https://github.com/tensorflow/tensorflow/releases/tag/v2.2.0-rc1?linkId=85073218). It includes features such as a Profiler that helps spot bottlenecks in your ML models and guide optimization of these models. Also, Colab now uses TensorFlow 2 by [default](https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/tutorials/quickstart/advanced.ipynb?linkId=85251566).

\\
Gabriel Peyré provides a nice set of [notes](https://mathematical-tours.github.io/book-sources/optim-ml/OptimML.pdf) for his course on ML optimization. Notes include convex analysis, SGD, autodiff, MLP, among other topics.


----------

## dair.ai updates

- ***Call for Contributions to Open Science:*** We have opened a call for contributions to open science. There are many interesting collaborations in the pipeline. We want to open the invitation to anyone that’s interested in contributing to open science. Looking for volunteers, writers, reviewers, editors, developers, speakers, researchers, project maintainers,… [Join us](https://github.com/dair-ai/dair-ai.github.io/issues/54)!

- ***NLP Research Highlights Issue #1:*** ICYMI, in this [article](https://dair.ai/NLP_Research_Highlights_-_Issue_-1/) we highlight some NLP trends and topics with a focus on summarizing the what, how, and why of a selection of interesting and important NLP papers published in the last few months.

----------

If you have any datasets, projects, blog posts, tutorials, or papers that you wish to share in the next issue of the NLP Newsletter, please submit them directly using this [form](https://forms.gle/3b7Q2w2bzsXE6uYo9).

\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*
