---
layout: post
title: "NLP Year in Review — 2019"
author: saravia_elvis
excerpt: "NLP highlights for the year 2019."
modified:
comments: true
tags: [Machine Learning | Data Science | Artificial Intelligence | Technology | Programming | NLP]
image:
  thumb: 
---

![](https://miro.medium.com/max/1842/1*T08rCNctBW5zUvol0gfIig.png)

\\
2019 was an impressive year for the field of natural language processing (NLP). In this blog post, I want to highlight some of the most important stories related to machine learning and NLP that I came across in 2019. I will mostly focus on NLP but I will also highlight a few interesting stories related to AI in general. The headlines are in no particular order. Stories may include publications, engineering efforts, yearly reports, the release of educational resources, etc.

\\
*Warning! This is a very long article so before you get started I would suggest bookmarking the article if you wish to read it in parts. I have also published the PDF version of this article which you can find at the end of the post.*

### **Table of Content**
- Publications
- ML/NLP Creativity and Society
- ML/NLP Tools and Datasets
- Articles and Blog Posts
- Ethics in AI
- ML/NLP Education
----------

### **Publications 📙**

Google AI introduces [ALBERT](https://ai.googleblog.com/2019/12/albert-lite-bert-for-self-supervised.html) which a lite version of [BERT](https://arxiv.org/abs/1810.04805) for self-supervised learning of contextualized language representations. The main improvements are reducing redundancy and allocating the model’s capacity more efficiently. The method advances state-of-the-art performance on 12 NLP tasks.

\\
Earlier this year, researchers at NVIDIA published a [popular paper](https://arxiv.org/pdf/1812.04948.pdf) (coined StyleGAN) which proposed an alternative generator architecture for GANs, adopted from [style transfer](https://en.wikipedia.org/wiki/Neural_Style_Transfer). Here is a [follow-up work](https://arxiv.org/pdf/1912.04958v1.pdf) where that focuses on improvements such as redesigning the generator normalization process.

![](https://miro.medium.com/max/1058/1*Oc0EmkL9Scp5WZ4m5bq-cA.png)
The top row shows target images and the bottom row shows synthesized images — [source](https://arxiv.org/pdf/1912.04958v1.pdf)

\\
One of my favorite papers this year was [code2seq](https://code2seq.org/) which is a method for generating natural language sequences from the structured representation of code. Such research can give way to applications such as automated code summarization and documentation.

\\
Ever wondered if it’s possible to train a biomedical language model for biomedical text mining? The answer is [BioBERT](https://arxiv.org/abs/1901.08746) which is a contextualized approach for extracting important information from biomedical literature.

\\
After the release of BERT, Facebook researchers published [RoBERTa](https://ai.facebook.com/blog/roberta-an-optimized-method-for-pretraining-self-supervised-nlp-systems/) which introduced new methods for optimization to improve upon BERT and produced state-of-the-art results on a wide variety of NLP benchmarks.

\\
Researchers from Facebook AI also recently published a [method](https://ai.facebook.com/blog/making-transformer-networks-simpler-and-more-efficient/) based on an all-attention layer for improving the efficiency of a Transformer language model. More work from this research group includes a [method](https://ai.facebook.com/blog/-teaching-ai-to-plan-using-language-in-a-new-open-source-strategy-game/) to teach AI systems on how to plan using natural language.


![](https://miro.medium.com/max/968/1*0ZYSozImqnmFHxKmREpzmw.png)


Explainability continues to be an important topic in machine learning and NLP. This [paper](https://arxiv.org/abs/1910.10045) provides a comprehensive overview of works addressing explainability, taxonomies, and opportunities for future research.

\\
Sebastian Ruder published his [thesis](https://ruder.io/thesis/) on Neural Transfer Learning for Natural Language Processing.

\\
A group of researchers developed a [method](https://arxiv.org/abs/1910.04980) to perform emotion recognition in the context of conversation which could pave the way to affective dialogue generation. Another related work involves a GNN approach called [DialogueGCN](https://www.aclweb.org/anthology/D19-1015.pdf) to detect emotions in conversations. This research paper also provides [code implementation](https://github.com/SenticNet/conv-emotion/tree/master/DialogueGCN).

\\
The Google AI Quantum team published a [paper](https://www.nature.com/articles/s41586-019-1666-5) in Nature where they claim to have developed a quantum computer that is faster than the world’s largest supercomputer. Read more about their experiments (here](https://ai.googleblog.com/2019/10/quantum-supremacy-using-programmable.html).

\\
As mentioned earlier, one of the areas of neural network architectures that require a lot of improvement is explainability. This [paper](https://arxiv.org/abs/1908.04626) discusses the limitations of attention as a reliable approach for explainability in the context of language modeling.

\\
[Neural Logic Machine](https://arxiv.org/abs/1904.11694) is a neural-symbolic network architecture that is able to do well at both inductive learning and logic reasoning. The model does significantly well on tasks such as sorting arrays and finding shortest paths.


![](https://miro.medium.com/max/1298/1*t7rfBC1pdn0wGgE1L0VNXw.png)


And [here](https://arxiv.org/abs/1909.03186) is a paper that applies Transformer language models to Extractive and Abstractive Neural document summarization.

\\
Researchers developed a method that focuses on using comparisons to build and train ML models. Instead of requiring large amounts of feature-label pairs, this [technique](https://blog.ml.cmu.edu/2019/03/29/building-machine-learning-models-via-comparisons/) compares images with previously seen images to decide whether the image should be of a certain label.

\\
Nelson Liu and others presented a [paper](https://arxiv.org/abs/1903.08855) discussing the type of linguistic knowledge being captured by pretrained contextualizers such as BERT and ELMo.

\\
[XLNet](https://arxiv.org/abs/1906.08237) is a pretraining method for NLP that showed improvements upon BERT on 20 tasks. I wrote a summary of this great work [here](https://medium.com/dair-ai/xlnet-outperforms-bert-on-several-nlp-tasks-9ec867bb563b).

\\
This [work](https://arxiv.org/abs/1901.11373) from DeepMind reports the results from an extensive empirical investigation that aims to evaluate language understanding models applied to a variety of tasks. Such extensive analysis is important to better understand what language models capture so as to improve their efficiency.

\\
[VisualBERT](https://arxiv.org/abs/1908.03557) is a simple and robust framework for modeling vision-and-language tasks including VQA and Flickr30K, among others. This approach leverages a stack of Transformer layers coupled with self-attention to align elements in a piece of text and the regions of an image.

\\
This [work](https://arxiv.org/abs/1903.05987) provides a detailed analysis comparing NLP transfer learning methods along with guidelines for NLP practitioners.

\\
Alex Wang and Kyunghyun propose an [implementation of BERT](https://arxiv.org/abs/1902.04094) that is able to produce high-quality, fluent generations. Here is a Colab [notebook](https://colab.research.google.com/drive/1MxKZGtQ9SSBjTK5ArsZ5LKhkztzg52RV) to try it.

\\
Facebook researchers published code ([PyTorch implementation](https://github.com/facebookresearch/XLM)) for XLM which is a model for cross-lingual model pretraining.

\\
This [works](https://www.cl.uni-heidelberg.de/statnlpgroup/blog/rl4nmt/) provides a comprehensive analysis of the application of reinforcement learning algorithms for neural machine translation.

\\
This survey [paper](https://jair.org/index.php/jair/article/view/11640) published in JAIR provides a comprehensive overview of the training, evaluation, and use of cross-lingual word embedding models.

\\
The Gradient published an excellent [article](https://thegradient.pub/the-promise-of-hierarchical-reinforcement-learning/) detailing the current limitations of reinforcement learning and also providing a potential path forward with hierarchical reinforcement learning. And in a timely manner, a couple of folks published an excellent set of [tutorials](https://github.com/araffin/rl-tutorial-jnrr19/blob/master/1_getting_started.ipynb) to get started with reinforcement learning.

\\
This [paper provides](https://arxiv.org/abs/1902.06006) a light introduction to contextual word representations.


### **ML/NLP Creativity and Society 🎨**

*Machine learning has been applied to solve real-world problems but it has also been applied in interesting and creative ways. ML creativity is as important as any other research area in AI because at the end of the day we wish to build AI systems that will help shape our culture and society.*

\\
Towards the end of this year, Gary Marcus and Yoshua Bengio [debated](https://www.zdnet.com/article/devils-in-the-details-in-bengio-marcus-ai-debate/) on the topics of deep learning, symbolic AI and the idea of hybrid AI systems.

\\
The [2019 AI Index Report](https://hai.stanford.edu/ai-index/2019) was finally released and provides a comprehensive analysis of the state of AI which can be used to better understand the progress of AI in general.

\\
[Commonsense reasoning](https://en.wikipedia.org/wiki/Commonsense_reasoning) continues to be an important area of research as we aim to build artificial intelligence systems that not are only able to make a prediction on the data provided but also understand and can reason about those decisions. This type of technology can be used in conversational AI where the goal is to enable an intelligent agent to have more natural conversations with people. Check out this [interview](https://www.forbes.com/sites/ayurellahornmuller/2018/12/31/the-art-of-ai-storytelling-how-one-30-under-30-scientist-is-teaching-devices-to-make-assumptions/#61de7c52a4f0) with Nasrin Mostafazadeh having a discussion on commonsense reasoning and applications such as storytelling and language understanding. You can also check out this recent [paper](https://arxiv.org/abs/1906.02361) on how to leverage language models for commonsense reasoning.

\\
[Activation Atlases](https://openai.com/blog/introducing-activation-atlases/) is a technique developed by researchers at Google and Open AI to better understand and visualize the interactions happening between neurons of a neural network.


![] (https://miro.medium.com/max/1600/0*MQUIQ6n7i1RwfCbK.jpg)
An activation atlas of the InceptionV1 vision classification network reveals many fully realized features, such as electronics, buildings, food, animal ears, plants, and watery backgrounds.” — [source](https://openai.com/blog/introducing-activation-atlases/)

\\
Check out the [Turing Lecture](https://fcrc.acm.org/turing-lecture-at-fcrc-2019) delivered by Geoffrey Hinton and Yann LeCun who were [awarded](https://medium.com/dair-ai/turing-award-goes-to-deep-learning-pioneers-38d37cc6d0dd?source=collection_home---4------10-----------------------), together with Yoshua Bengio, the Turing Award this year.

\\
Tackling climate change with machine learning is discussed in this [paper](https://arxiv.org/abs/1906.05433).

\\
OpenAI published an extensive [report](https://d4mucfpksywv.cloudfront.net/papers/GPT_2_Report.pdf) discussing the social impacts of language models covering topics like beneficial use and potential misuse of the technology.

\\
Emotion analysis continues to be used in a diverse range of applications. [The Mojifier](https://themojifier.com/) is a cool project that looks at an image, detects the emotion, and replaces the face with the emojis matching the emotion detected.

\\
Work on radiology with the use of AI techniques has also been trending this year. Here is a nice [summary](https://arxiv.org/abs/1903.11726) of trends and perspectives in this area of study. 

\\
Researchers from NYU also released a [Pytorch implementation](https://medium.com/@jasonphang/deep-neural-networks-improve-radiologists-performance-in-breast-cancer-screening-565eb2bd3c9f) of a deep neural network that improves radiologists’ performance on breast cancer screening. And here is a major [dataset](https://physionet.org/content/mimic-cxr/2.0.0/) release called MIMIC-CXR which consists of a database of chest Xrays and text radiology reports.

\\
The New York Times wrote a [piece](https://www.nytimes.com/2019/01/02/obituaries/karen-sparck-jones-overlooked.html) on Karen Spark Jones remembering the seminal contributions she made to NLP and Information Retrieval.

\\
OpenAI Five [became](https://openai.com/blog/openai-five-defeats-dota-2-world-champions/) the first AI system to beat a world champion at an esports game.

\\
The [Global AI Talent Report](https://jfgagne.ai/talent-2019/) provides a detailed report of the worldwide AI talent pool and the demand for AI talent globally.

\\
If you haven’t subscribed already, the DeepMind team has an excellent [podcast](https://deepmind.com/blog?filters=%7B%22category%22:%5B%22Podcasts%22%5D%7D) where participants discuss the most pressing topics involving AI. Talking about AI potential, Demis Hassabis did an [interview](https://worldin.economist.com/article/17385/edition2020demis-hassabis-predicts-ai-will-supercharge-science?utm_medium=pr&utm_source=inf-a&utm_campaign=worldin) with The Economist where he spoke about futuristic ideas such as using AI as an extension to the human mind to potentially find solutions to important scientific problems.

\\
This year also witnessed incredible advancement in ML for health applications. For instance, researchers at Massachusetts [developed](https://venturebeat.com/2019/01/04/massachusetts-generals-ai-can-spot-brain-hemorrhages-as-accurately-as-humans/) an AI system capable of spotting brain hemorrhages as accurate as humans.

![] https://miro.medium.com/max/1104/0*HQad0irUNeJ79Ib9
“Brain scans analyzed by the AI system.”

\\
Janelle Shane summarizes a set of [“weird” experiments](https://aiweirdness.com/post/181621835642/10-things-artificial-intelligence-did-in-2018) showing how machine learning can be used in creative ways to conduct fun experimentation. Sometimes this is the type of experiment that’s needed to really understand what an AI system is actually doing and not doing. Some experiments include neural networks generating fake snakes and telling jokes.


![](https://miro.medium.com/max/400/0*5DZujahMQxmWHG-J.png)
[Snake Species](https://aiweirdness.com/post/181621835642/10-things-artificial-intelligence-did-in-2018)

\\
[Learn](https://www.blog.google/topics/machine-learning/hunting-planets-machine-learning/) to find planets with machine learning models build on top of TensorFlow.

\\
OpenAI [discusses](https://openai.com/blog/better-language-models/#sample1) the implication of releasing (including the potential of malicious use cases) large-scale unsupervised language models.

\\
This [Colab notebook](https://colab.research.google.com/github/google/nucleus/blob/master/nucleus/examples/dna_sequencing_error_correction.ipynb) provides a great introduction on how to use Nucleus and TensorFlow for “DNA Sequencing Error Correction”. And here is a great detailed [post](https://blog.floydhub.com/exploring-dna-with-deep-learning/) on the use of deep learning architectures for exploring DNA.


![](https://miro.medium.com/max/819/1*m6Olf8Vu5M0VLdd8-TU2Nw.jpeg)
[source](https://raw.githubusercontent.com/google/nucleus/master/nucleus/examples/images/consensus-approach-overview.jpg)

\\
Alexander Rush is a Harvard NLP researcher who wrote an important article about the [issues](http://nlp.seas.harvard.edu/NamedTensor) with tensors and how some current libraries expose them. He also went on to talk about a proposal for tensors with named indices.

----------

### **ML/NLP Tools and Datasets ⚙️**

*Here I highlight stories related to software and datasets that have assisted in enabling NLP and machine learning research and engineering.*

\\
Hugging Face released a popular Transformer [library](https://github.com/huggingface/transformers) based on Pytorch names pytorch-transformers. It allows NLP practitioners and researchers to easily use state-of-the-art general-purpose architectures such as BERT, GPT-2, and XLM, among others. If you are interested in how to use pytorch-transformers there are a few places to start but I really liked this detailed [tutorial](https://rsilveira79.github.io/fermenting_gradients/machine_learning/nlp/pytorch/pytorch-transformer-squad/) by Roberto Silveira showing how to use the library for machine comprehension

![]https://miro.medium.com/max/425/0*wHSaulTrUQzX4mRd.png)
[source](https://github.com/huggingface/transformers)

\\
TensorFlow 2.0 was released with a bunch of [new features](https://medium.com/tensorflow/whats-coming-in-tensorflow-2-0-d3663832e9b8). Read more about best practices [here](https://medium.com/tensorflow/effective-tensorflow-2-0-best-practices-and-whats-changed-a0ca48767aff). François Chollet also wrote an extensive overview of the new features in this [Colab notebook](https://colab.research.google.com/drive/1UCJt8EYjlzCs1H1d1X0iDGYJsHKwu-NO).

\\
PyTorch 1.3 was [released](https://ai.facebook.com/blog/pytorch-13-adds-mobile-privacy-quantization-and-named-tensors/) with a ton of new features including named tensors and other front-end improvements.

\\
The Allen Institute for AI released [Iconary](https://iconary.allenai.org/) which is an AI system that can play Pictionary-style games with a human. This work incorporates visual/language learning systems and commonsense reasoning. They also published a new commonsense reasoning [benchmark](https://arxiv.org/abs/1908.05739) called Abductive-NLI.

\\
spaCy [releases](https://explosion.ai/blog/spacy-transformers) a new library to incorporate Transformer language models into their own library so as to be able to extract features and used them in spaCy NLP pipelines. This effort is built on top of the popular Transformers library developed by Hugging Face. Maximilien Roberti also [wrote](https://towardsdatascience.com/fastai-with-transformers-bert-roberta-xlnet-xlm-distilbert-4f41ee18ecb2) a nice article on how to combine fast.ai code with pytorch-transformers.

\\
The Facebook AI team released [PHYRE](https://phyre.ai/) which is a benchmark for physical reasoning aiming to test the physical reasoning of AI systems through solving various physics puzzles.


![] https://miro.medium.com/max/416/1*1sNrObRoffXbfX2D61bXTw.gif)
[source](https://phyre.ai/)

\\
StanfordNLP released [StanfordNLP 0.2.0](https://stanfordnlp.github.io/stanfordnlp/) which is a Python library for natural language analysis. You can perform different types of linguistic analysis such as lemmatization and part of speech recognition on over 70 different languages.

\\
[GQA](https://cs.stanford.edu/people/dorarad/gqa/) is a visual question answering dataset for enabling research related to visual reasoning.

\\
exBERT is a visual interactive tool to explore the embeddings and attention of Transformer language models. You can find the paper [here](https://arxiv.org/abs/1910.05276) and the demo [here](http://exbert.net/).


![] https://miro.medium.com/max/1600/0*eHjrWea2jeGqhvI_.png)
exBERT — [source](http://exbert.net/)

\\
Distill published an [article](https://distill.pub/2019/memorization-in-rnns/) on how to visualize memorization in Recurrent Neural Networks (RNNs).

\\
[Mathpix](https://mathpix.com/) is a tool that lets you take a picture of an equation and then it provides you with the latex version.


![](https://miro.medium.com/max/400/1*d3BlwVO1E9ndiLVOj4BPcQ.gif)
[source](https://mathpix.com/)

\\
[Parl.ai](https://parl.ai/) is a platform that hosts many popular datasets for all works involving dialog and conversational AI.

\\
Uber researchers released [Ludwig](https://uber.github.io/ludwig/), an open-source tool that allows users to easily train and test deep learning models with just a few lines of codes. The whole idea is to avoid any coding while training and testing models.

\\
Google AI researchers release [“Natural Questions”](https://ai.googleblog.com/2019/01/natural-questions-new-corpus-and.html) which is a large-scale corpus for training and evaluating open-domain question answering systems.


### **Articles and Blog posts ✍️**

*This year witnessed an explosion of data science writers and enthusiasts. This is great for our field and encourages healthy discussion and learning. Here I list a few interesting and must-see articles and blog posts I came across:*

\\
Christian Perone provides an [excellent introduction](http://blog.christianperone.com/2019/01/mle/) to maximum likelihood estimation (MLE) and maximum a posteriori (MAP) which are important principles to understand how parameters of a model are estimated.

\\
Reiichiro Nakano published a [blog post](https://reiinakano.com/2019/06/21/robust-neural-style-transfer.html) discussing neural style transfer with adversarially robust classifiers. A Colab [notebook](https://colab.research.google.com/github/reiinakano/adversarially-robust-neural-style-transfer/blob/master/Robust_Neural_Style_Transfer.ipynb) was also provided.

\\
Saif M. Mohammad started a great [series](https://medium.com/@nlpscholar/state-of-nlp-cbf768492f90) discussing a diachronic analysis of ACL anthology.


![](https://miro.medium.com/max/1570/0*zfM9ED6W74NyxMln.png)
“Graphs showing average academic age, median academic age, and percentage of first-time publishers in AA over time.” — [source](https://medium.com/@nlpscholar/state-of-nlp-cbf768492f90)

\\
The question is: can a language model learn syntax? Using structural probes, this [work](https://nlp.stanford.edu/~johnhew/structural-probe.html) aims to show that it is possible to do so using contextualized representations and a method for finding tree structures.

\\
Andrej Karpathy wrote a [blog post](https://karpathy.github.io/2019/04/25/recipe/) summarizing best practices and a recipe on how to effectively train neural networks.

\\
Google AI researchers and other researchers collaborated to [improve](https://www.blog.google/products/search/search-language-understanding-bert) the understanding of search using BERT models. Contextualized approaches like BERT are adequate to understand the intent behind search queries.

\\
[Rectified Adam](https://medium.com/@lessw/new-state-of-the-art-ai-optimizer-rectified-adam-radam-5d854730807b) (RAdam) is a new optimization technique based on Adam optimizer that helps to improve AI architectures. There are several efforts in coming up with better and more stable optimizers but the authors claim to focus on other aspects of optimizations that are just as important for delivering improved convergence.

\\
With a lot of development of machine learning tools recently, there are also many discussions on how to implement ML systems that enable solutions to practical problems. Chip Huyen [wrote](https://github.com/chiphuyen/machine-learning-systems-design/blob/master/build/build1/consolidated.pdf) an interesting chapter discussing machine learning system design emphasizing on topics such as hyperparameter tuning and data pipeline.

\\
NVIDIA [breaks the record](https://techcrunch.com/2019/08/13/nvidia-breaks-records-in-training-and-inference-for-real-time-conversational-ai/) for creating the biggest language model trained on billions of parameters.

Abigail See wrote this excellent blog [post](http://www.abigailsee.com/2019/08/13/what-makes-a-good-conversation.html) about what makes a good conversation in the context of systems developed to perform natural language generation task.

\\
Google AI [published](https://ai.googleblog.com/2019/09/announcing-two-new-natural-language.html) two natural language dialog datasets with the idea to use more complex and natural dialog datasets to improve personalization in conversational applications like digital assistants.

\\
Deep reinforcement learning continues to be one of the most widely discussed topics in the field of AI and it has even attracted interest in the space of psychology and neuroscience. Read more about some highlights in this [paper published](https://www.cell.com/trends/cognitive-sciences/fulltext/S1364-6613(19)30061-0) in Trends in Cognitive Sciences.

\\
Samira Abner wrote this excellent [blog post](https://staff.fnwi.uva.nl/s.abnar/?p=108) summarizing the main building blocks behind Transformers and capsule networks and their connections. Adam Kosiorek also wrote this magnificent [piece](http://akosiorek.github.io/ml/2019/06/23/stacked_capsule_autoencoders.html) on stacked capsule-based autoencoders (an unsupervised version of capsule networks) which was used for object detection.


![] https://miro.medium.com/max/819/0*R4x3osVbWIuUUPrn.png)
[source](https://staff.fnwi.uva.nl/s.abnar/?p=108)

\\
Researchers published an [interactive article](https://distill.pub/2019/visual-exploration-gaussian-processes/) on Distill that aims to show a visual exploration of Gaussian Processes.

\\
Through this Distill [publication](https://distill.pub/2019/gan-open-problems/), Augustus Odena makes a call to researchers to address several important open questions about GANs.

\\
Here is a PyTorch [implementation](https://github.com/zaidalyafeai/Notebooks/blob/master/Deep_GCN_Spam.ipynb) of graph convolutional networks (GCNs) used for classifying spammers vs. non-spammers.

\\
At the beginning of the year, VentureBeat released a list of [predictions](https://venturebeat.com/2019/01/02/ai-predictions-for-2019-from-yann-lecun-hilary-mason-andrew-ng-and-rumman-chowdhury/) for 2019 made by experts such as Rumman Chowdury, Hilary Mason, Andrew Ng, and Yan LeCun. Check it out to see if their predictions were right.

\\
[Learn](https://medium.com/huggingface/multi-label-text-classification-using-bert-the-mighty-transformer-69714fa3fb3d) how to finetune BERT to perform multi-label text classification.

\\
Due to the popularity of BERT, in the past few months, many researchers developed methods to “compress” BERT with the idea to build faster, smaller and memory-efficient versions of the original. Mitchell A. Gordon [wrote](http://mitchgordon.me/machine/learning/2019/11/18/all-the-ways-to-compress-BERT.html) a summary of the types of compressions and methods developed around this objective.

\\
Superintelligence continued to be a topic of debate among experts. It’s an important topic that needs a proper understanding of frameworks, policies, and careful observations. I found this interesting [series of comprehensive essays](https://www.fhi.ox.ac.uk/wp-content/uploads/Reframing_Superintelligence_FHI-TR-2019-1.1-1.pdf) (in the form of a technical report by K. Eric Drexler) to be useful to understand some issues and considerations around the topic of superintelligence.

\\
Eric Jang wrote a nice [blog post](https://blog.evjang.com/2019/02/maml-jax.html) introducing the concept of meta-learning which aims to build and train machine learning models that not only predict well but also learn well.

\\
A [summary](https://ruder.io/aaai-2019-highlights/) of AAAI 2019 highlights by Sebastian Ruder.

\\
Graph neural networks were heavily discussed this year. David Mack wrote a [nice visual article](https://medium.com/octavian-ai/finding-shortest-paths-with-graph-networks-807c5bbfc9c8) about how they used this technique together with attention to perform shortest path calculations.

\\
Bayesian approaches remain an interesting subject, in particular how they can be applied to neural networks to avoid common issues like over-fitting. Here is a [list](https://medium.com/neuralspace/bayesian-neural-network-series-post-1-need-for-bayesian-networks-e209e66b70b2) of suggested reads by Kumar Shridhar on the topic.


![](https://miro.medium.com/max/1600/0*E8ScZUhm9npwaZQm.png)
“Network with point-estimates as weights vs Network with probability distribution as weights” - [Source](https://arxiv.org/pdf/1806.05978.pdf)

### **Ethics in AI 🚨**

*Perhaps one of the most highly discussed aspects of AI systems this year was ethics which include discussions around bias, fairness, and transparency, among others. In this section, I provide a list of interesting stories and papers around this topic:*

\\
The paper titled [“Does mitigating ML’s impact disparity require treatment disparity?”](http://papers.nips.cc/paper/8035-does-mitigating-mls-impact-disparity-require-treatment-disparity) discusses the consequences of applying disparate learning processes through experiments conducted on real-world datasets.

\\
HuggingFace published an [article](https://medium.com/huggingface/ethical-analysis-of-the-open-sourcing-of-a-state-of-the-art-conversational-ai-852113c324b2) discussing ethics in the context of open-sourcing NLP technology for conversational AI.

\\
Being able to quantify the role of ethics in AI research is an important endeavor going forward as we continue to introduce AI-based technologies to society. This [paper](https://arxiv.org/abs/1809.08328) provides a broad analysis of the measures and “use of ethics-related research in leading AI, machine learning and robotics venues.”

\\
This [work](https://arxiv.org/abs/1903.03862) presented at NAACL 2019 discusses how debiasing methods can cover up gender bias in word embeddings.

\\
[Listen](https://www.youtube.com/watch?v=A2Jtqi_oa2Y]) to Zachary Lipton presenting his paper “Troubling Trends in ML Scholarship”. I also wrote a summary of this interesting paper which you can find [here](https://medium.com/dair-ai/an-overview-of-troubling-trends-in-machine-learning-scholarship-582df3caa518?source=false---------0).

\\
Gary Marcus and Ernest Davis published their book on [“Rebooting AI: Building Artificial Intelligence We Can Trust”](https://www.amazon.com/Rebooting-AI-Building-Artificial-Intelligence/dp/1524748250). The main theme of the book is to talk about the steps we must take to achieve robust artificial intelligence. On the topic of AI progression, François Chollet also wrote an impressive [paper](https://arxiv.org/abs/1911.01547) making a case for better ways to measure intelligence.

\\
Check out this Udacity [course](https://www.udacity.com/course/secure-and-private-ai--ud185) created by Andrew Trask on topics such as differential privacy, federated learning, and encrypted AI. On the topic of privacy, Emma Bluemke wrote this great [post](https://blog.openmined.org/federated-learning-differential-privacy-and-encrypted-computation-for-medical-imaging/) discussing how one may go about training machine learning models while preserving patient privacy.

\\
At the beginning of this year, Mariya Yao [posted](https://www.topbots.com/most-important-ai-ethics-research/) a comprehensive list of research paper summaries involving AI ethics. Although the list of paper reference was from 2018, I believe they are still relevant today.


### **ML/NLP Education 🎓**

*Here I will feature a list of educational resources, writers and people doing some amazing work educating others about difficult ML/NLP concepts/topics:*

\\
CMU released materials and syllabus for their [“Neural Networks for NLP”](http://phontron.com/class/nn4nlp2019/) course.

\\
[Elvis Saravia](https://twitter.com/omarsar0) and [Soujanya Poria](https://github.com/soujanyaporia) released a project called [NLP-Overview](https://nlpoverview.com/) that is intended to help students and practitioners to get a condensed overview of modern deep learning techniques applied to NLP, including theory, algorithms, applications, and state of the art results — [Link](https://github.com/omarsar/nlp_overview)


![] https://miro.medium.com/max/992/0*FN-wy7HwrSN1dmW0.png)
[NLP Overview](https://nlpoverview.com/)

\\
Microsoft Research Lab published a free [ebook](https://www.datasciencecentral.com/profiles/blogs/new-book-foundations-of-data-science-from-microsoft-research-lab) on the foundation of data science with topics ranging from Markov Chain Monte Carlo to Random Graphs.

\\
[“Mathematics for Machine Learning”](https://mml-book.github.io/) is a free ebook introducing the most important mathematical concepts used in machine learning. It also includes a few Jupyter notebook tutorials describing the machine learning parts. Jean Gallier and Jocelyn Quaintance wrote an [extensive free ebook](https://www.cis.upenn.edu/~jean/math-deep.pdf) covering mathematical concepts used in machine learning.

\\
Stanford releases a [playlist of videos](https://www.youtube.com/playlist?list=PLoROMvodv4rObpMCir6rNNUlFAn56Js20) for its course on “Natural Language Understanding”.

\\
On the topic of learning, OpenAI put together this great [list](https://openai.com/blog/learning-day/) of suggestions on how to keep learning and improving your machine learning skills. Apparently, their employees use these methods on a daily basis to keep learning and expanding their knowledge.


![] (https://miro.medium.com/max/792/1*VIcTGpIn2GoHQbZx3rPucQ.png)
[source](https://openai.com/blog/learning-day/)

\\
Adrian Rosebrock [published](https://www.pyimagesearch.com/start-here/) an 81-page guide on how to do computer vision with Python and OpenCV.

\\
Emily M. Bender and Alex Lascarides published a [book](http://www.morganclaypoolpublishers.com/catalog_Orig/product_info.php?products_id=1451) titled “Linguistic Fundamentals for NLP”. The main idea behind the book is to discuss what
“meaning” is in the field of NLP by providing a proper foundation on semantics and pragmatics.

\\
Elad Hazan published his [lecture notes](https://drive.google.com/file/d/1GIDnw7T-NT4Do3eC0B5kYJlzwOs6nzIO/view) on “Optimization for Machine Learning” which aims to present machine training as an optimization problem with beautiful math and notations. Deeplearning.ai also published a [great article](https://www.deeplearning.ai/ai-notes/optimization/?utm_source=social&utm_medium=twitter&utm_campaign=BlogAINotesOptimizationAugust272019) that discusses parameter optimization in neural networks using a more visual and interactive approach.

\\
Andreas Mueller published a [playlist](https://www.youtube.com/playlist?list=PL_pVmAaAnxIQGzQS2oI3OWEPT-dpmwTfA) of videos for a new course in “Applied Machine Learning”.

\\
Fast.ai [releases](https://www.fast.ai/2019/06/28/course-p2v3/) its new MOOC titled “Deep Learning from the Foundations”.

\\
MIT published all [videos](https://www.youtube.com/playlist?list=PLtBw6njQRU-rwp5__7C0oIVt26ZgjG9NI) and syllabus for their course on “Introduction to Deep Learning”.

\\
Chip Huyen [tweeted](https://twitter.com/chipro/status/1157772112876060672) an impressive list of free online courses to get started with machine learning.

\\
Andrew Trask [published](https://github.com/iamtrask/Grokking-Deep-Learning) his book titled “Grokking Deep Learning”. The book serves as a great starter for understanding the fundamental building blocks of neural network architectures.

\\
Sebastian Raschka uploaded [80 notebooks](https://github.com/rasbt/deeplearning-models) about how to implement different deep learning models such as RNNs and CNNs. The great thing is that the models are all implemented in both PyTorch and TensorFlow.

\\
Here is a great [tutorial](https://medium.com/@d3lm/understand-tensorflow-by-mimicking-its-api-from-scratch-faa55787170d) that goes deep into understanding how TensorFlow works. And here is [one](http://blog.christianperone.com/2018/03/pytorch-internal-architecture-tour/) by Christian Perone for PyTorch.

\\
Fast.ai also published a course titled “Intro to NLP” accompanied by a [playlist](https://www.youtube.com/playlist?list=PLtmWHNX-gukKocXQOkQjuVxglSDYWsSh9). Topics range from sentiment analysis to topic modeling to the Transformer.

\\
[Learn](https://ipam.wistia.com/medias/excbyr8gvv) about Graph Convolutional Neural Networks for Molecular Generation in this talk by Xavier Bresson. Slides can be found [here](http://helper.ipam.ucla.edu/publications/glws4/glws4_16076.pdf). And here is a paper discussing how to [pre-train](https://arxiv.org/abs/1905.12265) GNNs.

\\
On the topic of graph networks, some engineers [use them](https://www.eurekalert.org/pub_releases/2019-06/uoc--eug060719.php) to predict the properties of molecules and crystal. The Google AI team also published an excellent [blog](https://ai.googleblog.com/2019/10/learning-to-smell-using-deep-learning.html) post explaining how they use GNNs for odor prediction. If you are interested in getting started with Graph Neural Networks, here is a comprehensive [overview](https://arxiv.org/pdf/1812.08434.pdf) of the different GNNs and their applications.

\\
Here is a [playlist](https://www.youtube.com/playlist?list=PLFInMJnvb3owAddRh4qk2gCX25kGLDay-) of videos on unsupervised learning methods such as PCA by Rene Vidal from Johns Hopkins University.

\\
If you are ever interested in converting a pretrained TensorFlow model to PyTorch, Thomas Wolf has you covered in this [blog post](https://medium.com/huggingface/from-tensorflow-to-pytorch-265f40ef2a28).

\\
Want to learn about generative deep learning? David Foster wrote a great [book](https://www.oreilly.com/library/view/generative-deep-learning/9781492041931/) that teaches data scientists how to apply GANs and encoder-decoder models for performing tasks such as painting, writing, and composing music. Here is the [official repository](https://github.com/davidADSP/GDL_code) accompanying the book, it includes TensorFlow code. There is also an [effort](https://github.com/MLSlayer/Generative-Deep-Learning-Code-in-Pytorch) to convert the code to PyTorch as well.

\\
A Colab [notebook](https://colab.research.google.com/drive/1rjjjA7teiZVHJCMTVD8KlZNu3EjS7Dmu#scrollTo=T9xtzFTJ1Uwf) containing code blocks to practice and learn about causal inference concepts such as interventions, counterfactuals, etc.

\\
Here are the [materials](https://github.com/huggingface/naacl_transfer_learning_tutorial) for the NAACL 2019 tutorial on “Transfer Learning in Natural Language Processing” delivered by Sebastian Ruder, Matthew Peters, Swabha Swayamdipta and Thomas Wolf. They also provided an accompanying Google Colab [notebook](https://colab.research.google.com/drive/1iDHCYIrWswIKp-n-pOg69xLoZO09MEgf) to get started.

\\
Another great [blog post](https://jalammar.github.io/visual-numpy/) from Jay Alammar on the topic of data representation. He also wrote many other interesting illustrated guides that include [GPT-2](http://jalammar.github.io/illustrated-gpt2/) and [BERT](http://jalammar.github.io/a-visual-guide-to-using-bert-for-the-first-time/). Peter Bloem also published a very detailed [blog post](http://peterbloem.nl/blog/transformers) explaining all the bits that make up a Transformer.


![] (https://miro.medium.com/max/1094/1*MIS8yQRqbP-c6eldo9K4QQ.png)
A visual illustration of basic self-attention — [source](http://peterbloem.nl/blog/transformers)

\\
Here is a nice overview of trends in NLP at ACL 2019, written by [Mihail Eric](https://www.mihaileric.com/posts/nlp-trends-acl-2019/). Some topics include infusing knowledge into NLP architectures, interpretability, and reducing bias among others. Here are a couple more overviews if you are interested: [link 2](https://medium.com/@mgalkin/knowledge-graphs-in-natural-language-processing-acl-2019-7a14eb20fce8) and [link 3](http://noecasas.com/post/acl2019/).

\\
The full syllabus for CS231n 2019 edition was [released](http://cs231n.stanford.edu/syllabus.html) by Stanford.

\\
David Abel [posted](https://david-abel.github.io/notes/iclr_2019.pdf) a set of notes for ICLR 2019. He was also nice to provide an [impressive](https://david-abel.github.io/notes/neurips_2019.pdf) summary of NeurIPS 2019.

\\
This is an excellent [book](http://d2l.ai/) that provides learners with a proper introduction to deep learning with notebooks provided as well.


![](https://miro.medium.com/max/560/0*_Rr1ogWtztlm3ffH.png)
[source](http://d2l.ai/)

\\
An illustrated [guide](http://jalammar.github.io/illustrated-bert/) to BERT, ELMo, and co. for transfer learning NLP.


![](https://miro.medium.com/max/1098/0*wywWzpKhTISgCtq5.png)

\\
Fast.ai [releases](https://www.fast.ai/2019/01/24/course-v3/) its 2019 edition of the “Practical Deep Learning for Coders” course.

\\
[Learn](https://sites.google.com/view/berkeley-cs294-158-sp19/home) about deep unsupervised learning in this fantastic course taught by Pieter Abbeel and others.

\\
Gilbert Strang [released](http://math.mit.edu/~gs/learningfromdata/') a new book related to Linear Algebra and neural networks.

\\
Caltech provided the entire syllabus, lecture slides, and video playlist for their course on [“Foundation of Machine Learning”](http://tensorlab.cms.caltech.edu/users/anima/cs165.html).

\\
The “[Scipy Lecture Notes](https://scipy-lectures.org/)” is a series of tutorials that teach you how to master tools such as matplotlib, NumPy, and SciPy.

\\
Here is an excellent [tutorial](https://peterroelants.github.io/posts/gaussian-process-tutorial/) on understanding Gaussian processes. (Notebooks provided).

\\
This is a must-read [article](https://lilianweng.github.io/lil-log/2019/01/31/generalized-language-models.html) in which Lilian Weng provides a deep dive into generalized language models such as ULMFit, OpenAI GPT-2, and BERT.

\\
[Papers with Code](https://paperswithcode.com/) is a website that shows a curated list of machine learning papers with code and state-of-the-art results.

\\
Christoph Molnar released the first edition of “[Interpretable Machine Learning](https://christophm.github.io/interpretable-ml-book/)” which is a book that touches on important techniques used to better interpret machine learning algorithms.

\\
David Bamman [releases](http://people.ischool.berkeley.edu/~dbamman/nlp18.html) the full syllabus and slides to the NLP courses offered at UC Berkley.

\\
Berkley [releases](https://github.com/dbamman/anlp19) all materials for their “Applied NLP” class.

\\
Aerin Kim is a senior research engineer at Microsoft and [writes](https://towardsdatascience.com/@aerinykim) about topics related to applied Math and deep learning. Some topics include intuition to conditional independence, gamma distribution, perplexity, etc.

\\
Tai-Danae Bradley wrote this [blog post](https://www.math3ma.com/blog/matrices-as-tensor-network-diagrams) discussing ways on how to think about matrices and tensors. The article is written with some incredible visuals which help to better understand certain transformations and operations performed on matrices.

![] (https://miro.medium.com/max/1600/0*TLepZbfBk5EjK1E0.jpg)
[source](https://www.math3ma.com/blog/matrices-as-tensor-network-diagrams)

----------

I hope you found the links useful. I wish you a successful and healthy 2020!
Due to the holidays, I didn’t get much chance to proofread the article so any feedback or corrections are welcomed!
>> [PDF version](https://github.com/omarsar/nlp_highlights) <<











