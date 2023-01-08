---
layout: post
title: "NLP Newsletter #10 [PT-BR]: Aprimorando a reprodutibilidade em ML, Privacidade e Segurança em NLP, XTREME, Longformer, VilBERT, exBERT,…"
author: VictorGarritano
excerpt: "Nessa edição, são cobertos tópicos como melhores práticas envolvendo modelos de linguagem, reprodutibilidade em ML e privacidade e segurança no Processamento de Linguagem Natural (NLP)"
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_10.png
---


![](https://cdn-images-1.medium.com/max/1200/1*WxbP3uKvd2GB6B-NaxtiIw.png)

\\
Seja muito bem-vindo à 10ª edição da NLP Newsletter. Nós esperamos que todos estejam bem e se mantendo seguros. Essa edição cobre tópicos como melhores práticas envolvendo Modelos de Linguagem, reprodutibilidade em ML e privacidade e segurança em NLP.
<!-- Welcome to the 10th issue of the NLP Newsletter. We hope you are well and staying safe. In this issue, we cover topics that range from best practices regarding language models to reproducibility in machine learning to privacy and security in natural language processing (NLP). -->


# Atualizações da dar.ai 🔬🎓⚙️

- Com o intuito de ajudar na análise exploratória do [*COVID-19 Open Research Dataset*](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) e na obtenção de *insights* a partir dessa literatura, nós publicamos um [*notebook*](https://github.com/dair-ai/covid_19_search_application) com os passos para a implementação de uma aplicação simples de busca por similaridade textual utilizando ferramentas de código-aberto e modelos de linguagem pré-treinados publicamente disponíveis.

<!-- - In order to help in the exploration of the [COVID-19 Open Research Dataset](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) and obtain insights from scientific literature, we published a [notebook](https://github.com/dair-ai/covid_19_search_application) that walks through the steps of building a simple text similarity search application using open source tools and publicly available pretrained language models. -->

- Nós realizamos um treinamento virtual na [*Open Data Science Conference*](https://odsc.com/boston/) na semana passada, com o tema *Deep Learning for Modern NLP*. Você pode acessar os materiais [aqui](https://github.com/dair-ai/odsc_2020_nlp).

<!-- - We delivered a virtual training at the [Open Data Science Conference](https://odsc.com/boston/) this past week on ["Deep Learning for Modern NLP"](https://github.com/dair-ai/odsc_2020_nlp). Find materials here. -->

- Também na semana passada, nós publicamos dois artigos bem interessantes, numa colaboração com membros da nossa comunidade. Um dos trabalhos aborda [*unsupervised progressive learning*](https://medium.com/dair-ai/unsupervised-progressive-learning-upl-a-new-problem-for-ai-9a1c68c70a28), um problema que envolve um agente que analisa uma sequência de vetores de dados não anotados (fluxo de dados) e aprende representações a partir da mesma. O segundo [trabalho](https://medium.com/dair-ai/structural-scaffolds-for-citation-intent-classification-in-scientific-publications-e5acd2f0ebf9) resume uma abordagem para *Citation Intent Classification* (que consiste em identificar porquê um autor citou outro trabalho) utilizando o modelo ELMo.

<!-- - This past week we published two articles together with members of our community. One is about [unsupervised progressive learning](https://medium.com/dair-ai/unsupervised-progressive-learning-upl-a-new-problem-for-ai-9a1c68c70a28) which is a problem that involves an agent that analyzes a sequence of unlabelled data vectors (data stream) and learns representations from these. The second [article](https://medium.com/dair-ai/structural-scaffolds-for-citation-intent-classification-in-scientific-publications-e5acd2f0ebf9) summarizes an approach for citation intent classification using ELMo. -->


<!-- - We recently published a [notebook](https://colab.research.google.com/drive/1nwCE6b9PXIKhv2hvbqf1oZKIGkXMTi1X) that helps to provide ideas on how to fine-tune pretrained language models for the task of emotion classification. -->

- Nós publicamos recentemente um [*notebook*](https://colab.research.google.com/drive/1nwCE6b9PXIKhv2hvbqf1oZKIGkXMTi1X) que fornece ideias para o ajuste fino de modelos de linguagem pré-treinados para a tarefa de classificação de emoções.


# Pesquisas e Publicações 📙

***XTREME: A Massively Multilingual Multi-task Benchmark for Evaluating Cross-lingual Generalization***

\\
No início dessa semana, pesquisadores da Google AI e da DeepMind publicaram um interessante *benchmark* multi-tarefa denominado [XTREME](https://arxiv.org/abs/2003.11080), que busca encorajar a avaliação das capacidades de generalização em diferentes idiomas de modelos de linguagem que aprendem representações multilíngues. O *benchmark* conta com 40 idiomas e 9 tarefas, que requerem entendimento sobre diferentes níveis de significado, tanto do ponto de vista sintático quanto semântico. O trabalho fornece bases para comparações utilizando modelos estado-da-arte para representações multilíngues, como o mBERT, XML e o MMTE.

<!-- Earlier this week, researchers at Google AI and DeepMind published an interesting multi-task benchmark called [XTREME](https://arxiv.org/abs/2003.11080) that aims to encourage evaluation of the cross-lingual generalization capabilities of language models that learn multilingual representations. The benchmark tests on 40 languages and 9 different tasks that collectively require reasoning about different levels of meaning either syntactically or semantically. The paper also provides baseline results using state-of-the-art models for multilingual representation such as mBERT, XLM, and MMTE. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*kk7J1fCht_VZR_su.png)

*Fonte:* [*Google AI Blog*](https://ai.googleblog.com/2020/04/xtreme-massively-multilingual-multi.html)

\\
***Evaluating Machines by their Real-World Language Use***

\\
Foi demonstrado que modelos de linguagem apresentam um desempenho relativamente bom em diversas tarefas, como *question answering* e *sequence labeling*. Entretanto, um novo [artigo](https://arxiv.org/abs/2004.03607) propõe um *framework* e *benchmark* para melhor avaliar se modelos de linguagem (LMs) conseguem desempenhar bem seu papel com o uso de linguagem do mundo real em situações mais complexas (por exemplo, gerar conselhos proveitosos para o cenário atual do mundo). Resultados empíricos mostraram que modelos do estado-da-arte atual, como o T5, geram conselhos úteis como os escritos por humanos em apenas 9% dos casos. Essas observações apontam as deficiências dos LMs no que diz respeito a entender e modelar conhecimentos de mundo e do senso comum.

<!-- It has been shown that language models perform relatively well on a variety of tasks such as question answering and sequence labeling. However, a new [paper](https://arxiv.org/abs/2004.03607) proposes a framework and benchmark to better evaluate whether language models can perform at real-world language use with more complex settings (e.g., generating helpful advice for current situations). Empirical results demonstrate that current state-of-the-art models such as T5 generate advice that is as helpful as human-written advice in only 9% of the cases. These results point out the shortcomings of LMs in the ability to understand and model world knowledge and common-sense reasoning. -->

\\
***Give your Text Representation Models some Love: the Case for Basque***

\\
É possível que modelos monolíngues (como os *word embeddings* do FastText e o BERT) treinados em grandes bases de dados de idiomas específicos produzam melhores resultados que alternativas multilíngues? Num [artigo recente](https://arxiv.org/abs/2004.00033), pesquisadores estudaram o desempenho de diversos modelos desse tipo utilizando uma grande base de dados para a língua basca. Os resultados indicaram que modelos monolíngues podem de fato produzir melhores resultados em tarefas como classificação de tópicos, de sentimentos e *PoS tagging* para esse idioma. Seria muito interessante verificar se o comportamento se repete para outros idiomas e quais resultados interessantes e novos desafio podem surgir.

<!-- Can training monolingual models (FastText word embeddings and BERT) on large language-specific datasets produce better results than pretrained multilingual versions? In a recent [paper](https://arxiv.org/abs/2004.00033), researchers study the effect and performance of pertaining models using larger Basque corpora. Results indicate that indeed the model does produce better results on downstream tasks such as topic classification, sentiment classification, and PoS tagging for Basque. It could be interesting to test if this holds for other languages and whether there could some interesting results or new challenges that arise. -->


\\
![](https://cdn-images-1.medium.com/max/800/1*rN7mNPz0os7kd8rBboliIg.png)

*Figura extraída de* [*Agerri et al. (2020)*](https://arxiv.org/abs/2004.00033)

\\
***Advancing Self-Supervised and Semi-Supervised Learning with SimCLR***

\\
Numa [edição anterior](https://dair.ai/NLP_Newsletter-PT-BR-_The_Annotated_GPT-2,_Understanding/) da Newsletter, nós apresentamos o SimCLR, método desenvolvido pela Google AI que propõe um *framework* para *contrastive self-supervised learning* de representações visuais, com o objetivo de melhorar os resultados da tarefa de classificação de imagens em diferentes cenários, como *transfer-learning* ou aprendizado semi-supervisionado, utilizando bases não-anotadas. Os [resultados](https://ai.googleblog.com/2020/04/advancing-self-supervised-and-semi.html) obtidos demonstraram que a abordagem alcança resultados estado-da-arte no ImageNet utilizando apenas 1% de dados anotados, o que também é um indicativo das possíveis vantagens do método em cenários com escassez de dados.

<!-- In a previous [issue](https://medium.com/dair-ai/nlp-newsletter-the-annotated-gpt-2-understanding-self-distillation-haiku-ganilla-sparkwiki-b0f47f595c82) of the newsletter, we featured SimCLR, a method by Google AI that proposes a framework for *contrastive self-supervised learning* of visual representations for improving image classification results in different settings such as transfer learning and semi-supervised learning. It is a new approach to self-and semi-supervised learning to learn visual representations from unlabeled data. [Results](https://ai.googleblog.com/2020/04/advancing-self-supervised-and-semi.html) demonstrate that it achieves state-of-the-art results on ImageNet while only relying on 1% labeled data which indicates that the method could also be beneficial in low-resourced settings. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*kGiv7LFJW1g_R6m2XblSSA.png)

*Fonte:* [*Google AI Blog*](https://ai.googleblog.com/2020/04/advancing-self-supervised-and-semi.html)

\\
Vale mencionar que o aprendizado auto-supervisionado (*self-supervised learning*) é um dos tópicos mais quentes na área atualmente. Se você tem interesse em saber mais, confira:

<!-- It is worth mentioning that self-supervised learning is one of the hot topics in the field. If you are interested to know more you can check out the following: -->

- [Computers Already Learn From Us. But Can They Teach Themselves?](https://www.nytimes.com/2020/04/08/technology/ai-computers-learning-supervised-unsupervised.html)
- [The Illustrated Self-Supervised Learning](https://amitness.com/2020/02/illustrated-self-supervised-learning/)
- [Self-supervised learning and computer vision](https://www.fast.ai/2020/01/13/self_supervised/)

\\
***Byte Pair Encoding is Suboptimal for Language Model Pretraining***

\\
Kaj Bostrom and Greg Durrett publicaram um [trabalho](https://arxiv.org/pdf/2004.03720.pdf) onde foi investigado se o *Byte Pair Encoding (BPE)*, um algoritmo para tokenização habitualmente utilizado, é a estratégia ótima para o treinamento de modelos de linguagem. Os autores propuseram uma avaliação direta do impacto da tokenização no desempenho desses modelos, o que, segundo eles, é raramente examinado, como observado na literatura. Para verificar isso, LMs foram treinados do zero em experimentos controlados, empregando diferentes técnicas de tokenização, a saber, *Unigram* e *BPE*. Após isso, os modelos pré-treinados foram testados em diversas tarefas. Os resultados mostraram que o desempenho utilizando a estratégia *Unigram* se equiparou e até mesmo foi superior ao BPE.

<!-- Kaj Bostrom and Greg Durrett published a [paper](https://arxiv.org/pdf/2004.03720.pdf) where they aimed to investigate whether the commonly used tokenization algorithm called Byte Pair Encoding (BPE) is the most optimal for pretraining language models (LMs). In other words, they proposed a direct evaluation of the tokenization impact on the performance of LMs. According to the authors, this is rarely ever examined as observed in the literature. To achieve this, they pretrain LMs from scratch using controlled experiments and apply different tokenization, namely unigram and BPE. Thereafter they would test the resulting pretrained LMs on several downstream tasks. Results demonstrate that the unigram tokenization matches or outperforms the more common BPE. -->

\\
***Longformer: The Long-Document Transformer***

\\
Pesquisadores do Allen AI publicaram um novo modelo baseado no Transformer, denominado [Longformer](https://arxiv.org/abs/2004.05150), desenvolvido visando um desempenho mais eficiente em textos longos. Como já é conhecido, uma das limitações de modelos baseados no Transformer é que eles são computacionalmente custosos, devido à maneira como a operação de *self-attention* escala (quadraticamente com o tamanho da sequência), limitando assim a utilização de contextos mais longos. Recentemente, várias alternativas como o [Reformer](https://arxiv.org/abs/2001.04451) e o [Sparse Transformers](https://arxiv.org/abs/1904.10509) foram propostas, visando possibilitar a aplicação dessa classe de modelos para documentos maiores. O Longformer combina modelagem a nível de caractere e *self-attention* (uma mistura do mecanismo de atenção local e global) para requerer menos memória e demonstra sua eficiência na modelagens de textos longos. Os autores também mostraram que o seu modelo pré-treinado supera outros métodos quando aplicados à tarefas a nível de documento, como *question answering* e classificação de texto.  

<!-- Researchers at Allen AI published a new Transformer-based model called [Longformer](https://arxiv.org/abs/2004.05150) that is targeted at performing more efficiently with longer text. It is well known that one of the limitations of Transformer-based models is that they are computationally expensive due to how the self-attention operation scales (quadratically with sequence length) thus limiting the ability to process longer sequences. Recently, there have been many efforts such as the [Reformer](https://arxiv.org/abs/2001.04451) and [Sparse Transformers](https://arxiv.org/abs/1904.10509) to enable the applicability of Transformers for long documents. The Longformer combines character-level modeling and self-attention (mix of local and global attention) to consume less memory and demonstrate effectiveness in long document modeling. Authors also show that their pretrained model outperforms other methods when applied to document-level downstream tasks including QA and text classification. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*uTxVqLtO_nQaDw4OedUUtQ.png)

*Figura extraída de* [*Beltagy et al. (2020)*](https://arxiv.org/abs/2004.05150)

# Criatividade, Ética e Sociedade 🌎

***Reprodutibilidade em ML***

- A questão da reprodutibilidade vem sendo discutida ativamente pelas comunidades de Aprendizado de Máquina. Com o intuito de encorajar uma ciência mais aberta, transparente e acessível, diversos esforços vêm sendo realizados a favor dela. Se você quiser entender como está essa questão no campo de ML, confira essa [publicação](https://arxiv.org/abs/2003.12206) feita por Joelle Pineau, dentre outros.

<!-- - Reproducibility has been an ongoing topic of discussion amongst the machine learning communities. In order to encourage more open, transparent and accessible science, there have been many efforts around reproducibility. If you want to understand where the field of machine learning stands in terms of reproducibility, check out this [publication](https://arxiv.org/abs/2003.12206) by Joelle Pineau and others. -->

- Recentemente, e inspirado por esses esforços, o time do Papers With Code (que agora fazem parte do grupo de IA do Facebook) realizaram uma [postagem](https://medium.com/paperswithcode/ml-code-completeness-checklist-e9127b168501) explicando uma [*checklist* de reprodutibilidade](https://github.com/paperswithcode/releasing-research-code) bem útil, com o objetivo de *"facilitar pesquisas reprodutíveis apresentadas nas principais conferências de ML"* (em tradução livre). A *checklist* avalia os códigos disponibilizados nos seguintes aspectos:

<!-- - More recently, and inspired by these efforts, the Papers With Code team (now part of Facebook AI) published a [blog post](https://medium.com/paperswithcode/ml-code-completeness-checklist-e9127b168501) explaining a useful [reproducibility checklist](https://github.com/paperswithcode/releasing-research-code) to “*facilitate reproducible research presented at major ML conferences*”. The checklist assesses code submission on the following: -->

1. **Dependências**: O repositório apresenta informações sobre as dependências ou instruções sobre como preparar o ambiente de desenvolvimento?

2. **Códigos de treinamento**: O repositório fornece uma maneira de treinar o(s) modelo(s) descritos no artigo?

3. **Códigos de Avaliação**: O repositório fornece um código para calcular o desempenho do(s) modelo(s) treinado(s) ou rodar os experimentos neles?

4. **Modelos pré-treinados**: O repositório fornece acesso gratuito aos parâmetros do modelo pré-treinado?

5. **Resultados**: O repositório fornece uma tabela/gráfico com os principais resultados e o código para reproduzir esses resultados?

![](https://cdn-images-1.medium.com/max/800/1*BQH6F1J3TE1T_GREv5xSew.png)

*Fonte:* [*Papers with Code*](https://medium.com/paperswithcode/ml-code-completeness-checklist-e9127b168501)

- Ainda nessa questão de ciência aberta e reprodutibilidade, aqui está uma postagem interessante, feita por um pesquisador de NLP, [oferecendo uma recompensa](https://twitter.com/srush_nlp/status/1245825437240102913?s=20) pela reprodução de resultados de um artigo que outro pesquisador não conseguiu reproduzir.

<!-- - On the topic of open science and reproducibility, here is an interesting post by an NLP researcher [offering](https://twitter.com/srush_nlp/status/1245825437240102913?s=20) a bounty for replicating results from a paper that another researcher couldn’t replicate. -->

\\
***Privacidade e Segurança em NLP***

\\
Será que um modelo de linguagem pré-treinado pode ser roubado, ou sua exposição para uso via *API* pode trazer implicações de segurança? Em um novo artigo, pesquisadores testaram *APIs* de modelos baseados no BERT para implicações de segurança, no que diz respeito à utilização de consultas para roubo do modelo. Resumidamente, eles observaram que um adversário pode roubar um modelo refinado apenas utilizando sequências de palavras sem sentido e refinando o seu próprio modelo com as predições do modelo-alvo. Leia mais sobre ataques de extração de modelos [aqui](http://www.cleverhans.io/2020/04/06/stealing-bert.html).

<!-- Can a pretrained language model be stolen or does it impose any security implications when exposed for usage via APIs? In a new paper, researchers aim to test BERT-based APIs for security implications particularly regarding the use of queries to steal the model. In summary, they did found that an adversary can steal a fine-tuned model by just feeding gibberish sequences and fine-tuning their own model on the predicted labels of the victim model. Read more about model extraction attacks [here](http://www.cleverhans.io/2020/04/06/stealing-bert.html). -->

\\
![](https://cdn-images-1.medium.com/max/800/1*K9ZD4USdovdyHXomB7csfA.png)

Sistema de extração de modelos aplicado a um modelo-alvo treinado no SQuAD ([Fonte](http://www.cleverhans.io/2020/04/06/stealing-bert.html)).

\\
Outro [artigo interessante](https://arxiv.org/abs/2004.06660), aceito na ACL 2020, investigou se modelos de linguagem pré-treinados são suscetíveis a ataques. Os autores desenvolveram um método de "envenenamento" que é capaz de injetar vulnerabilidades nos parâmetros pré-treinados, tornando os modelos vulneráveis à ameaças. Devido a essas vulnerabilidades, é possível mostrar que esses modelos expõem *backdoors* que podem ser aproveitadas por invasores com o intuito de manipular as predições do modelo, simplesmente injetando qualquer palavra-chave arbitrária. Para testar esse comportamento, modelos pré-treinados foram utilizados em tarefas que envolviam bases de dados "corrompidas" com palavras-chave específicas, feitas para forçar o modelos a classificar exemplos de maneira incorreta.

<!-- Another interesting [paper](https://arxiv.org/abs/2004.06660), accepted at ACL 2020, investigates whether pretrained language models are susceptible to attacks. The authors develop a *poisoning* method that is able to inject vulnerabilities into pretrained weights rendering these pretrained models vulnerable to serious threats. Due to this vulnerability, it is possible to show that these models expose backdoors that can be leveraged by an attacker to manipulate the model’s predictions by simply injecting any arbitrary keyword. To test this, pretrained models were used to perform downstream tasks that involved datasets injected with specific keywords meant to force the model to misclassify instances. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*s4QscGOeDiN6tHOfM99pww.png)

*Figura extraída de* [*Kurita et al. (2020)*](https://arxiv.org/abs/2004.06660)

\\
***Uma série de pesquisas e aplicações baseadas em IA para COVID-19***
<!-- ***A COVID-19 series of AI-based applications and research*** -->

- A COVID-19 provou-se um dos maiores desafios dos tempos modernos. Pesquisadores de todas as partes do mundo tentam encontrar maneiras de contribuir e ajudar a entender a doença, fornecendo desde ferramentas de busca até bases de dados. Sebastian Ruder publicou uma [edição dedicada](http://newsletter.ruder.io/issues/covid-19-edition-236509) da sua *Newsletter* destacando alguns projetos interessantes que pesquisadores de IA vêm desenvolvendo.
<!-- - COVID-19 has proven one of the biggest challenges in modern times. Researchers from all over the world are trying to find ways to contribute and help in understanding COVID-19, from search engines to data set releases. Sebastian Ruder recently published a dedicated [issue](http://newsletter.ruder.io/issues/covid-19-edition-236509) of his newsletter highlighting a few interesting projects that AI researchers have been work on. -->

- Ainda nesse assunto, pesquisadores do Allen AI irão discutir a agora popular base de dados *COVID-19 Open Research Dataset (CORD-19)* num [*meetup* virtual](https://www.meetup.com/NY-NLP/events/269849442) que acontecerá no final desse mês (27/04/2020).
<!-- - On the topic of COVID-19, researchers at Allen AI will discuss the now popular COVID-19 Open Research Dataset (CORD-19) in a [virtual meetup](https://www.meetup.com/NY-NLP/events/269849442) happening towards the end of this month. -->


- A CORD-19 vem sendo utilizada por muitos pesquisadores para a construção de aplicações impulsionadas por NLP, como ferramentas de busca. Confira esse [artigo recente](https://openreview.net/forum?id=PlUA_mgGaPq) para um exemplo de implementação dessas ferramentas que auxiliam pesquisadores a obter *insights* rápidos relacionados à CORD-19 a partir de resultados reportados em artigos de especialistas. De acordo com os autores, tais ferramentas ajudam em tomadas de decisão baseadas em evidências.
<!-- - The CORD-19 dataset is being used by many researchers to build NLP-powered applications such as search engines. Take a look at this recent [paper](https://openreview.net/forum?id=PlUA_mgGaPq) for an example of a search engine implementation that can help researchers obtain quick insights related to CORD-19 from results reported in scholarly articles. Such tools can help inform evidence-based decision making according to the authors. -->

- ArCOV-19 é uma base de dados de *tweets* em árabe sobre COVID-19, que cobre um período de 27 de janeiro até 31 de março de 2020 (e a coleta continua!). É a primeira base dados publicamente disponível do Twitter Árabe cobrindo a pandemia do COVID-19, onde estão inclusos cerca de 748K *tweets* populares (de acordo com o critério de busca do próprio Twitter) junto com as redes de propagação do sub-conjunto mais popular de postagens. As redes incluem tanto *retweets* quando *threads* de respostas.  [ArCOV-19](https://gitlab.com/bigirqu/ArCOV-19) é projetado para permitir a pesquisa em diversas áreas, como NLP, Ciência de Dados, Computadores e Sociedade, entre outras.
<!-- - ArCOV-19 is an Arabic COVID-19 Twitter dataset that covers the period from the 27th of January till the 31st of March 2020 (and still ongoing). It is the first publicly-available Arabic Twitter dataset covering the COVID-19 pandemic that includes around 748k popular tweets (according to Twitter search criterion) alongside the propagation networks of the most-popular subset of them. The propagation networks include both retweets and conversational threads (i.e., threads of replies). [ArCOV-19](https://gitlab.com/bigirqu/ArCOV-19) is designed to enable research under several domains including natural language processing, data science, and social computing, among others. -->

# Ferramentas e Bases de Dados ⚙️

***Machine Learning in Python: Main Developments and Technology Trends in Data Science, Machine Learning, and Artificial Intelligence***

\\
Mesmo não sendo uma ferramenta ou base de dados por si só, esse excelente [artigo](https://www.mdpi.com/2078-2489/11/4/193), com autoria de Sebastian Raschka, Joshua Patterson, e Corey Nolet, fornece uma visão geral compreensiva de alguns dos principais desenvolvimentos em termos de tendências tecnológicas em ML, com foco na linguagem de programação Python.

<!-- Not a tool or dataset per se, but this excellent [paper](https://www.mdpi.com/2078-2489/11/4/193) by Sebastian Raschka, Joshua Patterson, and Corey Nolet provides a comprehensive overview of some of the main developments in terms of technology trends in machine learning, particularly focused on the Python programming language. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*OUpM4KS2uvT7zWlMYqy8RQ.png)

*Figura extraída de* [*Raschka et al. (2020)*](https://www.mdpi.com/2078-2489/11/4/193)

\\
***Interpretabilidade e Explicabilidade em ML***

\\
A Hugging Face disponibilizou uma ferramenta de visualização denominada exBERT, que nos permite visualizar as representações aprendidas por modelos de linguagem como o BERT e RoBERTa. Essa funcionalidade foi integrada à [página de modelos](https://huggingface.co/models?filter=exbert), com o objetivo de prover um melhor entendimento sobre como os modelos de linguagem estão aprendendo, assim como quais propriedades são potencialmente codificadas por eles nessas representações.

<!-- HuggingFace released a visualization tool called exBERT that allows you to visualize learned representations from language models such as BERT and RoBERTa. This feature was integrated into their [model pages](https://huggingface.co/models?filter=exbert) and aims at better understanding how language models are learning and what properties they are potentially encoding in these learned representations. -->

\\
A OpenAI disponibilizou recentemente uma aplicação web chamada [Microscope](https://microscope.openai.com/models) que contém uma coleção de visualizações obtidas de camadas e neurônios de diversos modelos de visão computacional que são comumente estudados no contexto de interpretabilidade. O objetivo principal é facilitar a análise e compartilhamento de *insights* interessantes, obtidos a partir das características aprendidas pelas redes neurais, assim como viabilizar um melhor entendimento dos mesmos.

<!-- OpenAI recently released a web application called [Microscope](https://microscope.openai.com/models) that contains a collection of visualizations obtained from significant layers and neurons of various vision models that are often studied in the context of interpretability. The main objective is to allow ease of analysis and sharing of interesting insights that emerge from these features learned in the neural networks so as to better understand them. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*4VdcqSSyzWDMvVDPEuKzIQ.png)

\\
***CloudCV: ViLBERT Multi-Task Demo***

\\
No edição anterior da [NLP Research Highlights](https://dair.ai/NLP_Research_Highlights_-_Issue_-1/), nós apresentamos o ViLBERT multi-tarefa, que é um método para o aprimoramento de *vision-and-language models* que pode ser utilizado em recuperação de imagens baseada em descrições e *visual question answering (VQA)*. Agora, os autores disponibilizaram uma [aplicação web](https://vilbert.cloudcv.org/) para teste dos modelos em 8 tarefas diferentes de linguagem e visão computacional, como VQA e *pointing question answering*.

<!-- In the previous [NLP Research Highlights](https://dair.ai/NLP_Research_Highlights_-_Issue_-1/), we featured multitask ViLBERT which is a method for improving vision-and-language models that can be used for caption-based image retrieval and visual question answering (VQA). The authors now provide a [web application](https://vilbert.cloudcv.org/) to test the models on eight different vision and language tasks such as VQA and pointing question answering. -->

\\
***A Twitter Dataset of 150+ million tweets related to COVID-19 for open research***

\\
Devido à relevância da pandemia global de COVID-19, pesquisadores estão liberando uma [base de dados](https://zenodo.org/record/3738018) com *tweets* relacionados a doença. Desde a primeira versão disponibilizada, dados adicionais de novos colaborados foram adicionados, permitindo o crescimento da base até seu volume atual. A aquisição dedicada de dados começou em 11 de março, com mais de 4 milhões de *tweets* por dia.

<!-- Due to the relevance of the COVID-19 global pandemic, researchers are releasing a [dataset](https://zenodo.org/record/3738018) of tweets acquired from Twitter related to COVID-19 chatter. Since the first release, additional data from new collaborators has been added, allowing this resource to grow to its current size. Dedicated data gathering started from March 11th yielding over 4 million tweets a day. -->

\\
***A tiny autograd engine***

\\
Andrej Karpathy disponibilizou recentemente uma biblioteca conhecida como [micrograd](https://github.com/karpathy/micrograd), que permite a construção e treinamento de redes neurais utilizando uma interface simples e intuitiva. Na verdade, ele escreveu a biblioteca completa com aproximadamente 150 linhas de código, o que, segundo ele, é a mais compacta ferramenta de diferenciação automática que existe. Idealmente, bibliotecas como essa podem ser utilizadas para fins educacionais.

<!-- Andrej Karpathy recently released a library called [micrograd](https://github.com/karpathy/micrograd) which provides the ability to build and train a neural network using a simple and intuitive interface. In fact, he wrote the whole library in roughly 150 lines of code which he claims is the tiniest autograd engine there is. Ideally, such types of libraries can be used for educational purposes. -->


# Artigos e Postagens ✍️

***The Transformer Family and Recent Developments***

\\
Numa nova e oportuna postagem, Lilian Weng resumiu alguns dos recentes avanços no modelo Transformer. O [artigo](https://lilianweng.github.io/lil-log/2020/04/07/the-transformer-family.html) utiliza uma notação amigável, apresenta uma revisão da literatura bem como as últimas melhorias propostas, como atenção com contextos mais longos (Transformer XL) e redução nos requisitos computacionais e de memória.

<!-- In a new and timely blog post, Lilian Weng summarizes some of the recent developments of the Transformer model. The [article](https://lilianweng.github.io/lil-log/2020/04/07/the-transformer-family.html) provides nice notation, historical review, and the latest improvements such as longer attention span (Transformer XL), reduced computation and memory consumption. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*i-4V-EIirg2cvGMVLd8BWA.png)

\\
A compressão de modelos é uma importante área de pesquisa em NLP, devido à natureza e ao tamanho de modelos de linguagem pré-treinados. Idealmente, conforme os modelos produzem novos resultados estado-da-arte para as mais diferentes tarefas de NLP, torna-se importante reduzir seus requisitos computacionais, tornando sua utilização viável em produção. Madison May publicou recentemente outro excelente [artigo](https://www.pragmatic.ml/a-survey-of-methods-for-model-compression-in-nlp/) trazendo um visão geral de alguns métodos utilizados para compressão de modelos para NLP. Alguns dos tópicos principais incluem poda, otimização dos grafos de computação, destilação de conhecimento, substituição progressiva de módulos, entre outros.

<!-- Model compression is an important area of research in NLP due to the nature and large size of pretrained language models. Ideally, as these models continue to produce state-of-the-art results across a wide variety of NLP tasks it becomes important to reduce their computational needs so as to make them feasible in production. Madison May recently published another excellent [article](https://www.pragmatic.ml/a-survey-of-methods-for-model-compression-in-nlp/) summarizing a few methods used for model compression, particularly in NLP. Some of the main topics include pruning, graph optimizations, knowledge distillation, progressive module replacement, among others. -->

# Educação 🎓

***Guest Lecture on Language Models by Alec Radford***

\\
Se você tem interesse em conhecer os aspectos teóricos dos métodos utilizados para o aprendizado de modelos de linguagem como o CBOW, Word2Vec, ELMo, GPT, BERT, ELECTRA, T5 e GPT, então você deveria conferir essa excelente [aula](https://www.youtube.com/watch?v=BnpB3GrpsfM) do Alec Radford (pesquisador na OpenAI). Ela faz parte de um [curso em andamento](https://sites.google.com/view/berkeley-cs294-158-sp20/home), lecionado pelo Pieter Abbeel, sobre técnicas de aprendizado não-supervisionado com redes neurais profundas.

<!-- If you are curious to know the theoretical aspect of methods used for learning language models such as CBOW, Word2Vec, ELMo, GPT, BERT, ELECTRA, T5, and GPT, then you might be interested in this great [guest lecture](https://www.youtube.com/watch?v=BnpB3GrpsfM) by Alec Radford (researcher at OpenAI). This was delivered as part of the ongoing [course](https://sites.google.com/view/berkeley-cs294-158-sp20/home) taught by Pieter Abbeel on deep unsupervised learning techniques. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*GUxoCXqhozkp_aaRxpT3Sg.png)

\\
***Python Numpy Tutorial (with Jupyter and Colab)***

\\
O popular curso online de Stanford, *Convolutional Neural Network for Visual Recognition*, agora inclui um *link* para um *notebook* do Colab com o seu [guia introdutório](https://cs231n.github.io/python-numpy-tutorial/) ao NumPy, que apresenta um passo a passo extenso mas muito interessante para iniciantes.

<!-- Stanford’s popular online course on Convolutional Neural Network for Visual Recognition now includes a link to a Google Colab notebook for its [introductory guide](https://cs231n.github.io/python-numpy-tutorial/) to Numpy. It’s a very extensive walkthrough but it’s very nice for beginners. -->

\\
***New mobile neural network architectures***

\\
Interessado em construir modelos de redes neurais para dispositivos móveis ou de borda? Então essa [postagem](https://machinethink.net/blog/mobile-architectures/) bem acessível pode te ajudar! O artigo cobre diversas configurações de redes e inclui testes de velocidade.

<!-- Interested in building neural network architectures for mobile and edge devices, then this comprehensive [blog post](https://machinethink.net/blog/mobile-architectures/) may be for you. The article covers a range of neural network designs and includes speed performance tests. -->

\\
***Data-Driven Sentence Simplification: Survey and Benchmark***

\\
A tarefa de *Sentence simplification* (simplificação de frases, numa tradução livre), possui a finalidade de modificar uma frase de modo a torná-la mais fácil de ler e entender. Essa [coletânea](https://www.mitpressjournals.org/doi/full/10.1162/coli_a_00370) foca em abordagens que tentam aprender a simplificar utilizando uma base de pares de sentenças em inglês, contendo as versões originais e simplificadas, que é um paradigma dominante nos dias atuais. Também está incluso um *benchmark* dos diferentes métodos em diversas bases de dados, que os compara e destaca os pontos fortes e fracos de cada um deles.

<!-- Sentence simplification aims to modify a sentence in order to make it easier to read and understand. This [survey paper](https://www.mitpressjournals.org/doi/full/10.1162/coli_a_00370) focuses on approaches that attempt to learn how to simplify using corpora of aligned original-simplified sentence pairs in English, which is the dominant paradigm nowadays. It also includes a benchmark of different approaches on common data sets so as to compare them and highlight their strengths and limitations. -->

\\
***Tópicos Avançados em Aprendizado de Máquina***

\\
Yisong Yue publicou todas as vídeo-aulas do curso [Data-Driven Algorithm Design](https://sites.google.com/view/cs-159-spring-2020/lectures?authuser=0). São cobertos tópicos de ML como otimização Bayesiana, computação diferenciável e *imitation learning*.

<!-- Yisong Yue published all lecture videos for the [Data-Driven Algorithm Design](https://sites.google.com/view/cs-159-spring-2020/lectures?authuser=0) course. It contains advanced topics in machine learning that range from Bayesian optimization to differentiable computation to imitation learning. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*8YFTbEPUw3Bqio70xP0WXQ.png)

# Menções Honrosas ⭐️

Acesse as edições anteriores da NLP Newsletter [aqui](https://github.com/dair-ai/nlp_newsletter) ([última edição em PT-BR]((https://github.com/dair-ai/nlp_newsletter))).

<!-- Get access to the previous issues of the NLP Newsletter [here](https://github.com/dair-ai/nlp_newsletter). -->

\\
Harvard está [oferecendo](https://online-learning.harvard.edu/catalog?keywords=&paid%5B1%5D=1&max_price=&start_date_range%5Bmin%5D%5Bdate%5D=&start_date_range%5Bmax%5D%5Bdate%5D=) uma ótima seleção de cursos *self-paced* de maneira gratuita!
<!-- Harvard is currently [offering](https://online-learning.harvard.edu/catalog?keywords=&paid%5B1%5D=1&max_price=&start_date_range%5Bmin%5D%5Bdate%5D=&start_date_range%5Bmax%5D%5Bdate%5D=) a great selection of self-paced courses for free. -->

\\
[ARBML](https://github.com/zaidalyafeai/ARBML) fornece implementações de diversos projetos de NLP e ML para a língua árabe, incluindo experiências em tempo real utilizando diversas interfaces, como a *web*, linha de comando e *notebooks*.

<!-- [ARBML](https://github.com/zaidalyafeai/ARBML) provides implementations of many Arabic NLP and ML projects providing real-time experience using many interfaces like web, command line and notebooks. -->

\\
[NLP Dashboard](https://nlpdashboard.com) é uma aplicação *web* de NLP interessante, que oferece Reconhecimento de Entidades Nomeadas e análises estatísticas de textos e notícias. Construída utilizando spaCy, Flask e Python.

<!-- [NLP Dashboard](https://nlpdashboard.com) is a fun NLP web app to perform named entity recognition and statistical analysis of text and news stories. Built using spaCy, Flask, and Python. -->

\\
Caso você ainda não conheça, Connor Shorten mantém um [canal no YouTube](https://www.youtube.com/channel/UCHB9VepY6kYvZjj0Bgxnpbw?sub_confirmation=1) bastante informativo, onde ele resume artigos de ML bem recentes e interessantes. São apresentados os detalhes importantes de cada trabalho através de um excelente e conciso resumo. Connor também começou um [*podcast*](https://www.youtube.com/channel/UCMLtBahI5DMrt0NPvDSoIRQ) com outros grandes pesquisadores e educadores da área.

<!-- If you haven’t checked it out, Connor Shorten maintains this really informative [YouTube channel](https://www.youtube.com/channel/UCHB9VepY6kYvZjj0Bgxnpbw?sub_confirmation=1) where he summarizes interesting and recent ML papers. He covers the important details of each work while providing excellent short and concise summaries. He also started a [podcast](https://www.youtube.com/channel/UCMLtBahI5DMrt0NPvDSoIRQ) with other great researchers and explainers in the field. -->

\\
[Aqui](https://github.com/microsoft/nlp-recipes) está um repositório impressionante e bem completo que apresenta as melhoras práticas e recomendações (via *notebooks* e explicações) para diversos cenários de NLP, como classificação de texto, *entailment* (estabelecer relações lógicas, como implicação e contradição, entre textos), sumarização de texto, *question answering*, etc.

<!-- [Here](https://github.com/microsoft/nlp-recipes) is a rich and impressive repository that provides best practices and recommendations (via notebooks and explanations) for many NLP scenarios such as text classification, entailment, text summarization, question answering, etc. -->

----------

Se você conhece bases de dados, projetos, postagens, tutoriais ou artigos que gostaria de ver na próxima edição da *Newsletter*, por favor nos envie utilizando esse [formulário](https://forms.gle/3b7Q2w2bzsXE6uYo9).

\\
[*Inscreva-se*](https://dair.ai/newsletter/) *🔖 para receber as próximas edições na sua caixa de entrada!*
