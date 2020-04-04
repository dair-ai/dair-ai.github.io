---
layout: post
title: "An Overview of Troubling Trends in Machine Learning Scholarship"
author: 
excerpt: "...troubling trends in machine learning (ML) scholarship…"
modified:
comments: true
tags: []
image:
  thumb: 
---#

\\
A new [paper](https://arxiv.org/abs/1807.03341) presented in ICML 2018 describes some of the troubling trends in machine learning (ML) scholarship. The authors, Zachary C. Lipton and Jacob Steinhardt, discuss the implications of these trends on the field of ML and the proper distilling of machine learning research and knowledge.

\\
Machine learning (ML) research aims to disseminate knowledge about data-driven algorithms through theoretical characterizations and or empirical results. The field of ML is growing rapidly, at an unprecedented scale and speed, with certain troubling patterns emerging which could negatively affect meaningful progress in the field, **poorly serving to researchers and enthusiasts.

\\
ML research is most valuable when communicated properly to the interested reader by avoiding the presentation of speculations as facts and other misleading interpretations and explanations. Lipton and Steinhardt propose several ways to combat some of the troubling trends occurring in the ML community, particularly as it relates to the poor dissemination of foundational knowledge and empirical results. The overall goal is to communicate research and findings with greater clarity and to pay closer attention to the following troubling patterns:

### **Explanation vs. Speculation**

In writing, speculation encompasses a whole range of techniques used to explain concepts and intuitions without providing proper evidence or formal definitions. For example, we claim that X produces Y given some conditions Z. We know X and Y to be true, but we don’t know if all conditions Z apply because we haven’t formally defined them. Yet we claim that all conditions Z seem to work even when we haven’t defined them properly. Just because the reader isn’t aware or doesn’t care about all Zs it doesn’t mean the claim warrants validity — *it’s “explanation disguised as speculation.”*

\\
This is a risky form of science communication since other researchers may blindly use them as facts in their work, further increasing the severity and reach of the initial speculation. It’s important to avoid asserting speculations as facts and explicitly separating them from facts when using them. (See actual examples in the paper)

![](https://miro.medium.com/max/1120/0*DmfsfA-JCsWXi7Pn.png)


### **Failure to Identify the Sources of Empirical Gains**

Sometimes ML researchers propose complex models that combine several techniques to address a problem. Even though the proposed approach does well, authors sometimes fail to identify the source/s of empirical gains.
The problem is that this may generate a false impression that the authors did a lot of work when in reality the improvements were incremental and only occurred due to a small change. This can sometimes be minimized and clarified by performing proper ablation studies. (See more examples in the paper)
\\
![](https://miro.medium.com/max/752/0*m5KmxuY3L0zw0SWo.png)


### **Mathiness**

Mathiness is a concept proposed by economist Paul Romer that describes the idea of using both natural language and mathematics to explain concepts but failing to provide tight links between statements and symbols. Mathiness manifests in many ways such as authors trying to pile math equations to convey technical depth without proper explanations and linkings.
The problem with this approach is that clarity suffers, distracting the readers from acquiring the important knowledge and insights of the research. The best remedy seems to be avoiding the use of mathiness and providing clear explanations of the formulations so that it benefits all kinds of readers and not just ML researchers.
\\
![](https://miro.medium.com/max/752/0*cd3SbJbw0cqseDP4.png)


### **Misuse of Language**

Lipton and Steinhardt currently identified three types of language misuse in machine learning research: *suggestive definitions*, *overloaded terminology*, and *suitcase words*. Let’s briefly describe the three below:

\\
- ***Suggestive definitions*** — This occurs when authors coin suggestive terms that convey human qualities (i.e., anthropomorphic characterizations) such as “thought vectors.” These type of terms are not necessarily bad but if not qualified may only confuse readers.
- ***Overloaded terminology*** — This refers to the inappropriate or contradictory use of a technical term that already holds a very precise meaning in the literature. An example is the misuse of the term “deconvolution” to refer to transpose convolution as opposed to “reversing a convolution” which is what it originally describes.
- ***Suitcase words*** — This refers to terms that may pack many different meanings, often creating a confusion to readers with different backgrounds. These type of words could also manifest in the form of suggestive definitions and overloaded terminology as explained above. Some notorious examples include “generalization”, “interpretability”, and “bias.” Loosely using these type of words is common practice but often detracts and confuse readers.
\\
![](https://miro.medium.com/max/752/0*zIrt9rR0W6DGzBYA.png)


### **Potential Causes Behind Troubling Trends**

Lipton and Steinhardt also discuss the potential causal factors to these troubling trends in ML scholarship:

\\
- **Complacency in the face of progress** — This describes the notion that authors feel entitled to make weak arguments because they are already providing strong results. This poses a problem since reviewers may feel pressured to accept potentially flawed papers only to compensate for the quantitative findings.
- **Growing pains** — ML is expanding rapidly and thus increases the entrance of inexperienced researchers which are more susceptible to the misuse of language. This is not to say that experienced researchers cannot fall into these patterns, especially when their reviewing responsibilities increase with the rapid growth of the field. This is not to discourage junior researchers, but spreading awareness of these issues is key to conducting proper research.
- **Misaligned incentives** — As ML becomes more popular, both the media and startup investors seek to provide incentives for things which may not be aligned with the objectives of the field. For instance, anthropomorphic descriptions, such as “simulated brain”, may be effective for popular coverage but could actually cause confusion in the ML community and literature.
![](https://miro.medium.com/max/752/0*hF1JDenZ0JdCUNkL.png)


### **Suggestions**

Besides recommending that authors — experienced and inexperienced — refrain from participating in these trends, Lipton and Steinhard outline a few preliminary suggestions:

\\
- **What, Why, How** — Identify “what worked” and provide clear details explaining “why it worked”, and not just “how well it worked.”
- **Insights** — Authors are encouraged to provide error analysis, ablation studies, and robustness check. Besides identifying empirical gains, authors can also discuss insights with strong evidence to support them.
- **Writing tips** — Authors are recommended to revise important questions and theorems reported in the research, with clarity, flow, and precision in mind. Open problems can also be separated from closed ones when offering discussions to avoid confusion and to encourage follow-up research. Other suggestions are also provided for publishers and reviewers. (See paper for more details)
![](https://miro.medium.com/max/752/0*879_wpeyAGluJXTj.png)

\\
Overall, it’s important to avoid the use of confusing terminology (e.g. anthropomorphic characterization) and unsupported claims. Greater rigor is essential for the healthy growth of ML scholarship and scientific progress more broadly. There are special cases where the recommendations set forth above may actually hurt the fast pace of research. In some cases, original ideas may even be impeded. However, historically speaking, undisciplined scholarship affects both researchers and the public, which means there could potentially emerge a crisis and a “lack of meaningful progress.”

### **Final Words From the Editor**

\\
Machine learning has grown tremendously over the past few years and it promises to be at the epicenter of “everything technology.” It’s the responsibility of everyone — researchers, students, reviewers, industry, startups, lawmakers, and everyone involved — to participate in the debate and to ensure the proper distilling of machine learning research and knowledge in a transparent and accurate way. We are responsible for guiding the conversation in the right direction and to avoid harming the ML field and science more broadly.

----------

### *Ref:* [https://arxiv.org/abs/1807.03341](https://arxiv.org/abs/1807.03341) — “Troubling Trends in Machine Learning Scholarship**”** — ****Zachary C. Lipton and Jacob Steinhardt

