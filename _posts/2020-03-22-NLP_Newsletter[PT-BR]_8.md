---
layout: post
title: "NLP Newsletter #8 [PT-BR]: NeRF, CORD-19, Stanza, Text Generation 101, Notebooks, SECNLP, Dreamer,…"
author: VictorGarritano
excerpt: "Essa edição cobre tópicos como produção de novas perspectivas em cenários complexos, tutoriais para geração de textos, e coletâneas de artigos sobre embeddings contextualizados e modelos de linguagem pré-treinados."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_8.png
---


![](https://cdn-images-1.medium.com/max/1200/1*SptuncVzQw49OZFlDVaQdw.png)

# Atualizações da dair.ai

- Nós melhoramos a categorização de todos os *TL;DR*'s e resumos já incluídos no [repositório](https://github.com/dair-ai/nlp_paper_summaries) do *NLP Paper Summaries*.
- Todos os *issues* e traduções da *Newsletter* passaram a ser mantidos [aqui](https://github.com/dair-ai/nlp_newsletter).
- Também foram introduzidos nessas semanas os [Notebooks](https://github.com/dair-ai/notebooks), focando no compartilhamento de *notebooks* de Ciência de Dados com a comunidade. Se você tem algum que gostaria de compartilhar, entre em contato conosco!
- Nós disponibilizamos um [tutorial](https://colab.research.google.com/drive/1YuL0iqxaz09qR0_2Fgyi2wQHgil_Seqg) que demonstra como realizar uma classificação de emoções utilizando a *TextVectorization* — uma funcionalidade experimental do TensorFlow 2.1 que auxilia no tratamento de texto em redes neurais.
<!-- - We have added better categorization for all TL;DR and summaries included in the NLP paper summaries [repo](https://github.com/dair-ai/nlp_paper_summaries). -->
<!-- - All issues and translations of the NLP Newsletter are being maintained [here](https://github.com/dair-ai/nlp_newsletter). -->
<!-- - This week we also introduced [Notebooks,](https://github.com/dair-ai/notebooks) a hub for easily sharing data science notebooks with the community at large. If you have any notebooks that you would love to share with the community get in touch. -->
<!-- - We shared a [tutorial](https://colab.research.google.com/drive/1YuL0iqxaz09qR0_2Fgyi2wQHgil_Seqg) that provides steps on how to perform multiclass emotion classification using TextVectorization — an experimental feature in TensorFlow 2.1.0 that helps to manage text in a neural network. -->

# Pesquisas e Publicações 📙

***Surveys on Contextual Embeddings***

\\
Esse [artigo](https://arxiv.org/abs/2003.07278v1) fornece um compilado de metodologias para o aprendizado de *embeddings* contextualizados. Também estão inclusos uma revisão dos casos de uso da técnica para *transfer learning*, métodos de compressão de modelos e análises.

Outro [trabalho](https://arankomatsuzaki.files.wordpress.com/2020/03/written_report.pdf) traz uma coleção de métodos utilizados para a melhoria de modelos de linguagem baseados no *Transformer*.

E aqui está outra [coletânea](https://arxiv.org/pdf/2003.08271.pdf) de modelos de linguagem pré-treinados, que propõe uma taxonomia para modelos dessa natureza em NLP.

<!-- This [paper](https://arxiv.org/abs/2003.07278v1) provides a light survey of approaches for learning contextual embeddings. It also includes a review of its applications for transfer learning, model compression methods, and model analyses. Another report involves a [summary](https://arankomatsuzaki.files.wordpress.com/2020/03/written_report.pdf) of methods used to improve Transformer based language models. Here is also another [comprehensive survey](https://arxiv.org/pdf/2003.08271.pdf) on pretrained language models which provides a taxonomy of NLP pretrained models. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*1jLfdem3xZ0I3EVSyOy48g.png)

[*Qiu et al., 2020*](https://arxiv.org/pdf/2003.08271.pdf)

\\
***Visualizing Neural Networks with the Grand Tour***

\\
O *Grand Tour* é um método linear (em contraste com outras técnicas não-lineares, como o t-SNE) que realiza a projeção de bases de dados de dimensão alta para duas dimensões. Neste novo [artigo](https://distill.pub/2020/grand-tour/) do Distill, Li et al. (2020) propõem a utilização das habilidades do *Grand Tour* para visualizar o comportamento de uma rede neural durante o processo de treinamento. Comportamentos de interesse nas análises incluem as mudanças de pesos e como essas afetam o processo de treinamento, comunicação entre camadas do modelo e o efeito de exemplos adversariais ao serem apresentados para a rede neural.

<!-- The Grand Tour is a linear approach (differs from the non-linear methods such as t-SNE) that projects a high-dimensional dataset to two dimensions. In a new Distill [article](https://distill.pub/2020/grand-tour/), Li et al. (2020) propose to use the Grand Tour capabilities to visualize the behavior of a neural network as it trains. Behaviors of interest in the analysis include weight changes and how it affects the training process, layer-to-layer communication in the neural network, the effect of adversarial examples when they are presented to the neural network. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*XYCRZOzslb-ZRYlmtHV0Ng.png)

*Fonte:* [*Distill*](https://distill.pub/2020/grand-tour/)

\\
***Meta-Learning Initializations for Low-Resource Drug Discovery***

\\
Diversos trabalhos demonstram como o *meta-learning* pode viabilizar a adoção de técnicas de *Deep Learning* para melhorar *benchmarks* de *few-shot learning*. Essa ideia é particularmente útil quando nos deparamos com situações onde a quantidade de dados disponíveis é limitada, como no caso do desenvolvimento de novos medicamentos. Um [artigo recente](https://arxiv.org/abs/2003.05996) aplicou uma técnica de *meta-learning* denominada *Model-Agnostic-Meta-Learning (MAML)*, e suas variantes, para predizer propriedades químicas em cenários de escassez de dados. Os resultados obtidos demonstraram que a abordagem utilizada tem um desempenho similar a outros métodos multi-tarefa pré-treinados.

<!-- It has been widely reported that meta-learning can enable the application of deep learning to improve on few-shot learning benchmarks. This is particularly useful when you have situations where there is limited data as is typically the case in drug discovery. A recent [work](https://arxiv.org/abs/2003.05996) applied a meta-learning approach called Model-Agnostic-Meta-Learning (MAML) and other variants to predict chemical properties and activities in low-resource settings. Results show that the meta-learning approaches perform comparably to multi-task pre-training baselines. -->

\\
***NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis***

\\
Um trabalho bastante interessante envolvendo pesquisadores da UC Berkeley, Google Research e da UC San Diego desenvolveu um método ([NeRF](http://www.matthewtancik.com/nerf)) para a criação de novas perspectivas em cenários complexos. Tomando um conjunto de imagens RGB como base de dados, o modelo utiliza coordenadas 5D (espaço, localização e direção) para o treinamento de uma rede neural profunda totalmente conectada, otimizando uma *continuous volumetric scene function*, e retornando a densidade de volume e radiância para aquela localização. Os diversos valores de saída são combinados ao longo de um *camera ray* e renderizados como *pixels*. Essas saídas renderizadas são utilizadas para otimizar representações de cenas através da minimização do erro de renderização para todos os *camera rays* das imagens RGB. Comparada com outras abordagens para a tarefa, a NeRF é quantitativa e qualitativamente melhor, além de conseguir resolver algumas inconsistências das outras abordagens, como a ausência de pequenos detalhes e *flickering* indesejado. 

<!-- An exciting work involving researchers from UC Berkeley, Google Research, and UC San Diego present a method ([NeRF](http://www.matthewtancik.com/nerf)) for synthesizing novel views of complex scenes. Using a collection of RGB image inputs, the model takes 5D coordinates (spatial location and direction), train a fully-connected DNN to optimize *a continuous volumetric scene function*, and outputs the volume density and view-dependent emitted RGB radiance for that location. The output values are composed together along a camera ray and rendered as pixels. These rendered differentiable outputs are used to optimize the scene representations *by minimizing the error of renderings all camera rays* from RGB images. Compared to other top-performing approaches for view synthesis, NeRF is qualitatively and quantitatively better and addresses inconsistencies in rendering such as lack of fine details and unwanted flickering artifacts. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*E6RQL5jdtHXR98BJJREDYg.png)

\\
***Introducing Dreamer: Scalable Reinforcement Learning Using World Models***

\\
O [Dreamer](https://ai.googleblog.com/2020/03/introducing-dreamer-scalable.html) é um agente de Aprendizado por Reforço que busca resolver algumas limitações (como imediatismo e ineficiência computacional) observados em agentes baseados em modelos para resolver tarefas com alto nível de dificuldade. Esse agente, proposto por pesquisadores da DeepMind e da Google AI, é treinado para modelar o mundo no qual está inserido e desenvolver a habilidade de aprender comportamentos focados no longo prazo utilizando o *backpropagation*. Resultados estado-da-arte foram obtidos em 20 tarefas de controle, baseadas nas imagens de entrada fornecidas. Além disso, o modelo é eficiente e pode operar de forma paralela, tornando-o mais interessante do ponto de vista computacional. As três tarefas envolvidas no treinamento do agente, com objetivos distintos, são sintetizadas na Figura abaixo.

<!-- [Dreamer](https://ai.googleblog.com/2020/03/introducing-dreamer-scalable.html) is a reinforcement learning (RL) agent proposed to address some limitations (e.g. shortsightedness and computational inefficiency) present in model-free and model-based agents for solving difficult tasks. This RL agent, proposed by DeepMind and Google AI researchers, is trained to model the world that also provides the ability to learn long-sighted behaviors via backpropagation using the model predictions. SoTA results are achieved on 20 continuous control tasks based on the provided image inputs. In addition, the model is data-efficient and makes predictions in parallel, making it more computationally efficient. The three tasks involved in training the agent that achieve the different goals are summarized in the figure below: -->

\\
![](https://cdn-images-1.medium.com/max/800/1*DOlPDgvNu1kpTeogcLve-A.png)

*Fonte:* [*Google AI Blog*](https://ai.googleblog.com/2020/03/introducing-dreamer-scalable.html)

# Criatividade, Ética e Sociedade 🌎

***COVID-19 Open Research Dataset (CORD-19)***

\\
Num esforço para encorajar a utilização da IA na luta contra a COVID-19, o *Allen Institute of AI* publicou o [COVID-19 Open Research Dataset (CORD-19)](https://pages.semanticscholar.org/coronavirus-research), um recurso publicamente disponível que busca promover colaboração global. A base de dados contêm milhares de artigos que permitem a obtenção de *insights*, através do emprego de técnicas de NLP, que podem ajudar na luta contra o coronavírus e a [doença](https://www.who.int/emergencies/diseases/novel-coronavirus-2019) causada por ele.

<!-- In an effort to encourage the use of AI to fight COVID-19, the Allen Institute of AI published the [COVID-19 Open Research Dataset (CORD-19)](https://pages.semanticscholar.org/coronavirus-research), a free and open resource to promote global research collaboration. The dataset contains thousands of scholarly articles that can allow NLP inspired research to obtain insights that can help in the fight against [COVID-19](https://www.who.int/emergencies/diseases/novel-coronavirus-2019). -->

\\
***SECNLP: A survey of embeddings in clinical natural language processing***

\\
O [SECNLP](https://www.sciencedirect.com/science/article/pii/S1532046419302436) é um *survey* que inclui uma revisão detalhada de uma ampla gama de técnicas de NLP aplicadas no contexto de saúde. O trabalho foca principalmente em métodos de *embedding*, problemas/desafios que essas representações buscam resolver, e uma discussão sobre possíveis direções de pesquisas.

<!-- [SECNLP](https://www.sciencedirect.com/science/article/pii/S1532046419302436) is a survey paper that includes a detailed overview of a wide variety of NLP methods and techniques applied in the clinical domain. The overview emphasizes mostly on embedding methods, problems/challenges addressed with embeddings, and discussion of future research directions. -->

\\
***AI for 3D Generative Design***

\\
Essa [postagem](https://blog.insightdatascience.com/ai-for-3d-generative-design-17503d0b3943) apresenta uma abordagem utilizada para a geração de objetos 3D a partir de descrições em linguagem natural. A ideia é criar um solução que permita ao designer repetir o processo de criação de maneira mais ágil e explorar mais possibilidades. Após a criação de uma base de conhecimento do "espaço de design" composto de modelos 3D e descrições textuais, dois *autoencoders* (como exemplificado na Figura abaixo) são utilizados para codificar o conhecimento de maneira intuitiva. Com isso, o modelo é capaz de gerar um design 3D a partir de uma legenda, como você pode conferir nessa [demonstração](https://insight2020a.streamlit.io/starstorms9/shape/).

<!-- This [article](https://blog.insightdatascience.com/ai-for-3d-generative-design-17503d0b3943) covers an approach that was used to generate 3D objects from natural language descriptions. The idea is to create a solution that allows a designer to quickly reiterate in the design process and be able to explore more broadly the design space. After creating a knowledge base of the design space consisting of 3D models and text descriptions, two autoencoders (see figure below) were used to encode that knowledge in a way that can be interacted with intuitively. The model put together can then accept a text description and generate a 3D design, try it out in this [demo](https://insight2020a.streamlit.io/starstorms9/shape/). -->

\\
![](https://cdn-images-1.medium.com/max/800/0*pbBv2Wa5QX7lUufY.png)

[*Fonte*](https://blog.insightdatascience.com/ai-for-3d-generative-design-17503d0b3943)


# Ferramentas e Bases de Dados ⚙️

***Stanza — A Python NLP Library for Many Human Languages***

\\
O grupo de NLP de Stanford disponibilizou a [Stanza](https://stanfordnlp.github.io/stanza/) (denominada anteriormente como StanfordNLP), uma biblioteca em Python que oferece ferramentas de análise para mais de 70 idiomas. As funcionalidades incluem Tokenização, *Multi-Word Token Expansion*, Lematização, POS *tagging*, Reconhecimento de Entidades Nomeadas e muito mais. A biblioteca é baseada no PyTorch, com suporte a utilização em GPUs e modelos de redes neurais pré-treinadas. A [Explosion](https://github.com/explosion/spacy-stanza) já criou um *wrapper* para a Stanza, possibilitando sua utilização como um componente do Pipeline do spaCy.

<!-- The Stanford NLP Group releases [Stanza](https://stanfordnlp.github.io/stanza/) (formerly StanfordNLP), a Python NLP library that provides out-of-the-box text analytic tools for more than 70 languages. Capabilities include tokenization, multi-word token expansion, lemmatization, POS, NER, and much more. The tool is built on top of the PyTorch library with support for using GPU and pretrained neural models. [Explosion](https://github.com/explosion/spacy-stanza) has also built a wrapper around Stanza that allows you to interact with Stanza models as a spaCy pipeline. -->

\\
***GridWorld Playground***

\\
Pablo Castro criou esse [site interessante](https://gridworld-playground.glitch.me/) que implementa um *playground* para a criação de ambientes em grade, com o objetivo de observar e verificar como agentes de aprendizado por reforço tentam chegar ao objetivo, utilizando a técnica do *Q-Learning*. Dentre as funcionalidades, estão inclusas a habilidade de mudar os parâmetros do ambiente e de aprendizado em tempo real, mudar a posição dos agentes, e transferir *value functions* entre os dois. 

<!-- Pablo Castro created an interesting [website](https://gridworld-playground.glitch.me/) that provides a playground for creating a Grid World environment to observe and test how a reinforcement learning agent tries to solve the Grid World. Some features include the ability to change the learning/environment parameters in real-time, change the position of the agent, and transfer values between two agents. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*D1e6ixTEONl21t0UNmcaog.png)

\\
***X-Stance: A Multilingual Multi-Target Dataset for Stance Detection***

\\
A tarefa de [*Stance detection*](http://nlpprogress.com/english/stance_detection.html) consiste na identificação do posicionamento de um sujeito frente a uma declaração de um ator, podendo ser utilizada na avaliação de notícias falsas. Jannis Vamvas e Rico Sennrich disponibilizaram recentemente uma [base de dados de larga-escala](https://arxiv.org/abs/2003.08385) composta por textos escritos por candidatos das eleições na Suíça. Múltiplos idiomas estão disponíveis na base, o que possibilita a avaliação da tarefa de detecção de posicionamento em contextos multilíngues. Os autores também propuseram a utilização de um modelo BERT multilíngue, que apresentou um desempenho satisfatório nos cenários *zero-shot cross-lingual* and *cross-target transfer*.

<!-- [*Stance detection*](http://nlpprogress.com/english/stance_detection.html) is the extraction of a subject's reaction made to an actor’s claim which can be used for fake news assessment. Jannis Vamvas and Rico Sennrich recently published a [large-scale stance detection dataset](https://arxiv.org/abs/2003.08385) consisting of written text by electoral candidates in Switzerland. Multiple languages are available in the texts which could potentially lead to cross-lingual evaluations on the task of stance detection. The authors also propose the use of a multilingual BERT that achieves satisfactory performance on zero-shot cross-lingual and cross-target transfer. Learning across targets, in particular, is a challenging task so the authors used a simple technique involving standardized targets to train a single model on all the issues at once. -->

\\
***Create interactive textual heatmaps for Jupyter notebooks***

\\
Andreas Madsn criou uma biblioteca Python chamada [TextualHeatMap](https://github.com/AndreasMadsen/python-textualheatmap), que pode ser utilizada para gerar visualizações que auxiliam no entendimento de quais partes de uma frase estão sendo utilizadas pelo modelo na hora de predizer a próxima palavra, como ocorre em modelos de linguagem. 

<!-- Andreas Madsen created a Python library called [TextualHeatMap](https://github.com/AndreasMadsen/python-textualheatmap) that can be used to render visualizations that help to understand what parts of a sentence the model is using to predict the next word such as in language models. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*IY3tKkznwarnRxdo.gif)

*Fonte:* [*textualheatmap*](https://github.com/AndreasMadsen/python-textualheatmap)


# Artigos e Postagens ✍️

***How to generate text: using different decoding methods for language generation with Transformers***

\\
A Hugging Face publicou um [artigo](https://huggingface.co/blog/how-to-generate) revisando diferentes técnicas utilizadas para a geração de texto, focando em abordagens baseadas no *Transformer*. São discutidos métodos como *beam search* e variações de processos de amostragem ("simples", "Top-K" e "Top-p"). Já foram publicadas diversas outras postagens sobre esse mesmo assunto, porém nessa os autores dedicaram um bom tempo explicando os aspectos práticos das técnicas e como elas podem ser utilizadas na biblioteca *Transformers*.

<!-- HuggingFace published an [article](https://huggingface.co/blog/how-to-generate) explaining the different methods used for language generation in particular for Transformer based approaches. Among those techniques discussed are greedy search, beam search, sampling, top-k sampling, and top-p (nucleus) sampling. There are many articles like this out there but the authors spent more time explaining the practical side of these methods and how they can be applied via code snippets. -->

\\
***Training RoBERTa from Scratch — The Missing Guide***

\\
Motivado pela falta de um guia acessível para o treinamento do zero (*from scratch*) de modelos de linguagem baseados no BERT utilizando a biblioteca *Transformers* da Hugging Face, Marcin Zablocki disponibilizou esse [tutorial detalhado](https://zablo.net/blog/post/training-roberta-from-scratch-the-missing-guide-polish-language-model/). O guia mostra como treinar um modelo de linguagem para o Polonês e traz várias dicas sobre como evitar erros comuns, preparação dos dados, configurações de pré-processamento, tokenização, treinamento, monitoramento do processo de treino e compartilhamento do modelo.

<!-- Motivated by the lack of a comprehensive guide for training a BERT-like language model from scratch using the Transformer’s library, Marcin Zablocki shares this detailed [tutorial](https://zablo.net/blog/post/training-roberta-from-scratch-the-missing-guide-polish-language-model/). The guide shows how to train a transformer language model for the Polish language with tips on what common mistakes to avoid, data preparation, pretraining configuration, tokenization, training, monitoring training process, and sharing the model. -->

\\
![](https://cdn-images-1.medium.com/max/800/0*PFPgjeUmzvazglqg.png)

# Educação 🎓

***Getting started with JAX (MLPs, CNNs & RNNs)***

\\
Robert Lange publicou recentemente um [tutorial](https://roberttlange.github.io/posts/2020/03/blog-post-10/) ilustrando como treinar uma *Gated Recurrent Unit (GRU)* com a nova biblioteca da Google, a JAX. Na [edição passada da *Newsletter*](https://victorgarritano.github.io/personal_blog/nlp_newsletter/2020/03/16/NLP_Newsletter-PT-BR-_NLP_7.html), nós abordamos alguns tópicos relacionados à biblioteca.

<!-- Robert Lange recently published a comprehensive [tutorial](https://roberttlange.github.io/posts/2020/03/blog-post-10/) on how to train a GRU-RNN with JAX. In our [previous newsletter](https://medium.com/dair-ai/nlp-newsletter-nlp-paper-summaries-learning-to-simulate-transformers-notebooks-med7-measuring-de61fadd9db0), we also shared a couple of resources related to JAX. -->

\\
***NLP for Developers: Word Embeddings***

\\
Rachael Tatman publicou o primeiro episódio da sua nova série, a *NLP for Developers*, que cobrirá as melhores práticas relacionadas à aplicação de diversos métodos de NLP. O [primeiro vídeo](http://youtube.com/watch?v=oUpuABKoElw&feature=emb_logo) apresenta uma introdução à *word embeddings* e como são utilizados, além de dicas para evitar erros comuns quando trabalhamos com esse tipo de representação.

<!-- Rachael Tatman published the first episode of a new series called NLP for Developers that will cover best practices on how to apply a wide range of NLP methods. The [first episode](http://youtube.com/watch?v=oUpuABKoElw&feature=emb_logo) includes an introduction to word embedding and how they are used and other common issues to avoid when applying them. -->

\\
***Thomas Wolf: An Introduction to Transfer Learning and HuggingFace***

\\
Thomas Wolf apresentou essa [palestra](https://www.youtube.com/watch?v=rEGB7-FlPRs&feature=youtu.be) sobre *Transfer Learning* no *meetup* NLP Zurich, fornecendo uma excelente introdução ao assunto para o contexto de NLP. A palestra apresenta uma visão geral dos momentos mais importantes para a área, além de uma introdução às bibliotecas *Transformers* e *Tokenizers*, dois dos módulos mais populares da Hugging Face.

<!-- Thomas Wolf presented his [talk](https://www.youtube.com/watch?v=rEGB7-FlPRs&feature=youtu.be) on Transfer Learning for the NLP Zurich meetup providing a great introduction to transfer learning in NLP. The talk includes an overview of recent NLP breakthroughs and an introduction to Transformers and Tokenizers, two of the most popular libraries released by the HuggingFace team and contributors. -->

\\
![](https://cdn-images-1.medium.com/max/800/1*PMZ8ptBWo4wZ432kr-FXqA.png)


# Menções Honrosas ⭐️

\\
Você sabia que o Google Sheets fornece uma ferramenta de tradução gratuita? Amit Chaudhary compartilhou uma [postagem](https://amitness.com/2020/02/back-translation-in-google-sheets/) que mostra como utilizar essa funcionalidade para "tradução reversa", fornecendo uma maneira de aumentar a sua base de dados em tarefas de NLP.


<!-- Did you know that Google Sheets provides a free translation feature? Amit Chaudhary shares an [article](https://amitness.com/2020/02/back-translation-in-google-sheets/) that shows how to leverage the feature for back translation which is useful for augmenting your limited text corpus for NLP. -->

\\
A New York NLP estará organizando um [*meetup* online](https://www.meetup.com/NY-NLP/events/269502774/) para uma palestra intitulada *"Using Wikipedia and Wikidata for NLP"* onde será discutido como se beneficiar dos dados dessas plataformas para diferentes projetos e casos de uso de NLP.

<!-- New York NLP will be hosting an [online meetup](https://www.meetup.com/NY-NLP/events/269502774/) for a talk titled “Using Wikipedia and Wikidata for NLP” where the presenter will talk about how to leverage Wikipedia for different NLP projects and use cases. -->

\\
Lavanya Shukla escreveu esse [tutorial](https://app.wandb.ai/cayush/pytorchlightning/reports/Use-Pytorch-Lightning-with-Weights-%26-Biases--Vmlldzo2NjQ1Mw) sobre como utilizar a *PyTorch Lightning* para otimizar hiper-parâmetros de uma rede neural enquanto utilizamos funcionalidades de estrutura e estilo de código fornecidas pela biblioteca. O modelo resultante e seu desempenho utilizando diferentes combinações de hiper-parâmetros podem ser visualizados utilizando o *logger* WandB, que pode ser passado como parâmetro para o objeto responsável pelo treinamento do modelo.

<!-- Lavanya Shukla wrote this nice [tutorial](https://app.wandb.ai/cayush/pytorchlightning/reports/Use-Pytorch-Lightning-with-Weights-%26-Biases--Vmlldzo2NjQ1Mw) on how to use PyTorch Lightning to optimize hyperparameters of a neural network while at the same time taking advantage of the simple code structures/styles provided in PyTorch Lightning. The resulting model and its performance using different hyper-parameters are visualized using the results produced by the WandB logger which can be provided as a logger parameter to a trainer object. -->

\\
Um grupo de pesquisadores publicou um [estudo](https://arxiv.org/abs/2003.07845) investigando de maneira mais aprofundada porquê a técnica de *batch normalization (BN)* tende a prejudicar a performance de modelos baseados no *Transformer* para diferentes tarefas de NLP. Com base nos comportamentos observados, os autores propuseram uma nova abordagem denominada *power normalization*. A técnica proposta apresenta um desempenho superior tanto ao *BN* quanto ao *layer normalization*, outra técnica amplamente utilizada atualmente.

<!-- A group of researchers published a [study](https://arxiv.org/abs/2003.07845) investigating more in detail why batch normalization (BN) tends to degrade performance in Transformer based methods applied to different NLP tasks. Based on those findings, the authors propose a new approach called power normalization to deal with issues found in BN. The method outperforms both BN and layer normalization (commonly used these days) on a variety of NLP tasks. -->

\\
Esse [*blog post*](https://www.datasciencecentral.com/profiles/blogs/10-timeless-reference-books) apresenta uma extensa lista de livros para ajudar você a iniciar seus estudos e experiências com Aprendizado de Máquina.

<!-- This [blog post](https://www.datasciencecentral.com/profiles/blogs/10-timeless-reference-books) contains a long list of books to get you started with ML. -->

----------

Se você conhece bases de dados, projetos, postagens, tutoriais ou artigos que gostaria de ver na próxima edição da *Newsletter*, sinta-se a vontade para nos contactar através do e-mail ellfae@gmail.com ou de uma [mensagem direta no twitter](https://twitter.com/omarsar0).

\\
[*Inscreva-se*](https://dair.ai/newsletter/) *🔖 para receber as próximas edições na sua caixa de entrada!*
