---
layout: post
title: "XLNet outperforms BERT on several NLP Tasks"
author: billy_rick
excerpt: "XLNet is a new pretraining method for NLP that achieves state-of-the-art results on several NLP tasks."
modified:
comments: true
tags: ""
image:
  thumb: xlnet.png
---

Two pretraining objectives that have been successful for pretraining neural networks used in transfer learning NLP are autoregressive (AR) language modeling and autoencoding (AE).

\\
Autoregressive language modeling is not able to model deep bidirectional context which has recently been found to be effective in several downstream NLP tasks such as sentiment analysis and question answering.

\\
On the other hand, autoencoding based pretraining aims to reconstruct original data from corrupted data. A popular example of such modeling is used in BERT, an effective state-of-the-art technique used to address several NLP tasks.

\\
One advantage of models like [BERT](https://arxiv.org/pdf/1810.04805.pdf) is that bidirectional contexts can be used in the reconstruction process, something that AR language modeling lacks. However, BERT partially masks the input (i.e. tokens) during pretraining which results in a _pre-training-finetune discrepancy_. In addition, BERT assumes independence on predicted tokens, something which AR models allow for via the product rule which is used to factorize the joint probability of predicted tokens. This could potentially help with the pretrain-finetune discrepancy found in BERT.

\\
The proposed model (XLNet) borrows ideas from the two types of language pretraining objectives (AR and AE) while avoiding their limitations.


### **The XLNet model**

![](https://miro.medium.com/max/904/0*jzfLbSYA-VH5P7rC.png)

\\
XLNet makes use of a _permutation operation_ during training time that allows context to consists of tokens from both left and right, capturing the bidirectional context, making it a generalized order-aware AR language model. During pretraining, XLNet adopts the segment recurrent mechanism and relative encoding scheme proposed in [Transformer-XL](https://medium.com/dair-ai/a-light-introduction-to-transformer-xl-be5737feb13).

\\
Essentially, the novel permutation language modeling objective (see paper for extra details) allows sharing of the model parameters across all the permuted factorization orders. This enables the AR model to properly and effectively capture bidirectional context while avoiding the independence assumption and pretrain-finetune discrepancy that BERT is subject to.

\\
Simply put it, XLNet keeps the original sequence order, uses positional encodings, and relies on a special attention mask in Transformers to achieve the said permutation of the factorization order. In other words, the original Transformer architecture is modified and re-parameterized to avoid issues such as target ambiguity and pretrain-finetune discrepancy.

\\
The core change happens in the hidden representation layers (see paper for details). XLNet is based on the Transformer-XL which it uses as the main pretraining framework. Obviously, for the proposed permutation operation to work, a few modifications are proposed, which enforce the proper reuse of the hidden states from previous segments. Some design ideas from BERT are also used to perform partial prediction and support certain tasks that consist of multiple segments like question and context paragraph in question answering.

\\
From the following examples below, we can observe that both BERT and XLNet compute the objective differently. In general, XLNet captures more important dependencies between prediction targets, such as (New, York), which BERT omits.

\\
![](https://miro.medium.com/max/598/0*Cd9pc-cuqQF5k0Oc.png)

\\
XLNet also proves to cover more dependencies as compared to [GPT](https://openai.com/blog/better-language-models/) and [ELMo](https://arxiv.org/abs/1802.05365).

\\
Overall, XLNet makes a compelling case for bridging the gap between language modeling and pretraining, all achieved by leveraging AR modeling and borrowing techniques from previous methods like BERT and Transformer-XL. More importantly, XLNet aims to address the pretrain-finetune discrepancy, which means language models can potentially improve downstream tasks through this useful generalization.

### **Experiments**

Several sources like BooksCorpus, English Wikipedia, Giga5, and Common Crawl are combined and used for pretraining. Tokenization is achieved with SentencePiece.

\\
The same architecture hyperparameters as BERT-Large are used in XLNet-Large and trained on 512 TPU v3 chips for 500K epochs with an Adam optimizer. A linear learning rate decay and a batch size of 2048 are used, all leading to roughly 2.5 days of training. XLNet-Large was not able to leverage the additional data scale, so XLNet-Base (analogous to BERT-Base) was used to conduct a fair comparison with BERT. This also means that only BooksCorpus and English Wikipedia were used for pretraining.

### **Results**

RACE involves a reading comprehension dataset that is used to test the question answering and long text understanding capabilities of the model. As shown in the table below, XLNet outperforms (in terms of accuracy) both GPT and BERT pretraining models.

\\
![](https://miro.medium.com/max/500/0*7xDJVCyYbphxn65f.png)

\\
SQuAD and NewsQA are also popular reading comprehension datasets which consist of two tasks. Specifically, XLNet jointly trains on SQuAD 2.0 and NewsQA and obtains state-of-the-art performance on this task, outperforming BERT even on the dev set (see results below).

\\
![](https://miro.medium.com/max/753/0*CfvEjCH291LqOSqU.png)

\\
XLNet now holds state-of-the-art (SoTA) results on several text classification benchmarks such as IMDB and DBpedia (see results below).

\\
![](https://miro.medium.com/max/711/0*GCN5tQTix-cl30Ne.png)

\\
GLUE consists of 9 natural language understanding tasks. Using XLNet, multiple settings such as single-task and multi-task, as well as single models and ensembles are tested on GLUE. In the end, a multi-task ensemble XLNet achieves SoTA results on 7 out of 9 tasks. XLNet outperforms BERT on the different datasets as seen in the table below.

\\
![](https://miro.medium.com/max/769/0*jRNEM-D8HUIijxOW.png)

\\
An interesting ablation study and extended results are provided in the paper to justify some of the design choices made in XLNet and how it compares with other models such as BERT and GPT.

\\
XLNet: _Generalized Autoregressive Pretraining for Language Understanding_ — (Zhilin Yang, Zihang Dai, Yiming Yang, Jaime Carbonell, Ruslan Salakhutdinov, and Quoc V. Le)

\\
[Paper](https://arxiv.org/abs/1906.08237) | [Code](https://github.com/zihangdai/xlnet)

\\
**Other suggested readings:**

- [Deep Learning for NLP: A Complete Overview](https://medium.com/dair-ai/deep-learning-for-nlp-an-overview-of-recent-trends-d0d8f40a776d)
- [A Light Introduction to Transfer Learning for NLP](https://medium.com/dair-ai/a-light-introduction-to-transfer-learning-for-nlp-3e2cb56b48c8)
- [Adapters: A Compact and Extensible Transfer Learning Method for NLP](https://medium.com/dair-ai/adapters-a-compact-and-extensible-transfer-learning-method-for-nlp-6d18c2399f62)
- [A Light Introduction to Transformer-XL](https://medium.com/dair-ai/a-light-introduction-to-transformer-xl-be5737feb13)
