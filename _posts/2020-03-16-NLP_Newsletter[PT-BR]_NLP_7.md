---
layout: post
title: "NLP Newsletter [PT-BR]: NLP Paper Summaries, Learning to Simulate, Transformers Notebooks, Med7, Measuring Compositional Generalization, Neural Tangents,…"
author: VictorGarritano
excerpt: "Nessa edição, são abordados assuntos como melhorias na avaliação da compositional generalization, bibliotecas de visão computacional baseadas no PyTorch e um simulador físico estado-da-arte."

modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_7.png
---

![](https://cdn-images-1.medium.com/max/1200/1*9gNslKwKiRaffDt2RSOgoQ.png)

\\
Seja muito bem-vindo a sétima edição da NLP Newsletter. Esperamos que você tenha um dia incrível e que você as pessoas que você ama estejam em segurança nessas semanas difíceis. Nós decidimos publicar essa edição na esperança de trazer mais alegria aos nossos leitores. Sendo assim, por favor leia a *Newsletter* durante o seu tempo livre. Nesse momento, é importante mantermos o foco no que é a verdadeira prioridade - nossa família e amigos. ❤️ 💛 💚

<!-- Welcome to the 7th issue of the NLP Newsletter. I hope you are having a wonderful day and that you and your loved ones are safe in these difficult times. We decided to publish this newsletter to bring some joy to our readers so please read when you have free time. For now, let’s keep focused on the things that are of top priority— our families and friends. ❤️ 💛 💚 -->


\\
***Algumas atualizações sobre a NLP Newsletter e a dar.ai***

\\
Todas as traduções em francês e em chinês das edições anteriores estão agora [disponíveis](https://github.com/dair-ai/nlp_newsletter). Descubra como você pode contribuir com a tradução das edições anteriores (assim como as futuras!) da Newsletter nesse [link](https://github.com/dair-ai/dair-ai.github.io/issues/11).

\\
Nota do tradutor**: As traduções de todas as edições da Newsletter, exceto a 3ª, para português também estão disponíveis!

<!-- ***A few updates about the NLP Newsletter and dair.ai***
All French and Chinese translations for the previous issues of the NLP Newsletter are now [available](https://github.com/dair-ai/nlp_newsletter). Find out how you can contribute to the translation of previous and upcoming issues of the NLP Newsletter at this [link](https://github.com/dair-ai/dair-ai.github.io/issues/11). -->

\\
Nós criamos recentemente dois repositórios no Github que contêm [resumos de artigos de NLP](https://github.com/dair-ai/nlp_paper_summaries) e [notebooks utilizando PyTorch](https://github.com/dair-ai/pytorch_notebooks) para que você possa começar a ter experiência com redes neurais.

<!-- We recently created two GitHub repositories that contain [NLP paper summaries](https://github.com/dair-ai/nlp_paper_summaries) and [PyTorch notebooks](https://github.com/dair-ai/pytorch_notebooks) to get you started with neural networks. -->


# Pesquisas e Publicações 📙

***Measuring Compositional Generalization***

\\
No contexto de Aprendizado de Máquina, *compositional generalization* se refere a habilidade de representar o conhecimento aprendido com a base de dados e aplicá-lo a novos e diferentes contextos. Até o presente momento, não estava claro como medir essa composicionalidade nas redes neurais. Recentemente, o time de IA da Google [apresentou](https://ai.googleblog.com/2020/03/measuring-compositional-generalization.html) um dos maiores *benchmarks* para *compositional generalization*, utilizando tarefas como *question answering* e *semantic parsing*. A imagem abaixo apresenta um exemplo do modelo proposto utilizando os chamados *átomos* (unidades utilizadas para se gerar os exemplos) para que sejam produzidos *compostos* (novas combinações dos átomos). A ideia deste trabalho é construir bases de treino e teste que combinam exemplos que possuem a mesma distribuição pelos diferentes *átomos* mas com distribuições diferentes sobre os *compostos*. Os autores argumentam que essa é uma maneira mais confiável de se testar a *compositional generalization*.

<!-- In the context of machine learning, compositional generalization is the ability to learn to represent meaning and in turn sequences (novel combinations) from what’s learned in the training set. To this date, it is not clear how to properly measure compositionality in neural networks. A Google AI team [proposes](https://ai.googleblog.com/2020/03/measuring-compositional-generalization.html) one of the largest benchmarks for compositional generalization using tasks such as question answering and semantic parsing. The picture below shows an example of the proposed model using atoms (produce, direct, etc.) to produce novel compounds, i.e., combinations of atoms. The idea of this work is to produce a train-test split that contains examples that share similar atoms (building blocks to generate examples) distribution but different compound distribution (the composition of atoms). The authors claim that is a more reliable way to test for compositional generalization. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*lXmUWOY8HJL7YVn1.gif)

*Crédito: Google AI Blog*

\\
***Fine-Tuning Pretrained Language Models: Weight Initializations, Data Orders, and Early Stopping***

\\
Pesquisadores testaram uma série de [procedimentos de refinamento](https://arxiv.org/abs/2002.06305) (*fine-tuning*) com o objetivo de compreender melhor o efeito das diferentes estratégias de inicialização de pesos e políticas de *early stopping* no desempenho de modelos de linguagem. Através de exaustivos experimentos de refinamento do BERT, foi constatado que *seeds* aleatórias distintas produzem resultados bastante discrepantes. Em particular, o estudo reporta que certas inicializações de pesos de fato conferem ao modelo um bom desempenho em diversas tarefas. Todas as bases e testes realizados foram disponibilizadas, para uso de outros pesquisadores interessados em entender as dinâmicas que ocorrem durante o *fine-tuning* de maneira mais aprofundada.

<!-- Researchers ran a comprehensive [set of fine-tuning trials](https://arxiv.org/abs/2002.06305) to better understand the effect of weight initialization and early stopping in the performance of language models. Through various experiments that involved fine-tuning BERT hundreds of times, it was found that distinct random seeds produce very different results. In particular, the study reports that some weight initialization does perform well across a set of tasks. All the experimental data and trials were publicly released for other researchers that are interested in further understanding different dynamics during fine-tuning. -->

\\
***Zoom In: An Introduction to Circuits***

\\
Pesquisadores da OpenAI publicaram uma [postagem](https://distill.pub/2020/circuits/zoom-in/) discutindo o estado atual da tarefa de interpretabilidade de redes neurais, assim como uma nova abordagem para a interpretação das mesmas. Inspirada pela biologia celular, os autores buscaram entender modelos de visão computacional e o que eles aprendem de maneira bastante aprofundada, através da inspeção dos pesos do modelo. Basicamente, o estudo apresentou algumas conclusões, obtidas a partir dos experimentos realizados, as quais eles acreditam que possam ser utilizadas como base para uma melhor interpretação das redes neurais.

<!-- OpenAI researchers published a [piece](https://distill.pub/2020/circuits/zoom-in/) discussing the state of interpretability of neural networks and the proposal of a new approach to interpreting them. Inspired by cellular biology, the authors delve deep into understanding vision models and what they learn by inspecting the weights of neural networks. Essentially, the study presented a few claims along with collected evidence that they believe could pave the way to better interpret neural networks. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*i0c-qpiire6dD4IqJVKlYg.png)

\\
***NLP Research Highlights — Issue #1***

\\
Numa nova iniciativa da dar.ai, a [NLP Research Highlights](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040), são fornecidas descrições detalhadas de tópicos atuais e bem importantes da pesquisa em NLP. A ideia é que essa iniciativa seja utilizada para acompanhar os avanços da área através de resumos acessíveis desses trabalhos. Na primeira edição trimestral, os tópicos abordados tratam sobre melhorias em modelos de linguagem e em agentes conversacionais para sistemas de reconhecimento de voz. Os resumos são mantidos [aqui](https://github.com/dair-ai/nlp_paper_summaries).

<!-- In a new dair.ai series called [NLP Research Highlights](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040), we provide detailed descriptions of current interesting and important NLP research. This will serve as a way to keep track of NLP progress via approachable summaries of these works. In the first quarterly issue, topics range from improving language models to improving conversational agents to state-of-the-art speech recognition systems. These summaries will also be maintained [here](https://github.com/dair-ai/nlp_paper_summaries). -->

\\
***Learning to Simulate Complex Physics with Graph Networks***

\\
Nos últimos meses, as *Graph Neural Networks (GNNs)* (redes neurais que operam sobre redes) foram um assunto recorrente nas edições da *Newsletter*, devido a sua efetividade em tarefas não só da área de NLP como também em genômica e materiais. Um [artigo](https://arxiv.org/abs/2002.09405) publicado recentemente, propõe um *framework* geral baseado em *GNNs* que é capaz de realizar simulações físicas em diferentes cenários, como fluidos e materiais maleáveis. Os autores argumentam que eles obtiveram um desempenho estado-da-arte nesses diferentes contextos e que a abordagem proposta é possivelmente o melhor simulador treinado da atualmente. Os experimentos realizados incluem a simulação de materiais como fluidos viscosos sobre a água e outras interações com objetos rígidos. Também foi testado um modelo pré-treinado em tarefas *out-of-distribution* e os resultados obtidos foram bastante promissores, evidenciando o potencial de generalização para outros cenários.

<!-- In the past few months, we have been featuring a lot about Graph Neural Networks (GNNs) due to their effectiveness not only in NLP but in other areas such as genomics and materials. In a recent [paper](https://arxiv.org/abs/2002.09405), researchers propose a general framework based on graph networks that is able to learn simulations in different domains such as fluids and deformable materials. The authors claim that they achieve state-of-the-art performance across different domains and that their general-purpose approach is potentially the best-learned physics simulator to date. Experiments include the simulation of materials such as goop over water and other interactions with rigid obstacles. They also tested a pre-trained model on out-of-distribution tasks and found promising results that show the generalization of the framework to larger domains. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*48EolUDJoHpYRCTZxgn_qg.png)

[*(Sanchez-Gonzalez et al., 2020)*](https://arxiv.org/pdf/2002.09405.pdf)

\\
***Modelos BERT para idiomas específicos***

\\
O BERT Árabe (AraBERT) está agora disponível na biblioteca de *Transformers* da Hugging Face. Você pode acessar o modelo [aqui](https://huggingface.co/aubmindlab/bert-base-arabert) e o artigo [aqui](https://arxiv.org/abs/2003.00104).

\\
Recentemente, uma versão em japonês do BERT também foi [disponibilizada](https://github.com/akirakubo/bert-japanese-aozora). Uma versão em polonês também está disponível, batizada como [Polbert](https://github.com/kldarek/polbert).

<!-- Arabic BERT (AraBERT) is now available in the Hugging Face Transformer library. You can access the model [here](https://huggingface.co/aubmindlab/bert-base-arabert) and the paper [here](https://arxiv.org/abs/2003.00104). Recently, a Japanese version of BERT was also [released](https://github.com/akirakubo/bert-japanese-aozora). And there is also a Polish version of BERT called [Polbert](https://github.com/kldarek/polbert). -->


# Criatividade, Ética e Sociedade 🌎

***Computational predictions of protein structures associated with COVID-19***

\\
A DeepMind publicou suas [predições de estruturas](https://deepmind.com/research/open-source/computational-predictions-of-protein-structures-associated-with-COVID-19) das proteínas que se ligam ao vírus causador da COVID-19. As predições foram obtidas diretamente do sistema AlphaFold, embora não tenham sido verificadas experimentalmente. A ideia é que essa publicações encorajem outras contribuições que busquem entender melhor e vírus e suas funções.

<!-- DeepMind releases [computationally-predicted structures](https://deepmind.com/research/open-source/computational-predictions-of-protein-structures-associated-with-COVID-19) for proteins linked with the virus related to COVID-19. The predictions are directly obtained from the AlphaFold systems but haven’t been experimentally verified. The idea with this release is to encourage contributions that aim to better understand the virus and how it functions. -->

\\
***Court cases that sound like the weirdest fights***

\\
Janelle Shane compartilhou os [resultados](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights) de um divertido experimento onde um modelo do GPT-2 foi refinado para gerar processos judiciais contra objetos inanimados. Foi disponibilizado ao modelo uma lista de processos do governo sobre apreensões de objetivos contrabandeados e artefatos perigosos, e foram geradas acusações como as apresentadas na imagem abaixo.

<!-- Janelle Shane shares the [results](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights) of a fun experiment where a GPT-2 model is fine-tuned to generate cases against inanimate objects. The model was fed a list of cases where the government was seizing contraband or dangerous goods and it generated cases like the ones shown in the picture below. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*E5mHmkm1h4VQJ2Ni.png)

[*fonte*](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights)

\\
***Toward Human-Centered Design for ML Frameworks***

\\
A Google AI [publicou](https://ai.googleblog.com/2020/03/toward-human-centered-design-for-ml.html) os resultados de uma grande pesquisa com 645 pessoas que utilizaram a versão do TensorFlow para JavaScript. O objetivo era entender quais eram as funcionalidades mais importantes da biblioteca para desenvolvedores fora da área de ML, assim como a sua experiência com as atuais bibliotecas de Aprendizado de Máquina. Uma das conclusões obtidas mostra que a falta de entendimento conceitual de ML dificulta a utilização de bibliotecas específicas para esse grupo de usuários. Os participantes do estudo também reportaram a necessidade de instruções mais acessíveis sobre como aplicar modelos de ML em diferentes problemas e um suporte mais explícito para modificações do usuário.

<!-- Google AI [published](https://ai.googleblog.com/2020/03/toward-human-centered-design-for-ml.html) the results of a large-scale survey of 645 people who used TensorFlow.js. They aimed to find out from non-ML software developers what are the most important features and their overall experience with using current ML frameworks. Findings include that the “lack of conceptual understanding of ML” hinders the use of ML frameworks for this particular set of users. Participants in the study also reported the need for better instructions on how to apply the ML models to different problems and more explicit support for modification. -->

\\
***Face and hand tracking in the browser with MediaPipe and TensorFlow.js***

\\
Este excelente [artigo do TensorFlow](https://blog.tensorflow.org/2020/03/face-and-hand-tracking-in-browser-with-mediapipe-and-tensorflowjs.html?linkId=83996111) apresenta um passo-a-passo para habilitar um sistema de *tracking* do rosto e das mãos diretamente no navegador utilizando o TensorFlow.js e o MediaPipe.

<!-- This awesome [TensorFlow article](https://blog.tensorflow.org/2020/03/face-and-hand-tracking-in-browser-with-mediapipe-and-tensorflowjs.html?linkId=83996111) provides a walkthrough of how to enable real-time face and hand tracking on the browser using TensorFlow.js and MediaPipe. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*XsRsB-tSOZo9yWOc.gif)

*Créditos: Blog do TensorFlow*


# Ferramentas e Bases de Dados ⚙️

***NLP Paper Summaries***

\\
Nós criamos recentemente um [repositório]https://github.com/dair-ai/nlp_paper_summaries) contendo uma lista de resumos de artigos de NLP cuidadosamente formulados, para alguns dos mais interessantes e importantes *papers* da área nos últimos anos. O foco principal da iniciativa é expandir a acessibilidade do público-geral à tópicos e pesquisas de NLP.

<!-- We recently created a [repository](https://github.com/dair-ai/nlp_paper_summaries) containing a list of carefully curated NLP paper summaries for some of the most interesting and important NLP papers in the past few years. The focus is to feature paper summaries and blog posts of important papers to help improve the approachability and accessibility of NLP topics and research. -->

\\
***Uma biblioteca de visão computacional diferenciável em PyTorch***

\\
A [Kornia](https://github.com/kornia/kornia) é uma biblioteca construída sobre o PyTorch que permite a utilização de uma série de operadores para visão computacional diferenciável utilizando o PyTorch. Algumas das funcionalidades incluem transformações em images, *depth estimation*, processamento de imagens em baixo-nível, dentre várias outras. O módulo é fortemente inspirado no OpenCV, com a diferença de ser focado em pesquisa, ao invés de aplicações prontas para produção.

<!-- [Kornia](https://github.com/kornia/kornia) is an open-source library built on top of PyTorch that allows researchers to use a set of operators for performing differentiable computer vision using PyTorch. Some capabilities include image transformations, depth estimation, and low-level image processing, to name a few. It is heavily inspired by OpenCV but the difference is that it is meant to be used for research as opposed to building production-ready applications. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*gN_-llcA4_3lIHYE.gif)

\\
***Introducing DIET: state-of-the-art architecture that outperforms fine-tuning BERT and is 6X faster to train***

\\
*DIET (Dual Intent and Entity Transformer)* é uma arquitetura multi-tarefa de *natural language understanding (NLU)* [proposta](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/) pela Rasa. A *framework* foca no treinamento multi-tarefa, com o objetivo de melhorar o desempenho nos problemas de classificação de intenções e reconhecimento de entidades nomeadas. Outros benefícios do DIET incluem a flexibilidade de utilização de qualquer *embedding* pré-treinado, como o BERT e o GloVe. O foco principal, entretanto, é disponibilizar um modelo que ultrapassa o estado-da-arte atual nessas tarefas e que seja mais rápido de treinar (o *speedup* reportado foi de 6x!). O modelo está disponível na biblioteca [rasa](https://rasa.com/docs/rasa/1.8.0/nlu/components/#dietclassifier).

<!-- DIET (Dual Intent and Entity Transformer) is a natural language understanding (NLU) multitask architecture [proposed](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/) by Rasa. The framework focuses on multitask training to improve results on both intent classification and entity recognition. Other benefits of DIET include the ability to use any of the current pre-trained embeddings such as BERT and GloVe. However, the focus was to provide a model that improves the current state-of-the-art performance on those tasks and is faster to train (6X speedup reported). The model is available in the [Rasa Open Source python library](https://rasa.com/docs/rasa/1.8.0/nlu/components/#dietclassifier). -->

\\
![](https://cdn-images-1.medium.com/max/800/0*R_8FOU-CVZabv7hJ.jpg)

[*framework DIET*](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/?utm_source=twitter)

\\
***Perdido no meio dos modelos BERT?***

\\
O [BERT Lang Street](https://bertlang.unibocconi.it/) é uma plataforma que possui a capacidade de buscar por mais de 30 modelos baseados no BERT, em 18 idiomas e 28 tarefas, totalizando 177 entradas em sua base de dados. Dessa forma, se você quiser descobrir o estado-da-arte para a tarefa de classificação de sentimentos utilizando modelos BERT, basta procurar por *"sentiment"* na barra de busca (como exemplificado abaixo).

<!-- [BERT Lang Street](https://bertlang.unibocconi.it/) is a neat website that provides the ability to search over 30 BERT-based models with 18 languages and 28 tasks with a total of 177 entries. For instance, if you wanted to find out the state-of-the-art results for sentiment classification using BERT models, you can just search for “sentiment” in the search bar (example shown in the screenshot below). -->

\\
![](https://cdn-images-1.medium.com/max/800/1*UuVno2eOAzYb_wlSSfukPA.png)

\\
***Med7***

\\
O Andrey Kormilitzin disponibilizou o [Med7](https://github.com/kormilitzin/med7), que é um modelo para NLP (em particular Reconhecimento de Entidades Nomeadas (NER)) em relatórios médicos eletrônicos. O modelo é capaz de identificar até 7 categorias de entidades e está disponível para uso com a biblioteca spaCy.

<!-- Andrey Kormilitzin releases [Med7](https://github.com/kormilitzin/med7) which is a model for performing clinical NLP (in particular named entity recognition (NER) tasks) on electronic health records. The model can identify up to seven categories and is available for use with the spaCy library. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*yOMqhvTwYnxB4LYXv2Mgjg.png)

\\
***Uma biblioteca em código-aberto para Quantum Machine Learning***

\\
[TensorFlow Quantum](https://ai.googleblog.com/2020/03/announcing-tensorflow-quantum-open.html) é uma biblioteca que fornece uma série de funcionalidades para a prototipagem rápida de modelos quânticos de ML, possibilitando a aplicação destes em problemas em áreas como a medicina e materiais.

<!-- [TensorFlow Quantum](https://ai.googleblog.com/2020/03/announcing-tensorflow-quantum-open.html) is an open-source library that provides a toolbox for rapid prototyping of quantum ML research that allows the application of ML models to approach problems ranging from medicine to materials. -->

\\
***Fast and Easy Infinitely Wide Networks with Neural Tangents***

\\
A *Neural Tangents* é uma biblioteca que permite aos pesquisadores construir e treinar modelos de dimensão infinita e redes neurais utilizando a JAX. Leia a postagem de lançamento [aqui](https://ai.googleblog.com/2020/03/fast-and-easy-infinitely-wide-networks.html) e acesse a biblioteca [aqui](https://github.com/google/neural-tangents).

<!-- Neural Tangents is an open-source library that allows researchers to build and train infinite-width models and finite neural networks using JAX. Read the blog post of the release [here](https://ai.googleblog.com/2020/03/fast-and-easy-infinitely-wide-networks.html) and get access to the library [here](https://github.com/google/neural-tangents). -->

\\
![](https://cdn-images-1.medium.com/max/800/1*CojgKJwB_n_7-j0DJZ0y7g.png)

# Artigos e Postagens ✍️

***From PyTorch to JAX: towards neural net frameworks that purify stateful code***

\\
Sabrina J. Mielke publicou um [artigo](https://sjmielke.com/jax-purify.htm) com um passo-a-passo que ilustra a construção e treinamento de redes neurais utilizado o JAX. A postagem busca comparar o funcionamento interno das redes com o PyTorch e o JAX, o que auxilia num melhor entendimento dos benefícios e diferenças entra as duas bibliotecas.

<!-- Sabrina J. Mielke published an [article](https://sjmielke.com/jax-purify.htm) that provides a walkthrough of how to build and train neural networks using JAX. The article focuses on comparing the inner workings of PyTorch and JAX when building neural networks, which helps to better understand some of the benefits and differences of JAX. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*Nrw4UnmnIZ__elHu.png)

[*fonte*](https://sjmielke.com/jax-purify.htm)

\\
***Why do we still use 18-year old BLEU?***

\\
Nesse [*blog post*](https://ehudreiter.com/2020/03/02/why-use-18-year-old-bleu/), Ehud Reiter discorre sobre porquê nós ainda utilizamos técnicas de avaliação antigas como BLUE para mensurar o desempenho de modelos de NLP em tarefas como tradução automática (*machine translation*). Como um pesquisador da área, ele conta sobre as implicações para técnicas que realizam a avaliação em tarefas de NLP mais recentes.

<!-- In this [blog post](https://ehudreiter.com/2020/03/02/why-use-18-year-old-bleu/), Ehud Reiter talks about why we still use old evaluation techniques like BLUE for evaluating NLP models for tasks like machine translation. As a researcher in the space, he also expresses the implications for techniques that perform the evaluation on more recent tasks. -->

\\
***Introducing BART***

\\
O [BART](https://arxiv.org/abs/1910.13461) é um novo modelo proposto pelo Facebook que consiste num *denoising autoencoder* para o pré-treinamento de modelos *sequence-to-sequence*, que pode melhorar o desempenho dos mesmos em tarefas como sumarização abstrata. Sam Shleifer disponibilizou um [resumo interessante](https://sshleifer.github.io/blog_v2/jupyter/2020/03/12/bart.html) do BART e como ele realizou a integração do modelo na biblioteca Transformers da Hugging Face.

<!-- [BART](https://arxiv.org/abs/1910.13461) is a new model proposed by Facebook that involves a denoising autoencoder for pretraining seq2seq models that improve performance on downstream text generation tasks such as abstractive summarization. Sam Shleifer provides a [nice summary](https://sshleifer.github.io/blog_v2/jupyter/2020/03/12/bart.html) of BART and how he integrated it into the Hugging Face Transformers repo. -->

\\
***A Survey of Long-Term Context in Transformers***

\\
Madison May escreveu recentemente um [compilado](https://www.pragmatic.ml/a-survey-of-methods-for-incorporating-long-term-context/) bastante interessante descrevendo estratégias para melhorar abordagens baseadas em Transformers, que incluem *Sparse Transformers*, *Adaptive Span Transformers*, *Transformer-XL*, *compressive Transformers*, *Reformer*, e *routing transformer*. Alguns dos modelos já haviam aparecido em [publicações](https://medium.com/dair-ai) da dar.ai e na lista de [resumos de artigos](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a).

<!-- Madison May recently wrote an interesting [survey](https://www.pragmatic.ml/a-survey-of-methods-for-incorporating-long-term-context/) describing ways to improve Transformer based approaches, which include Sparse Transformers, Adaptive Span Transformers, Transformer-XL, compressive Transformers, Reformer, and routing transformer. We also touched on some of these topics in the dair.ai [publication](https://medium.com/dair-ai) and in this list of [paper summaries](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a). -->

\\
***“Mind your language, GPT-2”: how to control style and content in automatic text writing***

\\
Apesar da fluência impressionante na escrita automática de texto evidenciada no ano passado, continua sendo um desafio controlar atributos como estrutura ou conteúdo em textos gerados por modelos neurais. Numa [postagem recente](https://creatext.ai/blog-posts/controllable-text-generation), Manuel Tonneau discute o progresso atual e as perspectivas na área de geração de texto parametrizável, como o modelo GPT-2 da Hugging Face refinado no arXiv e o T5 da Google, além do CTRL da Salesforce e do PPLM do time de IA da Uber.

<!-- Despite the impressive fluency automatic text writing has exhibited in the past year, it is still challenging to control attributes like structure or content of the machine-written text. In a [recent blog post](https://creatext.ai/blog-posts/controllable-text-generation), Manuel Tonneau discusses the recent progress and the perspectives in the field of controllable text generation, from Hugging Face’s GPT-2 model fine-tuned on arXiv to Google’s T5, with mentions of Salesforce’s CTRL and Uber AI’s PPLM. -->

# Educação 🎓

***Talk: The Future of NLP in Python***

\\
Em uma de nossas edições anteriores, foi apresentado o [THiNC](https://thinc.ai/), uma biblioteca funcional de *Deep Learning* focada na compatibilidade com outras já existentes. Essa [apresentação](https://speakerdeck.com/inesmontani/the-future-of-nlp-in-python-keynote-pycon-colombia-2020?slide=9), utilizada pela Ines Montani na PyCon Colombia, introduz a biblioteca mais profundamente.

<!-- In one of our previous newsletters, we featured [THiNC](https://thinc.ai/) which is a functional deep learning library focused on compatibility with other existing libraries. This [set of slides](https://speakerdeck.com/inesmontani/the-future-of-nlp-in-python-keynote-pycon-colombia-2020?slide=9) introduces a bit more of the library which was used in the talk by Ines Montani for PyCon Colombia. -->

\\
***Transformers Notebooks***

\\
A Hugging Face publicou uma coleção de [notebooks no Colab](https://github.com/huggingface/transformers/tree/master/notebooks) que auxilia no início da utilização de sua biblioteca Transformers. Alguns notebooks incluem o uso de tokenização, configuração de *pipelines* de NLP, e o treinamento de modelos de linguagem em bases de dados próprias.

<!-- HuggingFace published a set of [Colab notebooks](https://github.com/huggingface/transformers/tree/master/notebooks) that help to get started with their popular Transformers library. Some notebooks include using tokenization, setting up NLP pipelines, and training a language model on custom data. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*0AYHYUsHbaqV2vqN2zCzLQ.png)

\\
***TensorFlow 2.0 in 7 hours***

\\
Confira esse [curso grátis de ~7 horas](https://www.freecodecamp.org/news/massive-tensorflow-2-0-free-course/) sobre o TensorFlow 2.0, onde são cobertos tópicos como o básico de redes neurais, NLP com redes neurais recorrentes (RNNs) e uma introdução ao Aprendizado por Reforço.

<!-- Check out this [~7-hour free course](https://www.freecodecamp.org/news/massive-tensorflow-2-0-free-course/) on TensorFlow 2.0 containing topics that range from basic neural networks to NLP with RNNs to an introduction to reinforcement learning. -->

\\
***DeepMind: The Podcast***

\\
A DeepMind liberou todos os episódios (numa [playlist no YouTube](https://www.youtube.com/playlist?list=PLqYmG7hTraZBiUr6_Qf8YTS2Oqy3OGZEj)) do seu *podcast* com cientistas, pesquisadores e engenheiros, onde são discutidos tópicos como *Artificial General Intelligence, neurociência e robótica.

\\
***Cursos de Machine Learning and Deep Learning***

\\
A Berkeley está disponibilizando publicamente o [plano de estudos](https://sites.google.com/view/berkeley-cs294-158-sp20/home) do seu curso em "*Deep Unsupervised Learning*", focado principalmente nos aspectos teóricos do *self-supervised learning* e em modelos generativos. Outros tópicos incluem modelos de variáveis latentes, modelos autorregressivos e *flow models*. As aulas e os *slides* também estão disponíveis.

<!-- Berkeley is publicly releasing the [entire syllabus](https://sites.google.com/view/berkeley-cs294-158-sp20/home) for its course on “Deep Unsupervised Learning” mainly focusing on the theoretical aspects of self-supervised learning and generative models. Some topics include latent variable models, autoregressive models, flow models, and self-supervised learning, to name a few. Youtube videos and slides are available. -->

\\
Nós também encontramos essa [lista impressionante](https://www.reddit.com/r/MachineLearning/comments/fdw0ax/d_advanced_courses_update/) de cursos avançados de ML, NLP e *Deep Learning* disponível de maneira online.

<!-- We also found this [impressive list](https://www.reddit.com/r/MachineLearning/comments/fdw0ax/d_advanced_courses_update/) of advanced online courses on machine learning, NLP and deep learning. -->

\\
E aqui está um outro curso intitulado [“Introduction to Machine Learning"](https://compstat-lmu.github.io/lecture_i2ml/index.html) que aborda assuntos como regressão supervisionada, avaliação de desempenho, *random forests*, ajuste de parâmetros, dicas práticas e muito mais.

<!-- And here is another course called [“Introduction to Machine Learning](https://compstat-lmu.github.io/lecture_i2ml/index.html)” which includes topics such as supervised regression, performance evaluation, random forests, parameter tuning, practical advice, and much more. -->


# Menções Honrosas ⭐️

A edição anterior da Newsletter (6ª edição) está disponível [aqui](https://dair.ai/NLP_Newsletter-PT-BR-_BERTology_Primer_fastpages_T5/).

<!-- The previous NLP Newsletter (Issue #6) is available [here](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040). -->

\\
Connon Shorten publicou um [vídeo](https://www.youtube.com/watch?v=QWu7j1nb_jI&feature=emb_logo) explicando o modelo ELECTRA, que propõe a utilização de uma técnica chamada *replaced token detection* como forma de pré-treinar Transformers de maneira mais eficiente. Se você tiver interesse em saber mais, nós também escrevemos um breve resumo do modelo [aqui](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a).

<!-- Connon Shorten published a [video](https://www.youtube.com/watch?v=QWu7j1nb_jI&feature=emb_logo) explaining the ELECTRA model which proposes a technique called replaced token detection to pre-train Transformers more efficiently. If you are interested, we also wrote a short summary of the model [here](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a). -->

\\
Rachael Tatman está trabalhando numa nova série denominada [NLP for Developers](https://www.youtube.com/watch?v=-G36q8_cYsc&feature=emb_logo) onde o objetivo é discutir diferentes métodos de NLP de maneira mais aprofundada, quando utilizá-los e como lidar com dificuldades comuns apresentadas por essas técnicas.

<!-- Rachael Tatman is working on a new series called [NLP for Developers](https://www.youtube.com/watch?v=-G36q8_cYsc&feature=emb_logo) where the idea is to talk more in-depth about different NLP methods, when to use them and explaining common issues that you may run into. -->

\\
A DeepMind liberou o [AlphaGo — The Movie](https://youtu.be/WXuK6gekU1Y) no YouTube para celebrar o 4º aniversário da vitória do modelo sobre o Lee Sedol no jogo de Go.

<!-- DeepMind releases [AlphaGo — The Movie](https://youtu.be/WXuK6gekU1Y) on YouTube to celebrate the 4th anniversary of AlphaGo beating Lee Sedol at the game of Go. -->

\\
A OpenMined está com [vagas abertas](https://blog.openmined.org/introducing-openmined-research/) para os cargos de *Research Engineer e Research Scientist*, que parecem ser boas oportunidades para se envolver com *privacy-preserving AI*.

<!-- OpenMined has [open positions](https://blog.openmined.org/introducing-openmined-research/) for Research Engineer and Research Scientist roles which is a good opportunity to get involved with privacy-preserving AI. -->

----------

Se você conhecer bases de dados, projetos, postagens, tutoriais ou artigos que você gostaria de ver na próxima edição da *Newsletter*, sinta-se a vontade para nos contactar através do e-mail ellfae@gmail.com ou de uma [mensagem direta no twitter](https://twitter.com/omarsar0).

<!-- If you have any datasets, projects, blog posts, tutorials, or papers that you wish to share in the next iteration of the NLP Newsletter, please free to reach out to me at ellfae@gmail.com or ****[**DM on Twitter**](https://twitter.com/omarsar0). -->

\\
[*Inscreva-se*](https://dair.ai/newsletter/) *🔖 para receber as próximas edições na sua caixa de entrada!*
