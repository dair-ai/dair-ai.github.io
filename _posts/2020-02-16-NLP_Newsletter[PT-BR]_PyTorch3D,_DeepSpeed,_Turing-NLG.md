---
layout: post
title: "NLP Newsletter [PT-BR]: PyTorch3D, DeepSpeed, Turing-NLG, Question Answering Benchmarks, Hydra, Sparse Neural Networks,…"
author: VictorGarritano
modified:
comments: true
excerpt: "Essa edição cobre tópicos como modelos de linguagem maiores, avanços na pesquisa de Deep Learning em 3D, benchmarks para question answering multi-idiomas, auditoria de sistemas de IA e muito mais"
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_4.png
---

![](https://cdn-images-1.medium.com/max/1200/1*3vNKhz6K-oGQ8aLi3mo84Q.png)

# Publicações 📙

***Turing-NLG: A 17-billion-parameter language model by Microsoft***

\\
O Turing Natural Language Generation (T-NLG) é um modelo de linguagem com 17 bilhões de parâmetros [proposto](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/) pelo grupo de pesquisa em Inteligência Artificial da Microsoft. O T-NLG é composto por 78 camadas, baseado na arquitetura dos Transformers, que superou o estado da arte anterior (atribuido ao [Megatron-LM](https://github.com/NVIDIA/Megatron-LM) da Nvidia) considerando a Perplexidade na base de dados WikiText-103. O modelo foi testado em diversas tarefas, como *question answering* e sumarização abstrata, onde foram observados comportamentos interessantes e desejáveis para modelos dessa categoria, como *"zero shot" question answering* (onde o modelo responde a um pergunta sem estar ciente do contexto explicitamente), e baixa necessidade de bases previamente anotadas, para as tarefas citadas anteriormente. O modelo pode ser treinado graças à biblioteca DeepSpeed, utilizando o esquema de otimização ZeRO (que também aparece nessa edição da *Newsletter*).

<!-- Turing Natural Language Generation (T-NLG) is a 17-billion-parameter language model [proposed](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/) by Microsoft AI researchers. Besides being the largest known language model to date (depicted in the figure below), T-NLG is a 78-layers Transformer-based language model that outperforms the previous state-of-the-art results (held by NVIDIA’s [Megatron-LM](https://github.com/NVIDIA/Megatron-LM)) on WikiText-103 perplexity. It was tested on a variety of tasks such as question answering and abstractive summarization while demonstrating desirable benefits such as zero short question capabilities and minimizing supervision, respectively. The model is made possible by a training optimization library called DeepSpeed with ZeRO, which is also featured later in this newsletter. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*CAZm7uj8EaupnvnJ.png)


*Modelos de Linguagem e suas quantidades de parâmetros —* [*fonte*](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/)

\\
***Neural based Dependency Parsing***

\\
A pesquisadora Miryam de Lhoneux liberou recentemente sua tese de Doutorado, entitulada “[Linguistically Informed Neural Dependency Parsing for Typologically Diverse Languages](http://uu.diva-portal.org/smash/record.jsf?pid=diva2%3A1357373&dswid=7905)”. O trabalho desenvolvido propõe a utilização de abordagens baseadas em redes neurais para a tarefa de análise de dependências ([dependency parsing](http://nlpprogress.com/english/dependency_parsing.html)) em idiomas com diversas tipologias (línguas que apresentam padrões funcionais e estruturais diferentes). O trabalho apresentado pela autora indica que a incorporação de RNNs e camadas recursivas nos analisadores pode ser benéfica para a tarefa, uma vez que essas arquiteturas podem indicar o conhecimento linguístico necessário à análise. Outras extensões incluem a utilização de analisadores poliglotas e estratégias de compartilhamento de parâmetros para a análise de linguagens correlacionadas ou descorrelacionadas.

<!-- Miryam de Lhoneux released her Ph.D. thesis titled “[Linguistically Informed Neural Dependency Parsing for Typologically Diverse Languages](http://uu.diva-portal.org/smash/record.jsf?pid=diva2%3A1357373&dswid=7905)”. This work is about using neural approaches for [dependency parsing](http://nlpprogress.com/english/dependency_parsing.html) in typologically diverse languages (i.e. languages that construct and express meaning in structurally different ways). This paper reports that RNNs and recursive layers could be beneficial for incorporating into parsers as they help to inform models with important linguistic knowledge needed for parsing. Other ideas include the use of polyglot parsing and parameter sharing strategies for parsing in related and unrelated languages. -->

\\
***End-to-end Cloud-based Information Extraction with BERT***

\\
Um time de pesquisadores publicou um [artigo](https://arxiv.org/abs/2002.01861) descrevendo como modelos de Transformers, como o BERT, podem auxiliar sistemas de extração de informação de ponta a ponta em documentos de domínios específicos, como documentação regulatória e de concessão de propriedades. Esse tipo de trabalho, além de otimizar operações de negócios, demonstra a eficiência e aplicabilidade de modelos baseados no BERT em cenários onde bases de dados anotadas são extremamente limitadas. Uma plataforma na nuvem é apresentada e discutida, assim como os detalhes de sua implementação (ver figura abaixo).

<!-- A team of researchers published a [paper](https://arxiv.org/abs/2002.01861) describing how Transformer models like BERT can help for end-to-end information extraction in domain-specific business documents such as regulatory filings and property lease agreements. Not only can this type of work help to optimize business operations but it also shows the applicability and effectiveness of BERT-based models on regimes with very low annotated data. An application, and its implementation details, that operates on the cloud is also proposed and discussed (see figure below). -->

\\
![](https://cdn-images-1.medium.com/max/800/1*KqViSLhP0otleDY-XFy3Bg.png)


[*fonte*](https://arxiv.org/abs/2002.01861)

\\
***Question Answering Benchmark***

\\
Em [Wolfson et al. (2020)](https://arxiv.org/abs/2001.11770v1), apresenta-se um *benchmark* para a tarefa de *question understanding* e um método para decomposição de questões, uma etapa necessária para a determinação de uma resposta apropriada. Os autores recorreram à um serviço de *crowdsourcing* para a criação da base anotada de decomposição de questões. Com objetivo de demonstar a viabilidade e aplicabilidade do método proposto, os autores mostraram que é possível melhorar o desempenho de modelos utilizando essa técnica sobre a base de dados HotPotQA.

<!-- [Wolfson et al. (2020)](https://arxiv.org/abs/2001.11770v1) published a question understanding benchmark and a method for breaking down a question that is necessary for computing an appropriate answer. They leverage crowdsourcing to annotate the required steps needed to break down questions. To show the feasibility and applicability of the approach, they improve on open-domain question answering using the HotPotQA dataset. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*AztG-Inqt6LGQ87lSufRcw.png)


*“Questões de diferentes fontes de informações exibem uma estrutura composicional semelhante. Questões em linguagem natural (parte de cima) são decompostas seguindo a metodologia QDMR (meio) e deterministicamente mapeadas para uma linguagem pseudo-formal (parte de baixo).” —* [*fonte*](https://arxiv.org/pdf/2001.11770v1.pdf)
<!-- Questions over different sources share a similar compositional structure. Natural language questions from multiple sources (top) are annotated with the QDMR formalism (middle) and deterministically mapped into a pseudo-formal language (parte inferior). -->

\\
***Radioactive data: tracing through training***

\\
Membros da equipe de pesquisa em IA do Facebook publicaram recentemente um [trabalho interessante](https://ai.facebook.com/blog/using-radioactive-data-to-detect-if-a-data-set-was-used-for-training/) que propõe a marcação de imagens (referenciadas como *radioactivate data*) de tal maneira que seja possível verificar se uma determinada base de dados foi utilizada no treinamento de um modelo de Aprendizado de Máquina. Os autores concluíram que é possível utilizar uma marcação mais robusta, que move as *features* para uma determinada direção, e que pode ser empregada para auxiliar a detecção de dados "radioativos", mesmo quando apenas **1%** destes estão presentes na base de treinamento.

Essa é uma tarefa bem desafiadora, uma vez que qualquer modificação nos dados pode potencialmente prejudicar o desempenho do modelo. De acordo com os autores, o trabalho proposto pode "*ajudar pesquisadores e engenheiros a monitorar quais bases de dados foram utilizadas no treinamento de um modelo, com o objetivo de compreender melhor como bases de dados de diferentes naturezas influenciam o desempenho de diversas redes neurais*". Parece uma tarefa crucial para aplicações *mission-critical*. Confira o artigo completo [aqui](https://arxiv.org/pdf/2002.00937.pdf).

<!-- Facebook AI researchers recently published [an interesting work](https://ai.facebook.com/blog/using-radioactive-data-to-detect-if-a-data-set-was-used-for-training/) that aims to mark images (referred to as radioactive data) so as to verify if that particular data set was used for training the ML model. They found that it is possible to use a clever marker that moves features towards a direction, which the model uses to help detect the usage of radioactive data even when only 1 percent of the training data is radioactive. This is challenging since any change in the data can potentially degrade the model accuracy. According to the authors, this work can “*help researchers and engineers to keep track of which data set was used to train a model so they can better understand how various data sets affect the performance of different neural networks*”. It seems like an important approach in mission-critical ML applications. Check out the full paper [here](https://arxiv.org/pdf/2002.00937.pdf). -->

\\
***REALM: Retrieval-Augmented Language Model Pre-Training***

\\
O [REALM](https://kentonl.com/pub/gltpc.2020.pdf) é um método de recuperação em larga escala baseado em redes neurais, que faz uso de bases de conhecimento textual para pré-treinar um modelo de linguagem de maneira não-supervisionada. Essencialmente, o objetivo da abordagem é capturar o conhecimento,  de uma maneira mais interpretável, expondo o modelo à conhecimentos gerais utilizados durante o processo de treinamento e inferência através do *backpropagation*. As bases onde o método foi testado e avaliado incluem *benchmarks* de *open-domain question answering*. Além do aumento observado na acurácia do modelo, outros benefícios incluem modularidade e interpretabilidade dos componentes.

<!-- [REALM](https://kentonl.com/pub/gltpc.2020.pdf) is a large-scale neural-based retrieval approach that makes use of a corpus of textual knowledge to pre-train a language model in an unsupervised manner. This approach essentially aims to capture knowledge in a more interpretable way by exposing the model to world knowledge that is used for training and predictions via backpropagation. Tasks approached and evaluated using REALM include open-domain question answering benchmarks. Besides the improvements in the accuracy of the model, other benefits include the modularity and interpretability components. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*MJO-yzCwsB5ydKGz7hKHVA.png)


[*fonte*](https://kentonl.com/pub/gltpc.2020.pdf)

# Criatividade e Sociedade 🎨


***Apresentações remotas de artigos e pôsteres em conferências científicas***

\\
Durante a semana passada, uma [petição](https://www.change.org/p/organizers-of-data-science-and-machine-learning-conferences-neurips-icml-aistats-iclr-uai-allow-remote-paper-poster-presentations-at-conferences) circulou na internet, reivindicando a permissão para apresentações remotas de artigos e pôsteres em conferências científicas, como as relacionadas à Aprendizado de Máquina. Para saber mais, acesse [change.org](https://www.change.org/p/organizers-of-data-science-and-machine-learning-conferences-neurips-icml-aistats-iclr-uai-allow-remote-paper-poster-presentations-at-conferences). Parece que Yoshua Bengio, um dos pioneiros do *Deep Learning*, está convocando as pessoas à assinar a petição. Ele deixou isso bem claro em seu novo [blog](https://yoshuabengio.org/2020/02/10/fusce-risus/).

<!-- The past week there was the circulation of a [petition](https://www.change.org/p/organizers-of-data-science-and-machine-learning-conferences-neurips-icml-aistats-iclr-uai-allow-remote-paper-poster-presentations-at-conferences) to allow for remote paper and poster presentations at scientific conferences like ML related ones. Go read more about it on [change.org](https://www.change.org/p/organizers-of-data-science-and-machine-learning-conferences-neurips-icml-aistats-iclr-uai-allow-remote-paper-poster-presentations-at-conferences). It seems Yoshua Bengio, a pioneer in deep learning, is advocating for people to go and sign the petition. He made this clear in his new [blog](https://yoshuabengio.org/2020/02/10/fusce-risus/). -->

\\
***Abstração e Desafios de Raciocínio***

\\
François Chollet postou recentemente uma [competição no Kaggle](https://www.kaggle.com/c/abstraction-and-reasoning-challenge/overview) onde ele disponibilizou o *Abstraction and Reasoning Corpus (ARC)*, uma base de dados que tem como objetivo encorajar os usuários a desenvolver sistemas de IA para resolver tarefas às quais nunca foram expostos. A esperança é que essa competição seja o pontapé inicial para  a construção de modelos mais robustos de IA, capazes de resolver novos problemas por conta própria de maneira mais eficiente e rápida, ajudando na resolução de aplicações mais desafiadoras do mundo real como a melhoria de carros autônomos que operam em ambientes diversos e extremos.

<!-- François Chollet has recently posted a [Kaggle competition](https://www.kaggle.com/c/abstraction-and-reasoning-challenge/overview) where he released the Abstraction and Reasoning Corpus (ARC) that aims to encourage users to create AI systems that can solve reasoning tasks it has never been exposed to. The hope is to begin to build more robust AI systems that are able to better and quickly solve new problems on its own which could help to address the more challenging real-world applications such as improving self-driving cars that operate in extreme and diverse environments. -->

\\
***Publicações de Aprendizado de Máquina e Processamento de Linguagem Natural em 2019***

\\
Marek Rei liberou sua [análise anual](https://www.marekrei.com/blog/ml-and-nlp-publications-in-2019/) com estatísticas das publicações sobre ML e NLP em 2019. As conferências consideradas nas análises foram ACL, EMNLP, NAACL, EACL, COLING, TACL, CL, CoNLL, NeurIPS, ICML, ICLR, e AAAI.

\\
***Growing Neural Cellular Automata***

\\
Morfogênese é um processo de auto-organização pelo qual alguns animais, como as salamandras, podem regenerar partes de seus corpos que sofreram danos. O processo é robusto a perturbações e adaptativo na natureza. Inspirado nesse esse fenômeno biológico e com a necessidade de uma melhor compreensão desse mecanismo, pesquisadores publicaram um [trabalho](https://distill.pub/2020/growing-ca/) entitulado “*Growing Neural Cellular Automata*”, que adota um modelo diferenciável para o processo de morfogênese buscando replicar os comportamentos e propriedades de sistemas de auto-reparação.

Espera-se que o processo seja capaz de criar máquinas "auto-reparáveis" que possuam a mesma robustez e maleabilidade dos organismos biológicos. Além disso, o método pode possibilitar um melhor entendimento do processo de regeneração em si. Áreas que podem se beneficiar com essa pesquisa incluem a medicina regenerativa e a modelagem de sistemas sociais e biológicos.


<!-- Morphogenesis is a self-organization process by which some creatures such as salamanders can regenerate or repair body damage. The process is robust to perturbations and adaptive in nature. Inspired by this biological phenomenon and a need to understand the process better, researchers published a [paper](https://distill.pub/2020/growing-ca/) titled “Growing Neural Cellular Automata”, which adopts a differentiable model for morphogenesis that aims to replicate behaviors and properties of self-repairing systems. The hope is to be able to build self-repairing machines that possess the same robustness and plasticity as biological life. In addition, it would help to better understand the process of regeneration itself. Applications that can benefit include regenerative medicine and modeling of social and biological systems. -->
\\
![](https://cdn-images-1.medium.com/max/800/1*2p62h1RaHD6d11LX8olnTA.png)


[*fonte*](https://distill.pub/2020/growing-ca/)

\\
***Visualização do mecanismo de Atenção do Transformer***

\\
Hendrik Strobelt compartilhou esse [repositório bem interessante](https://github.com/SIDN-IAP/attnvis) que mostra como construir rapidamente uma  visualização simples e interativa da Atenção do Transformer através de uma aplicação web utilizando as bibliotecas Hugging Face e d3.js.

\\
![](https://cdn-images-1.medium.com/max/800/1*lMaZGDRJUI1Qcv7T5AdhlQ.gif)


[*fonte*](https://github.com/SIDN-IAP/attnvis)

\\
***SketchTransfer: A Challenging New Task for Exploring Detail-Invariance and the Abstractions Learned by Deep Networks***

<!-- SketchTransfer proposes a new task to test the ability of deep neural networks to support invariance in the presence/absence of details. It has long been debated that deep networks cannot generalize to variations that have not yet been seen during training, something humans can do with relative ease such as dealing with the missing visual details when watching cartoons. The paper discusses and releases a dataset to help researchers carefully study the “detail-invariance” problem by providing unlabelled sketch images and labeled examples of real images. -->

\\
O SketchTransfer propõe uma nova tarefa que tem por objetivo testar a habilidade de redes neurais profundas em manter a capacidade invariância frente a presença/ausência de detalhes. Um debate de longa data existe acerca da inabilidade de redes profundas em generalizar variações que não foram vistas durante o treinamento, algo que os humanos conseguem fazer com relativa facilidade em situações como, por exemplo, a falta de alguns detalhes visuais quando assistimos desenhos. O trabalho discute e disponibiliza uma base de dados esboços não-anotados e imagens reais anotadas, permitindo que os pesquisadores possam estudar o problema de "*detail-invariance*" de maneira bastante cuidadosa.

\\
![](https://cdn-images-1.medium.com/max/800/1*jdYuMoHiu2yya5rHzZyjwQ.png)


[*fonte*](https://arxiv.org/pdf/1912.11570.pdf)


# Bibliotecas e Bases de Dados ⚙️

***DeepSpeed + ZeRO***

\\
A Microsoft liberou um pacote para otimização chamado DeepSpeed, compatível com o PyTorch, que possibilita o treinamento de modelos com 100 bilhões de parâmetros. A biblioteca dá destaque a 4 importantes aspectos do processo de treinamento: *operação em escala*, *velocidade*, *custo*, e *usabilidade*. A DeepSeed foi [liberada](https://www.microsoft.com/en-us/research/blog/zero-deepspeed-new-system-optimizations-enable-training-models-with-over-100-billion-parameters/) junto com o ZeRO, uma tecnologia que otimiza a utilização da memória, e que possibilita o emprego do Deep Learning em larga escala de maneira distribuída com as atuais tecnologias de GPU, além de melhorar o *throughput* em 3-5 vezes em relação à melhor solução atual. A tecnologia possibilita o treinamento de modelos de tamanho arbitrário que podem ocupar a memória total disponível, distribuída pelos diversos dispositivos na infra-estrutura.

<!-- Microsoft open sources a training optimization library called DeepSpeed, which is compatible with PyTorch and can enable the ability to train a 100-billion-parameter model. The library focuses on four important aspects of training a model: *scale*, *speed*, *cost*, and *usability*. DeepSpeed was [released](https://www.microsoft.com/en-us/research/blog/zero-deepspeed-new-system-optimizations-enable-training-models-with-over-100-billion-parameters/) together with ZeRO which is a memory optimization technology for enabling large-scale distributed deep learning in current GPU technology while improving throughput three to five times more than the best current system. ZeRO allows the training of models with any arbitrary size that can fit in the aggregated available memory in terms of shared model states. -->
\\
![](https://cdn-images-1.medium.com/max/800/0*MXDI1f3cSBrY5w2g.gif)


[*fonte*](https://www.microsoft.com/en-us/research/blog/zero-deepspeed-new-system-optimizations-enable-training-models-with-over-100-billion-parameters/)

<!-- ***A library for conducting fast and efficient 3D deep learning research*** -->

\\
***Deep Learning em Superfícies 3D de Maneira Rápida e Eficiente***

<!-- [PyTorch3D](https://ai.facebook.com/blog/-introducing-pytorch3d-an-open-source-library-for-3d-deep-learning/) is an open-source toolkit for 3D based deep learning research. This PyTorch library aims to help with the support and understanding of 3D data in deep learning systems. The library consists of fast and optimized implementations of frequently used 3D operators and loss functions. It also comes with a modular differentiable renderer which helps to conduct research on complex 3D inputs and supports high-quality 3D predictions. -->
\\
A [PyTorch3D](https://ai.facebook.com/blog/-introducing-pytorch3d-an-open-source-library-for-3d-deep-learning/) é uma biblioteca em código aberto para a pesquisa de Deep Learning aplicado à superfícies 3D. Esse pacote, baseado no PyTorch, busca auxiliar no suporte e entendimento de dados em 3D aplicados à redes neurais. A biblioteca consiste de implementações eficientes e otimizadas de operadores e funções de custo 3D comumente utilizadas. Um renderizador diferenciável modular também está disponível, que pode ser útil durante a pesquisa e exploração de entradas 3D com padrões complexos e na geração de predições de alta qualidade.

\\
![](https://cdn-images-1.medium.com/max/800/1*VbspKMmPBUsgpdnIkd5jYA.png)


[*fonte*](https://ai.facebook.com/blog/-introducing-pytorch3d-an-open-source-library-for-3d-deep-learning/)

<!-- ***Managing Configuration of ML projects*** -->

\\
***Gerenciamento de Configurações para projetos de ML***

\\
Hydra é uma ferramenta de configuração escrita em Python, que auxilia no gerenciamento de projetos complexos de ML de maneira mais eficiente. O propósito é dar suporte a pesquisadores que utilizam o PyTorch, oferencedo a possibilidade de reutilização de configurações de projetos de maneira funcional. O benefício principal oferecido é a possibilidade do programador *compor configurações como compõe-se código*, o que permite a rápida alteração de arquivos de configuração. A Hydra pode ainda gerenciar automaticamente o diretório de trabalho que armazena as saídas do seu projeto de ML, o que é bem útil quando precisamos salvar e acessar diversos resultados provenientes de múltiplos *jobs*. Para saber, mais visite o [site](https://hydra.cc/).

<!-- Hydra is a Python-based configuration tool for more efficiently managing complex ML projects. It is meant to help PyTorch researchers by offering functional reuse of configurations for ML projects. The main benefit it offers is that it allows the programmer to *compose the configuration like composing code*, which means the configuration file can be easily overridden. Hydra can also help with automatically managing the working directory of your ML project outputs which is useful when needing to save and accessing the results of several experiments for multiple jobs. Learn more about it [here](https://medium.com/pytorch/hydra-a-fresh-look-at-configuration-for-machine-learning-projects-50583186b710%27). -->

<!-- ***A Toolkit for Causal Inferencing with Bayesian Networks*** -->

\\
***Uma biblioteca para Inferência Causal com Redes Bayesianas***


<!-- [CausalNex](https://causalnex.readthedocs.io/en/latest/01_introduction/01_introduction.html) is a toolkit for “causal inference with Bayesian Networks”. The tool aims to combine machine learning and causal reasoning for uncovering structural relationships in data. The authors also prepared an introductory guide on why and how to infer causation with Bayesian networks using the proposed Python library. -->

\\
A [CausalNex](https://causalnex.readthedocs.io/en/latest/01_introduction/01_introduction.html) é uma ferramenta que busca combinar o aprendizado de máquina e o raciocínio causal, possibilitando a descoberta de relacionamentos estruturais na base de dados. Os autores prepararam um tutorial introdutório que mostra porquê e como inferir causalidade com as Redes Bayesianas utilizando a biblioteca proposta.

\\
![](https://cdn-images-1.medium.com/max/800/1*EYwKhdnscR7ZLuNkTqCS2Q.png)


[*fonte*](https://causalnex.readthedocs.io/en/latest/01_introduction/01_introduction.html)

\\
***Google Colab Pro agora está disponível***

\\
O Google Colab comecou a oferecer uma versão Pro, que disponibiliza vantagens como o acesso exclusivo à GPUs e TPUs, tempos de execução mais longos e mais memória.

<!-- Google Colab is now offering a Pro edition, which offers advantages such as exclusive access to faster GPUs and TPUs, longer runtimes, and more memory. -->

\\
***TyDi QA: A Multilingual Question Answering Benchmark***

\\
O grupo de IA da Google introduziu recentemente a [TyDi QA](https://ai.googleblog.com/2020/02/tydi-qa-multilingual-question-answering.html), uma base de dados multi-idiomas que busca encorajar pesquisadores a abordar a tarefa de *question answering* em línguas mais tipologicamente diversas, ou seja, que apresentam padrões estrturais não-convencionais. A liberação da base visa motivar a construção de modelos mais robustos a idiomas tipologicamente distantes, como o Árabe, Bengali, Coreano, Russo, Telugo e Tailândes, podendo generalizar para outros dialetos.

<!-- Google AI releases [TyDi QA](https://ai.googleblog.com/2020/02/tydi-qa-multilingual-question-answering.html) which is a multilingual dataset that can encourage researchers to perform question answering on more typologically diverse languages that construct and express meaning in different ways. The idea is to motivate researchers to build more robust models on typologically distant languages, such as Arabic, Bengali, Korean, Russian, Telugu, and Thai, so as to generalize to even more languages. -->
\\
![](https://cdn-images-1.medium.com/max/800/1*1dZv5you3jigdrQ2uAKzUw.png)


[*fonte*](https://ai.googleblog.com/2020/02/tydi-qa-multilingual-question-answering.html)

\\
***Question Answering para Node.js***

\\
A empresa Hugging Face liberou uma [biblioteca para *question answering*](https://github.com/huggingface/node-question-answering) baseada no DistilBERT, dando continuidade a sua missão de tornar a área de Processamento de Linguagem Natural mais acessível. O modelo apresentado pode rodar num ambiente de produção utilizando Node.js com apenas 3 linhas de código, se benficiando da implementação eficiente oferecida pela Tokenizers, também desenvolvida pelo Hugging Face, e a versão em Javascript do TensorFlow (TensorFlow.js).

<!-- Hugging Face releases a [question answering library](https://github.com/huggingface/node-question-answering) based on DistilBERT and continues to make NLP more accessible. This model can run in production using Node.js with just 3 lines of code. The model leverages the fast implementation of Tokenizers, also built by Hugging Face, and TensorFlow.js (a popular library for using machine learning models with Javascript). -->


# Ética em IA 🚨

***Identificando viés subjetivo em texto***

\\
Num [podcast](https://podcasts.apple.com/us/podcast/will-ai-help-identify-bias-or-perpetuate-it-with-diyi-yang/id1435564422?i=1000464141922) que contou com a participação de Diyi Yang, um pesquisador em ciência social computacional, foi discutido como sistemas de IA podem auxiliar na identificação de viés subjetivo em informações textuais. Essa é uma área de pesquisa importante envolvendo Inteligência Artificial e NLP, especialmente quando discutimos sobre o consumo de textos, como títulos e chamadas de notícias, e a facilidade que esses meios possuem para influenciar leitores com opiniões subjetivas.

Do ponto de vista da aplicação, se torna de vital importância a tarefa de identificação desse viés de maneira automática, assim como a conscientização dos leitores, para que esses se tornem mais atentos e criteriosos em relação ao conteúdo que estão consumindo.

<!-- This [podcast episode](https://podcasts.apple.com/us/podcast/will-ai-help-identify-bias-or-perpetuate-it-with-diyi-yang/id1435564422?i=1000464141922) features Diyi Yang, a researcher in computational social science, who talks about how AI systems can help to identify subjective bias in textual information. This is an important area of research involving AI systems and NLP especially when we discuss the consumption of text media such as news headlines that can be easily framed to bias consumers when in reality they should aim to be more objective. From an application perspective, it becomes critical to automatically identify the subjective bias present in text media so as to help consumers become more aware of the content they are consuming. The episode also discusses how AI can also perpetuate bias. -->

\\
***Artificial Intelligence, Values and Alignment***

\\
A disseminação de sistemas de IA e a forma com que esses sistemas se alinham com os valores humanos é uma área de pesquisa envolvendo ética na Inteligência Artificial em crescente atividade. A DeepMind publicou recentemente um [artigo](https://deepmind.com/research/publications/Artificial-Intelligence-Values-and-Alignment) que busca investigar de maneira mais profunda as questões filosóficas envolvidas no alinhamento da IA com os valores humanos. O trabalho discute duas frentes: a técnica (*como codificar valores que permitem que agentes de IA produzam resultados confiáveis*), e a normativa (*quais princípios deveriam ser codificados pelos modelos*), e como eles se relacionam e podem ser garantidos. O artigo encoraja uma abordagem baseada em princípios para o alinhamento de valores pelos sistemas de Inteligência, de modo a preservar um tratamento igualitário e justo frente às diferenças de convicções e opiniões.

<!-- The rise of AI systems and how they align human values is an active area of research that involves ethics in AI systems. DeepMind recently released a [paper](https://deepmind.com/research/publications/Artificial-Intelligence-Values-and-Alignment) that takes a deeper look at the philosophical questions surrounding AI alignment. The report focuses on discussing two parts, technical (i.e., *how to encode values that render reliable results from AI agents*) and normative (*what principles would be right to encode in AI*), and how they relate and can be ensured. The paper pushes for a principle-based approach for AI alignment and to preserve fair treatment despite the difference in beliefs and opinions. -->

\\
***Auditoria em Sistemas de IA***

\\
A VentureBeat divulgou que pesquisadores da Google, numa colaboração com outros grupos, criaram um *framework* chamado SMACTR, que permite a auditoria de sistemas de IA. A motivação para esse trabalho envolve a ausência de "prestação de contas" dos sistemas atuais, que são colocados à disposição do público geral. A reportagem completa pode ser acessada [aqui](https://venturebeat.com/2020/01/30/google-researchers-release-audit-framework-to-close-ai-accountability-gap/), assim como o [trabalho completo](https://dl.acm.org/doi/abs/10.1145/3351095.3372873).


<!-- A VentureBeat reports that Google Researchers, in collaboration with other groups, created a framework called SMACTR that allows engineers to audit AI systems. The reason for this work is to address the accountability gap that exists with current AI systems that are put in the wild to be used by consumers. Read the full report [here](https://venturebeat.com/2020/01/30/google-researchers-release-audit-framework-to-close-ai-accountability-gap/) and the full paper [here](https://dl.acm.org/doi/abs/10.1145/3351095.3372873). -->


# Artigos e Postagens ✍️

***Destilação de modelos em sistemas de NLP***

\\
Num [novo episódio](https://soundcloud.com/nlp-highlights/104-model-distillation-with-victor-sanh-and-thomas-wolf) do podcast *NLP Highlights*, Thomas Wolf and Victor Sanh discutiram sobre a destilação de modelos e como a técnica pode ser utilizada como uma alternativa factível para a compressão de grandes arquiteturas, como o BERT, para aplicações escaláveis de NLP em cenários reais. A metodologia é discutida no trabalho publicado pelos convidados, entitulado [DistilBERT](https://arxiv.org/abs/1910.01108), onde são construídos modelos menores (baseados na mesma arquitetura do modelo original) que tentam simluar o comportamento do modelo com maior número de parâmetros, de acordo com suas saídas. Essencialmente, o menor modelo (*student*) tenta modelar a distribuição de probabilidade do modelo maior (*teacher*) baseado na distribuição empírica gerado por suas saídas.

\\
***BERT, ELMo, & GPT-2: How contextual are contextualized word representations?***

\\
O sucesso de métodos contextualizados como o BERT para resolução de uma ampla gama de tarefas complexas de NLP é um assunto que está em voga no momento. Nesse [post](https://kawine.github.io/blog/nlp/2020/02/03/contextual.html), Kawin Ethayarajh tenta responder a questão que diz respeito à quão contextuais os modelos como BERT, o ELMo e o GPT-2 e seus respectivos *word embedddings* contextualizados são. As características exploradas incluem métricas de contextualidade, especificidade de contexto, além de comparações entre representações vetoriais de palavras "estáticas" e suas versões contextualizadas.

<!-- Recently there has been a lot of talk on the success of contextualized methods like BERT for approaching a wide variety of complex NLP tasks. In this [post](https://kawine.github.io/blog/nlp/2020/02/03/contextual.html), Kawin Ethayarajh attempts to answer the question of how contextual models like BERT, ELMo and GPT-2 and their contextualized word representation are? Topics include measures of contextuality, context-specificity, and comparisons between static embeddings and contextualized representations. -->
\\
![](https://cdn-images-1.medium.com/max/800/0*70aIv1Fkkz4rnHgQ.png)


[*fonte*](https://kawine.github.io/blog/nlp/2020/02/03/contextual.html)

\\
***Esparsidade em Redes Neurais***

\\
François Lagunas, pesquisador na área de ML, escreveu esse excelente [post](https://medium.com/huggingface/is-the-future-of-neural-networks-sparse-an-introduction-1-n-d03923ecbd70) compartilhando seu otimismo em relação à utilização de tensores esparsos em modelos de redes neurais. A expectativa é empregar alguma forma de esparsidade visando a redução do tamanho dos modelos atuais, que de certa forma estão se tornando impraticáveis, dadas suas colossais quantidades de parâmetros. Os Transformers, por exemplo, com seus bilhões de parâmetros, poderiam se beneficar com o emprego dessa técnica.

Entretanto, os detalhes de implementação para viabilizar a utilização eficiente da esparsidade em GPU ainda não estão claros... Felizmente, a comunidade de Aprendizado de Máquina já está trabalhando nisso!

<!-- François Lagunas, an ML researcher, wrote this great [blog post](https://medium.com/huggingface/is-the-future-of-neural-networks-sparse-an-introduction-1-n-d03923ecbd70) discussing his optimism for adopting sparse tensors in neural network models. The hope is to employ some form of sparsity to reduce the size of current models that at some point become unpractical due to their size and speed. This concept may be worth exploring in ML due to the sheer size of current models like Transformers (often relying on billions of parameters). However, the implementation details to support efficient sparsity in neural networks on GPUs are not so clear from a developer tool perspective and that is something the machine learning community is working on already. -->

\\
***Treinando Seu Próprio Modelo de Linguagem***

\\
Se você está interessado em aprender como treinar um modelo de linguagem do zero, confira esse excelente [tutorial](https://huggingface.co/blog/how-to-train) da Hugging Face que utiliza as suas incríveis bibliotecas Tokenizers e Transformers no treinamento do modelo.
<!--
If you are interested to learn how to train a language model scratch, check out this impressive and comprehensive [tutorial](https://huggingface.co/blog/how-to-train) by Hugging Face. They obviously leverage their own libraries Transformers and Tokenizers to train the model. -->

\\
***Tokenizers: How machines read***

\\
Cathal Horan publicou um [blog post](https://blog.floydhub.com/tokenization-nlp/) impresssionante e bem detalhado sobre como e quais tipos de *tokenizers* vêm sendo utilizados nos mais recentes modelos de NLP, auxiliando modelos de Inteligência a aprender por meio de informações textuais. O post também discute e motiva porquê a tarefa de tokenização é uma importante e desafiadora área de pesquisa ativa. O artigo apresenta ainda como treinar o seu próprio *tokenizer* utilizando métodos como o SentencePiece e o WordPiece.

<!-- Cathal Horan published an impressive and very detailed [blog post](https://blog.floydhub.com/tokenization-nlp/) about how and what type of tokenizers are being used by the most recent NLP models to help machine learning algorithms learn from textual information. He also discusses and motivated why tokenization is an exciting and important active area of research. The article even shows you how to train your own tokenizers using tokenization methods like SentencePiece and WordPiece. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*Vkjw5n9Sz0Was43haVNJMg.png)


[*fonte*](https://blog.floydhub.com/tokenization-nlp/%27)


# Educação 🎓

***Machine Learning na VU Amsterdam***

\\
Agora você pode acompanahar o curso [2020 MLVU machine learning](https://mlvu.github.io/) pela internet, onde estão inclusas a lista completa de slides, [videos](https://www.youtube.com/watch?v=excCZSTJEPs&feature=youtu.be) e o plano de estudos. O curso oferece uma introdução à ML, além de cobrir tópicos mais avançados de Deep Learning, como *Variational AutoEncoders* (VAEs) e Redes Neurais Adversariais (GANs).

<!-- You can now follow the [2020 MLVU machine learning](https://mlvu.github.io/) course online, which includes the full set of slides, [videos](https://www.youtube.com/watch?v=excCZSTJEPs&feature=youtu.be), and syllabus. It is meant to be an introduction to ML but it also has other deep learning related topics such as VAEs and GANs. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*zFpU2rQL5Fby7X3boJyQNg.png)


[*fonte*](https://mlvu.github.io/)

\\
***Materiais de Matemática para ML***

\\
Suzana Ilić e a organização Machine Learning Tokyo (MLT) vêm realizando um excelente trabalho em prol da democratização do conhecimento em ML. Confira esse [repositório](https://github.com/Machine-Learning-Tokyo/Math_resources) que apresenta uma coleção de fontes e materiais sobre os fundamentos matemáticos utilizados em Aprendizado de Máquina.


<!-- Suzana Ilić and the Machine Learning Tokyo (MLT) have been doing amazing work in terms of democratizing ML education. For example, check out this [repository](https://github.com/Machine-Learning-Tokyo/Math_resources) showcasing a collection of free online resources for learning about the foundations of mathematical concepts used in ML. -->

\\
***Introduction to Deep Learning***

\\
Acompanhe o curso “[Introduction to Deep Learning](http://introtodeeplearning.com/)” do MIT nesse site. Novas aulas serão postadas toda semanas e todos os materiais, como slides, vídeos e códigos utilizados, serão publicados.


<!-- Keep track of the “[Introduction to Deep Learning](http://introtodeeplearning.com/)” course by MIT on this website. New lectures will be posted every week and all the sides and videos, including coding labs, will be published. -->

\\
***Deep Learning com PyTorch***

\\
Alfredo Canziani publicou os slides e notebooks utilizados no minicurso de Deep Learning com Pytorch. O repositório contém ainda um [site](https://atcold.github.io/pytorch-Deep-Learning/) que incluem notas sobre os conceitos apresentados no curso.

<!-- Alfredo Canziani has published the slides and notebooks for the minicourse on Deep Learning with PyTorch. The repository also contains a [companion website](https://atcold.github.io/pytorch-Deep-Learning-Minicourse/) that includes text descriptions of the concepts taught in the course. -->

\\
***Missing Semester of Your CS***

\\
O “[Missing Semester of Your CS](https://missing.csail.mit.edu/)” é um excelente curso online composto por recursos que podem ser potencialmente úteis para cientistas de dados que não possuem background na área de desenvolvimenteo. Estão inclusos materiais sobre *shell scripting* e versionamento. O curso foi disponibilizado por alunos do MIT.
\\
![](https://cdn-images-1.medium.com/max/800/1*weUnTXxmHxYf-B2DDaslvw.png)


[*fonte*](https://missing.csail.mit.edu/2020/shell-tools/)

\\
***Advanced Deep Learning***

\\
A CMU disponibilizou recentemente os slides e plano de estudos para o curso “[Advanced Deep Learning](https://andrejristeski.github.io/10707-S20/syllabus.html)”, que cobre tópicos como modelos autoregressivos, modelos generativos, aprendizado autosupervisionado, entre outros. O público-alvo são alunos de mestrado e doutorado com sólidos conhecimentos de ML.

<!-- A CMU released the slides and syllabus for the “[Advanced Deep Learning](https://andrejristeski.github.io/10707-S20/syllabus.html)” course which includes topics such as autoregressive models, generative models, and self-supervised/predictive learning, among others. The course is meant for MS or Ph.D. students with an advanced background in ML. -->


# Menções honrosas ⭐️

\\
Você pode encontrar a última Newsletter [aqui](https://medium.com/dair-ai/nlp-newsletter-flax-thinc-language-specific-bert-models-meena-flyte-lasertagger-4f7da04a9060). Essa edição cobriu tópicos como melhorias em agentes conversacionais, divulgação de modelos BERT para idiomas específicos (entre eles o **Português**!!!), bases de dados publicamente disponívies, introdução de novas bibliotecas para Deep Learning, e muito mais.

<!-- You can catch the previous NLP Newsletter here. The [issue](https://medium.com/dair-ai/nlp-newsletter-flax-thinc-language-specific-bert-models-meena-flyte-lasertagger-4f7da04a9060) covers topics such as improving conversational agents, releases of language-specific BERT models, free datasets, releases of deep learning libraries, and much more. -->

Em Xu et al. (2020), foi proposto um [método](https://arxiv.org/abs/2002.02925]) para progressivamente substituir e comprimir modelos BERT através da separação de seus componentes originais. Através dessa substituição progressiva, aliado ao processo de treinamento, é possível combinar os componentes originais e suas versões compactadas. A metodologia apresentada supera outras abordagens de *knowledge distillation* no benchmark GLUE.

<!-- Xu et al. (2020) proposed a [method](https://arxiv.org/abs/2002.02925]) for progressively replacing and compressing a BERT model by dividing it into its original components. Through progressive replacement and training, there is also the advantage of combining the original components and compacted versions of the model. The proposed model outperforms other knowledge distillation approaches on the GLUE benchmark. -->

Um outro curso interessante é o “[Introduction to Machine Learning](https://compstat-lmu.github.io/lecture_i2ml/index.html)”, que cobre o básico de ML, regressão supervisionada, *random forests*, ajuste de parâmetros, dentre outros conceitos fundamentais.

<!-- Here is another interesting course called “[Introduction to Machine Learning](https://compstat-lmu.github.io/lecture_i2ml/index.html)” which covers the ML basics, supervised regression, random forests, parameter tuning, and many more fundamental ML topics. -->

A versão para 🇬🇷 grego do BERT ([GreekBERT](https://huggingface.co/nlpaueb/bert-base-greek-uncased-v1)) está disponível para uso através da biblioteca Transformers, da Hugging Face.

Jeremy Howard publicou um [artigo](https://arxiv.org/abs/2002.04688) descrevendo a biblioteca de Deep Learning fast.ai, que é amplamente utilizada para pesquisa e ensino em seus cursos de Deep Learning. Uma leitura bastante recomendada para desenvolvedores de software que trabalham construindo e melhorando pacotes de Aprendizado de Máquina e Deep Learning.
<!--
Jeremy Howard publishes a [paper](https://arxiv.org/abs/2002.04688) describing the fastai deep learning library which is widely used for research and to teach their open courses on deep learning. A recommended read for software developers working on building and improving deep learning and ML libraries. -->

A Deeplearning.ai completou o lançamento dos seus 4 cursos da série [TensorFlow: Data and Deployment Specialization](https://www.coursera.org/specializations/tensorflow-data-and-deployment). A especialização visa ensinar desenvolverdores a como realizar o *deploy* de modelos de maneira efetiva e eficiente nos mais diferentes cenários, além de utilizar dados de maneiras eficazes durante o treinamento de modelos.

<!-- Deeplearning.ai completes the release of all four courses of the [TensorFlow: Data and Deployment Specialization](https://www.coursera.org/specializations/tensorflow-data-and-deployment). The specialization mainly aims to educate developers on how to efficiently and effectively deploy models in different scenarios and make use of data in interesting and effective ways while training models. -->

Sebastian Raschka publicou recentemente um [artigo](https://arxiv.org/abs/2002.04803) entitulado “Machine Learning in Python: Main developments and technology trends in data science, machine learning, and artificial intelligence”. O trabalho apresenta uma revisão bastante acessível às mais variadas ferramentas de ML. É um artigo excelente para compreender as vantagens de algumas bibliotecas e conceitos utilizados em Aprendizado de Máquina. Além disso, levanta-se a discussão sobre o futuro de bibliotecas de ML baseadas em Python.


<!-- Sebastian Raschka recently published a [paper](https://arxiv.org/abs/2002.04803) titled “Machine Learning in Python: Main developments and technology trends in data science, machine learning, and artificial intelligence”. The paper serves as a comprehensive review of the machine learning tools landscape. It is an excellent report for understanding the various advantages of some libraries and concepts used in ML engineering. In addition, a word on the future of Python-based machine learning libraries is provided. -->