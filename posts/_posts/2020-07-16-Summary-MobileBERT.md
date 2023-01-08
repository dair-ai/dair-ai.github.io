---
layout: post
title: "MobileBERT"
author: viktor2k
excerpt: "A paper summary of _MobileBERT -  a Compact Task-Agnostic BERT for Resource-Limited Devices_ which covers the main motivation behind this work, their contribution and experimental findings."
modified:
comments: true
tags: []
image:
  thumb: ../images/summary-mobilebert/title-image.jpg
---

As the size of NLP model increases into the hundreds of billions of parameters, so does the importance of being able to create more compact representations of these models. **Knowledge distillation** has successfully enabled this where in one instance [96% of the teacher’s performance was retained in a 7x smaller model](https://medium.com/dair-ai/tinybert-size-does-matter-but-how-you-train-it-can-be-more-important-a5834831fa7d). However, knowledge distillation is still considered an afterthought when designing the teacher models which could reduce the effectiveness, leaving potential performance improvements for the student on the table.

\\
Further, the difficulties in fine-tuning small student models after the initial distillation, without degrading their performance, requires us to both pre-train and fine-tune the teachers on the tasks we want the student to be able to perform. Training a student modell through knowledge distillation will therefore require _more_ training compared to only training the teacher, which limits the benefits of a student model to inference-time.

\\
What would be possible if, instead, knowledge distillation was put front and centre during design and training of the teacher model? Could we design and successfully train a model that is _supposed_ to be distilled and could the distilled version successfully be fine-tuned on any down stream task? These are some of the questions adressed in [MobileBERT: a Compact Task-Agnostic BERT for Resource-Limited Devices](https://www.aclweb.org/anthology/2020.acl-main.195.pdf) which this article will provide a summary of.

# The MobileBERT architectures
![Architecture visualisation of transformer blocks within (a) BERT, (b) MobileBERT teacher and (c) MobileBERT student. The green trapezoids marked with “Linear” are referred to as bottlenecks. [Source](https://www.aclweb.org/anthology/2020.acl-main.195.pdf)](../images/summary-mobilebert/architecture-teacher-and-student.jpg)

## Linear
Knowledge distillation require us to compare teacher and student representations so that the difference between these can be minimised. This is straight forward when both matrices or vectors are of the same dimension. Therefore, MobileBERT introduces a _bottleneck_ layer into the transformer block. This allows the input to both student and teacher to be equivalent in size while their internal representations can differ. These bottlenecks are shown as green trapezoids marked with “Linear” in the figure above. In this particular case is the shared dimension 512, while the internal representation sizes for teacher and student are 1024 and 128 respectively. This allows us to use a BERT-large (340M parameters) equivalent model to train a 25M parameter student.

\\
Further, since input and output dimensions of each transformer block are the same for both models, it is possible to transfer both embedding and classifier parameters from teacher to student simply by copying them!

## Multi-Head Attention
The observant reader will have noticed that the input to the Multi-Head Attention block (MHA) is not the output from the prior linear projection. Instead, the initial input is used. There is no motivation for this design choice in the paper, which leave us to speculate. I believe the reason is the increased dimensions of freedom it allows. Basically, we separate how the model is forced to process the information into two separate streams, one fed into the MHA block and the other as a skip-connection. (It’s also quite easy to convince oneself that using the output from the linear projection does not change the behaviour of the MHA block due to its initial linear transform)

## Stacked FFN
To achieve high enough capacity within the small student, the authors introduce what they call _stacked FFN_, shown as a dashed box within the student model overview in the image above. Stacked FFN’s simply repeats the Feed Forward + Add & Norm blocks 4 times, which is chosen to achieve a good parameter ratio between MHA and FFN blocks. Ablation studies in this work show that the best performance is achieved when this ratio is in the range 0.4-0.6.

## Operational optimisations
Due to one of the goals being to enable fast inference on resource limited devices did the authors identify two areas where their architecture could be further improved.
1. Replace the smooth GeLU activation function for ReLU
2. Swap the normalisation operation for an element-wise linear transformation

# Proposed knowledge distillation objectives
To achieve knowledge transfer between the proposed teacher and student, the authors applies knowledge distillation at three staged of the model:
1. **Feature map transfer** - Allows the student to mimic the teacher at each transformer layer output. It the architecture image, this is shown as a dashed arrow between the output of the models.
2. **Attention map transfer** - Which tokens the teacher attend to at different layers and heads is another important property we want the student to learn. This is enabled through minimising the difference between the attention distributions (the KL-divergence) at each layer and head.
3. **Pre-training distillation** - It is also possible to use distillation during pre-training through combining both Masked Language Modelling and Next Sentence Prediction tasks in a linear combination.

With these objectives, there are more than one way we can perform knowledge distillation. The authors propose three alternatives:
1. **Auxiliary knowledge transfer** - The layer-wise knowledge transfer objectives are minimised together with the main objectives - masked language modelling and next sentence prediction. This can be considered the most simple approach.
2. **Joint knowledge transfer** - Instead of trying to achieve all objectives at once, it is possible to separate knowledge distillation and pre-training into two stages of training. First, all layer-wise knowledge distillation objectives are minimised until convergence, then further training with the pre-training objective is performed.
3. **Progressive knowledge transfer** - The two step approach can be taken even further. Errors not yet minimised properly in early layers will propagate and affect the training of later layers if all layers are trained simultaneously. It might, therefore, be better to train one layer at a time while freezing or reducing the learning rate of previous layers.

\\
![Knowledge transfer techniques. (a) Auxiliary knowledge transfer, (b) joint knowledge transfer, (c) progressive knowledge transfer. [Source](https://www.aclweb.org/anthology/2020.acl-main.195.pdf)](../images/summary-mobilebert/training-strategies.jpg)

# Experimental results
The authors evaluate their proposed MobileBERT in three configurations; the main model with 25M parameters (MobileBERT), the same model without the operational optimisations (MobileBERT w/o OPT), as well as a model with only 15M parameters (MobileBERT-tiny). These models were compared to both baseline algorithms such ELMo, GPT and BERT-base as wells as related distillation work: BERT-PKD, [DistilBERT](https://medium.com/dair-ai/tl-dr-distillbert-8fb0f9e3c03d) and [TinyBERT](https://medium.com/dair-ai/tinybert-size-does-matter-but-how-you-train-it-can-be-more-important-a5834831fa7d).

\\
Training these variations of MobileBERT was found to be most effective through the progressive knowledge transfer process, which consistently outperformed the other two by a significant margin.

\\
![Experimental results on the GLUE benchmark. [Source](https://www.aclweb.org/anthology/2020.acl-main.195.pdf)](../images/summary-mobilebert/results-glue.jpg)

\\
What we find is that MobileBERT w/ o OPT outperforms the much larger BERT-base by 0.2 average GLUE score, while being 4x smaller. MobileBERT on the other hand is only 0.6 points behind BERT-base while having a much faster inference time - 62 ms for a sequence of 128 tokens on a Pixel 4 phone! Its performance is however still competitive, since it outperform GTP and ELMo by a significant margin.

> It’s therefore safe to conclude that it it possible to create a distilled model which both can be performant and fast on resource limited devices!

MobileBERT-tiny achieves slightly better performance compared to TinyBERT. This does however become even more impressive when you consider how TinyBERT was fine-tuned for the GLUE tasks. Remember, prior to this work it was not possible to fine-tune the students due to their small capacity. TinyBERT’s teacher BERT-base, therefore, had to be fine tuned before its knowledge could be distilled into TinyBERT! That is **not** the case for MobileBERT. It’s been fine-tuned by itself on GLUE which proves that it’s possible to create a task agnostic model through the proposed distillation process!

# Conclusion
MobileBERT introduces bottlenecks in the transformer blocks, which allows us to more easily distil the knowledge from larger teachers into smaller students. This technique allows us to reduce the width rather than the depth of the student, which is known to produce a more capable model. This model highlight the fact that _it's possible to create a student model which by itself can be fine-tuned after the initial distillation process._

\\
Further, the results also show that this holds true in practice too as _MobileBERT is able to reach 99.2% of BERT-base's performance on GLUE with 4x fewer parameters and 5.5x faster inference on a Pixel 4 phone!_
