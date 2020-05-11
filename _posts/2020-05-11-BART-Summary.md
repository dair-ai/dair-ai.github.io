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
Lewis and et al. in this paper present valuable comparative work on different pre-training techniques and show how this kind of work can be used to guide large pre-training experiments reaching SOTA results. 

## **What does it propose?**
The authors propose a framework to compare pre-training techniques and Language Model objectives. This framework focuses on how these techniques can be viewed as **Corrupting text with an arbitrary noising function while the Language Model is tasked with denoising it.** After some comparative experiments using this framework, BART is introduced as a Transformers-based LM that reaches SOTA performance.

## **How does it work?** 

### **The Framework**
![image](https://lh3.googleusercontent.com/_ZYOOgt3efQF8LlFM_rmlJdiQyj3bkFeKfeihhbOK3w-UvPUPvFX9K_YFMh7SIURsyFclNwkL8oVByH3XlQKXPnhZYO8IFY54nhFBlE9wuk0vJBKxI1Ci_7xnbePqT8thQC-vB1ZUvs)
The idea behind the framework the authors propose is simple, they suggest that decoupling Language Models and the functions with which we corrupt the text is useful to compare different pre-training techniques and see how they fare on similar models and diverse benchmarks. Viewed this way pre-training is a sequence of repeated steps 
* We apply a noising function to the text 
* The language model attempts to reconstruct the text
* We calculate the Loss Function, typically CrossEntropy over the original text, we back-propagate the gradients and update the model's weights.
        
### **Comparing different Text-Noising techniques and LM Objectives**
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FAntonioLprd%2FdqcEKBSd0Y.png?alt=media&token=2cee8cc9-cb39-472f-9377-82c995a7ee85)
In the first experiment detailed in the paper Lewis et al., using the framework they introduced at the beginning of the article, compare different pre-training techniques and LM Objectives on a smaller than usual model, BART-base. The model uses a 6 layered, transformer-based, Seq2Seq architecture for autoencoding as introduced in the **"Attention is all you need"** paper from Vaswani et al. The pre-training techniques compared in the experiments can be divided between those that work at the token level and the ones that work at the sentence level.

**Token Masking** random tokens are sampled and replaced with [MASK]<br />
**Token Deletion** similar to masking but the token sampled are deleted and the model has to add new token in their place.<br />
**Token Infilling** a number of text spans, i.e. contiguous group tokens, are sampled, and then they are replaced by the [MASK] token.<br />
**Sentence Permutation** random shuffling of the document’s sentences.<br />
**Document Rotation** a token is chosen randomly to be the start of the document, the section before the starting token is appended at the end.<br />

Intuitively the techniques that work at the sentence level should help the LM learn the different roles of sentences in a paragraph or longer text and so help in NLG tasks.

Besides the pre-training techniques, the authors also compare different LM objectives focusing on the ones used by BERT and GPT and also the ones that tried to get the best of both worlds.

**Autoregressive, left to right, LM** (GPT-2)<br />
**Masked LM**(BERT) replace 15% of the token with [MASK] and predict the corresponding words.<br />
**Permuted LM** (XLNet) left to right, autoregressive LM training but with the order of the words to predict chosen at random. (worth looking into more, very interesting approach)<br />
**Multitask Masked LM** (UniLM) combination of right-to-left, left-to-right and Bidirectional. ⅓ of the time using each with shared parameters.<br />
**Masked Seq2Seq** (MASS) masking a span containing 50% of the tokens and train to  predict the masked tokens.<br />
        
### **Results of the first experiment**
![](https://lh6.googleusercontent.com/YxPMuTJc7EY2rFYIXUBVIYMjV-rloyEj2UmgJ6pbxyyMDCWzdwu4KOgRErOKJcmDe4QfC7LO-2bGE6-_0pCF1lRwJfFbjGvBbuk73oFQ8AgMdHAYDNIwDH8HlEcBI15SQKTUMIUhc_8)
    
From the results of this first experiments the authors draw some important conclusions.<br />
**Token masking is crucial** Only the configurations with token masking or its variations achieve consistently great performance on different tasks.<br />
**Left-to-right pre-training improves NLG** The Classical Language Model objective despite not doing well in inference or QA tasks achieves SOTA on ELI5(Explain Like I'm 5) a NLG benchmark that with longer sequences values coherent and grammatically correct text.<br />
**Bidirectional encoders are crucial for QA** Ignoring future context hinders the performance of left-to-right models.<br />

One Interesting note from the authors in this experiment explains how while pre-training techniques and LM objectives are important they don't tell the whole story. They report that their Permuted Language model performs much worse than XLNet due to some of the valuable architectural innovations introduced in XLNet that are not present in BART.
    
### **Results of the Large Scale Pre-training experiment**
After the comparative experiment, the authors trained a bigger model with 12 layers, transformer-based architecture for autoencoding, and similar hyperparameters to RoBERTa. They used both a form of token masking at 30% and sentence permutation as pre-training text-noising techniques and run the model on 160GB of news, books, stories, and web text, again similarly  to RoBERTa
![](https://lh4.googleusercontent.com/grHkzO3a2zUtdo-_AkH3sGhWmfGQ9_n4bAD0wm78kzVLpuzYFFdSwycnLIevdGUb5jVMJpGdA46LvZN_k0PDrCCObljSvgfcTo6PHevfpa5ZonMXn-C5tEXsUW1V33akbAIINi7whkA)

BART proves especially capable in abstractive summarization talks especially in the **XSum** benchmark that as oppose to the CNN/DailyMail data-set contains very few examples of summaries where phases are present both in the summary and the original text. Besides surpassing the previous best systems in summarization by a considerable margin BART does well also in NLI tasks and QA where it is on par with the SOTA. 

### **Qualitative Analysis**
The paper features also examples of the summaries produced by BART that can really give a sense of how well it does on the XSum data-set.
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FAntonioLprd%2F7kziiycrsc.png?alt=media&token=a6812c61-8d4b-4f0b-ac0c-e36c470dad45)
If you want to summarize some text of your own we have set up a [Google Colab notebook](https://colab.research.google.com/drive/1ufNmxZz3v8LloGAYFJvTM2Git2aNe83R?usp=sharing) using the Hugging Face library. 
