---
layout: post
title: "BART: Are all pretraining techniques created equal?"
author: AntonioLopardo
modified:
comments: true
tags: ""
image:
  thumb: BART_Board_cropped_more.jpg
---
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FAntonioLprd%2FMp23o_Xx8j.jpg?alt=media&token=72dbb3c1-93a5-4b9d-8cec-3e006952568e)

> Paper summary: BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension , Oct. 2019. ([link](https://arxiv.org/abs/1910.13461))

## **Why is this important?**
In this paper, Lewis et al. present valuable comparative work on different pre-training techniques and show how this kind of work can be used to guide large pre-training experiments reaching state-of-the-art (SOTA) results.

## **What does it propose?**
The authors propose a framework to compare pre-training techniques and language model (LM) objectives. This framework focuses on how these techniques can be viewed as **corrupting text with an arbitrary noising function while the Language Model is tasked with denoising it.** After some comparative experiments using this framework, BART is introduced as a transformer-based LM that reaches SOTA performance.

## **How does it work?**

### **The Framework**
![image](https://lh3.googleusercontent.com/_ZYOOgt3efQF8LlFM_rmlJdiQyj3bkFeKfeihhbOK3w-UvPUPvFX9K_YFMh7SIURsyFclNwkL8oVByH3XlQKXPnhZYO8IFY54nhFBlE9wuk0vJBKxI1Ci_7xnbePqT8thQC-vB1ZUvs)
The idea behind the proposed framework is simple, they suggest that decoupling language models and the functions with which the text are corrupted is useful to compare different pre-training techniques and see how they perform on similar models and diverse benchmarks. Viewed this way, pre-training is a sequence of repeated steps:
* Apply a noising function to the text
* The language model attempts to reconstruct the text
* Then calculate the loss function (typically cross entropy over the original text) and then back-propagate the gradients and update the model's weights.

### **Comparing different text-noising techniques and LM Objectives**
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FAntonioLprd%2FdqcEKBSd0Y.png?alt=media&token=2cee8cc9-cb39-472f-9377-82c995a7ee85)

\\
In the first experiment, using the framework they introduced at the beginning of the article, the authors compared different pre-training techniques and LM objectives on a smaller than usual model, BART-base. The model uses a 6 layered, transformer-based, seq2seq architecture for autoencoding as introduced by [Vaswani et al](https://arxiv.org/pdf/1706.03762.pdf). The pre-training techniques compared in the experiments can be divided between those that work at the token level and those that work at the sentence level:

\\
**Token Masking:** random tokens are sampled and replaced with [MASK]

\\
**Token Deletion:** similar to masking but the sampled tokens are deleted and the model has to add a new token in their place.

\\
**Token Infilling:** a number of text spans, i.e. contiguous group tokens, are sampled, and then they are replaced by the [MASK] token.

\\
**Sentence Permutation:** random shuffling of the document’s sentences.

\\
**Document Rotation** a token is chosen randomly to be the start of the document, the section before the starting token is appended at the end.

\\
Intuitively, the techniques that work at the sentence level should help the LM learn the different roles of sentences in a paragraph or longer text and in the process help dealing with natural language generation(NLG) tasks.

\\
Besides the pre-training techniques, the authors also compare different LM objectives focusing on the ones used by BERT and GPT as well as techniques that tried to incorporate the best of both worlds:

\\
**Autoregressive, left to right, LM** ([GPT-2](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf))

\\
**Masked LM** ([BERT](https://arxiv.org/abs/1810.04805)) replace 15% of the token with the [MASK] token and predict the corresponding words.

\\
**Permuted LM** ([XLNet](https://arxiv.org/pdf/1906.08237.pdf)) left to right, autoregressive LM training but with the order of the words to predict chosen at random.

\\
**Multitask Masked LM** ([UniLM](https://arxiv.org/pdf/1905.03197.pdf)) combination of right-to-left, left-to-right and bidirectionality. ⅓ of the time using each with shared parameters.

\\
**Masked Seq2Seq** ([MASS](https://arxiv.org/pdf/1905.02450.pdf)) masking a span containing 50% of the tokens and train to predict the masked tokens.



### **Results of the first experiment**
![](https://lh6.googleusercontent.com/YxPMuTJc7EY2rFYIXUBVIYMjV-rloyEj2UmgJ6pbxyyMDCWzdwu4KOgRErOKJcmDe4QfC7LO-2bGE6-_0pCF1lRwJfFbjGvBbuk73oFQ8AgMdHAYDNIwDH8HlEcBI15SQKTUMIUhc_8)

\\
From the results of this first experiments the authors draw some important conclusions.

\\
**Token masking is crucial**

\\
Only the configurations with token masking or its variations achieve consistently great performance on different tasks.

\\
**Left-to-right pre-training improves NLG**

\\
The classical LM objective despite not doing well in inference or question answering tasks, achieves SOTA on ELI5 (Explain Like I'm 5).

\\
**Bidirectional encoders are crucial for QA**

\\
Ignoring future context hinders the performance of left-to-right models.

\\
While pre-training techniques and LM objectives are important, the authors make note of the fact that they do not provide the full picture. They report that their permuted language model performs much worse than XLNet because BART lacks some of the valuable architectural innovations introduced in XLNet.

### **Results of the large-scale pre-training experiment**
After the comparative experiment, the authors trained a 12 layered, transformer-based architecture for autoencoding, and using similar hyperparameters to [RoBERTa](https://arxiv.org/pdf/1907.11692.pdf). They used both a form of token masking at 30% and sentence permutation as pre-training text-noising techniques and run the model on 160GB of news, books, stories, and web text, similar to what's done in RoBERTa.

\\
![](https://lh4.googleusercontent.com/grHkzO3a2zUtdo-_AkH3sGhWmfGQ9_n4bAD0wm78kzVLpuzYFFdSwycnLIevdGUb5jVMJpGdA46LvZN_k0PDrCCObljSvgfcTo6PHevfpa5ZonMXn-C5tEXsUW1V33akbAIINi7whkA)

\\
BART performs best in abstractive summarization tasks especially in the **XSum** benchmark that contains very few examples of summaries where phrases are present both in the summary and the original text. Besides surpassing the previous best systems in summarization by a considerable margin, BART does well also in natural language inference (NLI) tasks and QA, where it is on par with SOTA results.

### **Qualitative Analysis**
The paper also features examples of the summaries produced by BART that can really give a sense of how well it does on the XSum dataset:

\\
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FAntonioLprd%2F7kziiycrsc.png?alt=media&token=a6812c61-8d4b-4f0b-ac0c-e36c470dad45)

\\
If you want to summarize some text of your own we have set up a [Google Colab notebook](https://colab.research.google.com/drive/1ufNmxZz3v8LloGAYFJvTM2Git2aNe83R?usp=sharing) using the Hugging Face library.
