---
layout: post
title: "NLP Newsletter [PT-BR] #6: BERTology Primer, fastpages, T5, Data Science Education, PyTorch Notebooks, Slow Science in ML"
author: VictorGarritano
modified:
comments: true
excerpt: "Essa edição cobre tópicos como extensões ao modelo Transformer, desaceleração no processo de publicação em Aprendizado de Máquina, divulgação de livros e projetos sobre ML e NLP e muito mais"

tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_6.png
---



![](https://cdn-images-1.medium.com/max/1200/1*vWICxAehSy3xOnqGIXtpoQ.png)

\\
<!-- Welcome to the sixth issue of the NLP Newsletter. Thanks for all the support and for taking the time to read through the latest in ML and NLP. This issue covers topics that range from extending the Transformer model to slowing publication in ML to a series of ML and NLP book and project launches. -->

Seja muito bem-vindo à sexta edição da *NLP Newsletter*. Agradecemos por todo o suporte e dedicação à leitura dos temas mais recentes em ML e NLP. Essa edição cobre tópicos como extensões ao modelo Transformer, desaceleração no processo de publicação em Aprendizado de Máquina, divulgação de livros e projetos sobre ML e NLP e muito mais.

\\
***Algumas atualizaçãoes sobre a NLP Newsletter e o dair.ai***

\\
<!-- We have been translating the newsletter to other languages such as Brazilian Portuguese, Chinese, Arabic, Spanish, among others. Thanks to those folks that have helped with the translations 🤗. You can also contribute [here](https://github.com/dair-ai/dair-ai.github.io/issues/11). -->

Nós estamos traduzindo a Newsletter para outros idiomas, como o Português Brasileiro, Chinês, Árabe, Espanhol, dentre outros. Agradecemos aos colegas que realizaram as traduções 🤗. Você também pode contribuir [aqui](https://github.com/dair-ai/dair-ai.github.io/issues/11)!

\\
<!-- A month ago, we officially launched our new [website](https://dair.ai/). You can look at our [GitHub organization](https://github.com/dair-ai) for more information about dair.ai and projects. If you are interested in seeing how others are already contributing to dair.ai or are interested in contributing to democratizing artificial intelligence research, education, and technologies, check our [issues](https://github.com/dair-ai/dair-ai.github.io/issues) section. -->

No mês passado, nós realizamos o lançamento oficial do nosso novo [website](https://dair.ai/). Você pode dar uma olhada em nossa [organização no GitHub] (https://github.com/dair-ai) para mais informações sobre os projetos em andamento. Se você está interessado em saber mais sobre as contribuições já realizadas para a dar.ai, ou mesmo contribuir para a democratização das tecnologias, ensino e pesquisa sobre Inteligência Artificial, veja nossa seção de [issues](https://github.com/dair-ai/dair-ai.github.io/issues).

\\
[*Inscreva-se*](https://dair.ai/newsletter/) *🔖 para receber as próximas edições na sua caixa de entrada!*


# Publicações 📙

***A Primer in BERTology: What we know about how BERT works***

\\
<!-- Transformer-based models have shown to be effective at approaching different types of NLP tasks that range from *sequence labeling* to *question answering*. One of those models called BERT [(Devlin et al. 2019)](https://arxiv.org/abs/1810.04805) is widely used but, like other models that employ deep neural networks, we know very little about their inner workings. A new [paper](https://arxiv.org/abs/2002.12327) titled “**A Primer in BERTology: What we know about how BERT works**” aims to answer some of the questions about why BERT performs well on so many NLP tasks. Some of the topics addressed in the paper include the type of knowledge learned by BERT and where it is represented, and how that knowledge is learned and other methods researchers are using to improve it. -->

Modelos baseados no *Transformer* mostraram-se bastante efetivos na abordagem das mais diversas tarefas de Processamento de Linguagem Natural, como *sequence labeling* e *question answering*. Um desses modelos, o BERT [(Devlin et al. 2019)](https://arxiv.org/abs/1810.04805), vem sendo amplamente utilizado. Entretanto, assim como acontece com outros modelos que utilizam redes neurais profundas, ainda sabemos muito pouco sobre seu funcionamento interno. Um novo [artigo](https://arxiv.org/abs/2002.12327) entitulado “**A Primer in BERTology: What we know about how BERT works**” busca começar a responder questões sobre as razões que possibilitam o BERT funcionar tão bem em tantas tarefas de NLP. Alguns dos tópicos investigados no trabalho incluem o tipo de conhecimento aprendido pelo modelo e como o mesmo é representado, além de métodos que outros pesquisadores estão utilizando para melhorar o processo de aprendizado.

\\
***Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer***

\\
<!-- Google AI recently published a [method](https://arxiv.org/abs/1910.10683) that brings together all the lessons learned and improvements from NLP transfer learning models into one unified framework called Text-to-Text Transfer Transformer (T5). This work proposes that most NLP tasks can be formulated in a text-to-text format, suggesting that both the inputs and outputs are texts. The authors claim that this “*framework provides a consistent training objective both for pre-training and fine-tuning*”. T5 is essentially an encoder-decoder Transformer that applies various improvements in particular to the attention components of the model. The model was pre-trained on a newly released dataset called [Colossal Clean Crawled Corpus](https://www.tensorflow.org/datasets/catalog/c4) and achieved SOTA results on NLP tasks such as summarization, question answering, and text classification. -->

A Google AI publicou recentemente um [método](https://arxiv.org/abs/1910.10683) que incorpora todas as lições aprendidas e melhorias do *Transfer Learning* para NLP num *franework* unificado, denominado Text-to-Text Transfer Transformer (T5). O trabalho propõe que a maioria das tarefas de NLP podem ser formuladas no formato *text-to-text*, onde tanto a entrada quanto a saída do problema apresentam-se na forma de texto. Os autores alegam que "esse framework fornece uma função objetivo para treinamento que é consistente tanto na fase de pré-treinamento quanto no *fine-tuning*". O T5 é essencialmente um *encoder-decoder* baseado no *Transformer*, com várias melhorias, em especial nos componentes de atenção da arquitetura. O modelo foi pré-treinado sobre uma nova base de dados disponibilizada recentemente, conhecida como [Colossal Clean Crawled Corpus](https://www.tensorflow.org/datasets/catalog/c4), onde foi estabelecido um novo estado-da-arte para tarefas como sumarização, *question answering* e classificação de texto.

\\
![](https://cdn-images-1.medium.com/max/800/1*T9MXxcDOd2fX6xblbu7VdQ.png)


[*(Raffel et al. 2020)*](https://arxiv.org/abs/1910.10683)

\\
***12-in-1: Multi-Task Vision and Language Representation Learning***

\\
<!-- Current research uses independent tasks and datasets to perform vision-and-language research even when the “*visually-grounded language understanding skill*s” required to perform these tasks overlap. A new [paper](https://arxiv.org/abs/1912.02315) (to be presented at CVPR) proposes a large-scale multi-task approach to better model and jointly train vision-and-language tasks to generate a more generic vision-and-language model. The model reduces the parameter size and performs well on tasks like caption-based image retrieval and visual question answering. -->

Os esforços de pesquisa atuais utilizam tarefas e bases de dados independentes para realizar avanços na área de linguística e visão computacional, mesmo quando os conhecimentos necessários para abordar essas tarefas possuem interseção. Um novo [artigo](https://arxiv.org/abs/1912.02315) (que será apresentado na CVPR) propõe uma abordagem multi-tarefa em larga escala para uma melhor modelagem e treinamento conjunto em tarefas de linguística e visão computacional, gerando uma modelo mais genérico para as mesmas. O método reduz a quantidade de parâmetros e apresenta um bom desempenho em problemas como recuperação de imagens baseadas em legendas, e *question answering* visual.

\\
![](https://cdn-images-1.medium.com/max/800/1*yyvN4bK0K2iykyJ2-QVBjw.png)


[*(Lu et al. 2020)*](https://arxiv.org/abs/1912.02315)

\\
***BERT Can See Out of the Box: On the Cross-modal Transferability of Text Representations***

\\
<!-- reciTAL researchers and collaborators published a paper that aims to answer the question of whether a BERT model can produce representations that generalize to other modalities beyond text such as vision. They propose a model called BERT-gen that leverages mono or multi-modal representations and achieve improved results on visual question generation datasets. -->

Pesquisadores e colaboradores da reciTAL publicaram um trabalho que busca responder se um modelo BERT é capaz de gerar representações que generalizam para outras áreas, além de texto e visão computacional. Os autores apresentam um modelo denominado *BERT-gen*, que tira proveito de representações mono e multi-modais para obter desempenhos superiores em bases de dados de gerações de perguntas baseadas em imagens.

\\
![](https://cdn-images-1.medium.com/max/800/1*2NgR7yBuVLDcEza9UT41dw.png)


[*(Scialom et al. 2020)*](https://arxiv.org/abs/2002.10832)


# Criatividade e Sociedade 🎨

***The Next Decade in AI: Four Steps Towards Robust Artificial Intelligence***

\\
<!-- Gary Marcus recently published a [paper](https://arxiv.org/abs/2002.06177) where he explains a series of steps that, in his view, we should be taking to build more robust AI systems. Gary’s central idea in this paper is to focus on building hybrid and knowledge-driven systems guided by cognitive models as opposed to focusing on building larger systems that require more data and computation power. -->

Gary Marcus publicou recentemente um [trabalho](https://arxiv.org/abs/2002.06177) onde ele explica a série de passos que, na opinião dele, devem ser seguidos para o desenvolvimento de sistemas de IA mais robustos. A ideia central do artigo é priorizar a construção de sistemas híbridos e orientados à conhecimento, guiados por modelos cognitivos, ao invés da proposição de modelos com mais parâmetros que exigem mais dados e poder computacional.

\\
***10 Breakthrough Technologies 2020***

\\
<!-- MIT Technology Review published a list of the [10 breakthroughs](https://www.technologyreview.com/lists/technologies/2020/) they have identified that will make a difference in solving problems that could change the way we live and work. The list — in no particular order — includes unhackable internet, hyper-personalized medicine, digital money, anti-aging drugs, AI-discovered molecules, satellite mega-constellations, quantum supremacy, Tiny AI, differential privacy, and climate attribution. -->

A revista *MIT Technology Review* publicou a lista dos [10 avanços](https://www.technologyreview.com/lists/technologies/2020/) tecnológicos que segundo eles farão a diferença na resolução de problemas que podem mudar a maneira como vivemos e trabalhamos. A lista — sem ordem específica — inclui a internet *não-hackável*, medicina hiper-personalizada, moedas digitais, medicamentos anti-idade, moléculas descobertas por sistemas de IA, mega-constelações de satélites artificias, supremacia quântica, IA em aparelhos celulares, privacidade diferencial e *climate attribution*.

\\
***Time to rethink the publication process in machine learning***

\\
<!-- Yoshua Bengio recently [wrote](https://yoshuabengio.org/2020/02/26/time-to-rethink-the-publication-process-in-machine-learning/) on his concerns about the fast-paced cycles of ML publications. The main concern is that due to the velocity of publishing, a lot of papers get published that contain errors and are just incremental, whereas spending more time and ensuring rigour, which is how it used to work many years ago, seems to be vanishing. On top of it all, students are the ones that have to deal with the negative consequences of this pressure and stress. To address the situation, Bengio talks about his actions to help in the process of slowing down research publications for the good of science. -->

Yoshua Bengio [escreveu](https://yoshuabengio.org/2020/02/26/time-to-rethink-the-publication-process-in-machine-learning/) recentemente sobre suas preocupações em relação aos atuais ciclos acelerados de publicações em Aprendizado de Máquina. O ponto principal é que, por causa da velocidade dessas, diversos trabalhos publicados apresentam erros e são apenas incrementais, deixando o investimento de tempo na revisão e verificação do rigor empregado na metodologia e experimentos de lado. Diante de tudo isso, os estudantes são aqueles que precisam lidar com as consequências negativas da pressão e estresse gerados por essa situação. Com o objetivo de solucionar esse problema, Bengio compartilha suas ações para ajudar no processo de desaceleração das publicações para o bem da ciência.

# Ferramentas e Bases de Dados ⚙️

***Implementação da PointerGenerator network com a AllenNLP***

\\
<!-- Pointer-Generator networks aim to augment sequence-to-sequence attentional models that are used to [improve](https://arxiv.org/abs/1704.04368) [*abstractive summarization*](https://arxiv.org/abs/1704.04368). If you wish to use this technique for abstractive summarization using AllenNLP, Kundan Krishna has developed a [library](https://github.com/kukrishna/pointer-generator-pytorch-allennlp) that allows you to run a pretrained model (provided) or train your own model. -->

Redes *Pointer-Generator* buscam aprimorar o mecanismo de atenção de modelos *sequence-to-sequence* e são utilizadas para [melhorar o desempenho](https://arxiv.org/abs/1704.04368) em tarefas como [sumarização abstrata](https://arxiv.org/abs/1704.04368). Se você gostaria de utilizando essa técnica com a *framework* AllenNLP, saiba que o Kundan Krishna desenvolveu um [módulo](https://github.com/kukrishna/pointer-generator-pytorch-allennlp) que permite a execução de um modelo pré-treinado dessa categoria, além do treinamento de um novo modelo do zero.

\\
![](https://cdn-images-1.medium.com/max/800/1*Fa4G6BrnJm3NSDr3TDHhfw.jpeg)

\\
***Question answering para diferentes idiomas***

\\
<!-- With the proliferation of Transformer models and their effectiveness for large-scale NLP tasks performed in other languages, there has been an impressive amount of effort to release different types of datasets in different languages. For instance, Sebastian Ruder [shared](https://twitter.com/seb_ruder/status/1231713840502657025?s=20) a list of datasets that can be used for question answering research in different languages: [DuReader](https://www.aclweb.org/anthology/W18-2605/), [KorQuAD](https://arxiv.org/abs/1909.07005), [SberQuAD](https://arxiv.org/abs/1912.09723), [FQuAD](https://arxiv.org/abs/2002.06071), [Arabic-SQuAD](https://arxiv.org/abs/1906.05394), [SQuAD-it](https://github.com/crux82/squad-it), and [Spanish SQuAD](https://arxiv.org/abs/1912.05200v2). -->

Com a disseminação de modelos baseados no *Transformer* e sua efetividade em tarefas de NLP aplicadas a outros idiomas, existe um esforço significativo na construção e liberação de diferentes bases de dados em diferentes dialetos. Por exemplo, o Sebastian Ruder [compartilhou](https://twitter.com/seb_ruder/status/1231713840502657025?s=20) uma lista de *datasets* que podem ser utilizados no desenvolvimento de métodos para *question answering* em diversas línguas: DuReader](https://www.aclweb.org/anthology/W18-2605/), [KorQuAD](https://arxiv.org/abs/1909.07005), [SberQuAD](https://arxiv.org/abs/1912.09723), [FQuAD](https://arxiv.org/abs/2002.06071), [Arabic-SQuAD](https://arxiv.org/abs/1906.05394), [SQuAD-it](https://github.com/crux82/squad-it) e [Spanish SQuAD](https://arxiv.org/abs/1912.05200v2).

\\
***PyTorch Lightning***

\\
<!-- PyTorch Lightning is a [tool](https://towardsdatascience.com/from-pytorch-to-pytorch-lightning-a-gentle-introduction-b371b7caaf09) that allows you to abstract training that could require setting up GPU/TPU training and the use of 16-bit precision. Getting those things to work can become tedious but the great news is that PyTorch Lightning simplifies this process and allows you to train models on multi GPUs and TPUs without the need to change your current PyTorch code. -->

A PyTorch Lightning é uma [ferramenta](https://towardsdatascience.com/from-pytorch-to-pytorch-lightning-a-gentle-introduction-b371b7caaf09) que possibilita a abstração da escolha do dispositivo utilizado durante o treinamento de redes neurais (CPU ou GPU), além do uso de precisão de 16 bits. Fazer essas configurações funcionarem pode ser um trabalho entediante, mas felizmente os colaboradores da PyTorch Lightning simplificaram esse processo, permitindo o treinamento de modelos em várias GPUs/TPUs sem a necessidade de alteração do código.

\\
***Graph Neural Networks no TF2***

\\
<!-- A Microsoft Research team releases a [library](https://github.com/microsoft/tf2-gnn) that provides access to implementations of many different graph neural network (GNN) architectures. This library is based on TensorFlow 2 and also provides data-wrangling modules that can directly be used in training/evaluation loops. -->

O time de pesquisa da Microsoft liberou uma [biblioteca](https://github.com/microsoft/tf2-gnn) com a implementação de diversas arquiteturas de *Graph Neural Networks (GNNs)*. A biblioteca, baseada na versão 2.0 do TensorFlow, fornece funcionalidades para manipulação de dados que podem ser utilizadas diretamente nas iterações de treino/avaliação.

\\
***Pre-training SmallBERTa — A tiny model to train on a tiny dataset***

\\
<!-- Have you ever wanted to train your own language model from scratch but didn’t have enough resources to do so? If so, then Aditya Malte have you covered with this great [Colab notebook](https://gist.github.com/aditya-malte/2d4f896f471be9c38eb4d723a710768b#file-smallberta_pretraining-ipynb) that teaches you how to train an LM from scratch with a smaller dataset. -->

Você já pensou em treinar o seu próprio modelo de linguagem do zero, mas nunca teve o poder computacional necessário para isso? Se já, então o Aditya Malte pode lhe ajudar com esse excelente [notebook no Colab](https://gist.github.com/aditya-malte/2d4f896f471be9c38eb4d723a710768b#file-smallberta_pretraining-ipynb) que exemplifica o processo de treinamento de um modelo de linguagem numa base de dados reduzida.

# Ética em IA 🚨

***Why faces don’t always tell the truth about feelings***

\\

Há algum tempo, diversos pesquisadores e empresas tentam construir modelos de IA que consigam entender e reconhecer emoções em contextos visuais ou textuais. Um novo [artigo](https://www.nature.com/articles/d41586-020-00507-5) reabre o debate que técnicas de IA que tentam reconhecer emoções diretamente de imagens faciais não estão fazendo seu trabalho direito. O argumento principal, formulado por psicólogos proeminentes na área, é que não existe evidência da existência de expressões universais que possam ser utilizadas na detecção de emoções de maneira independente. Seria necessária uma melhor compreensão de traços de personalidade e movimentos corporais por parte do modelo, dentre outras características, para que seja possível detectar as emoções humanas de maneira mais precisa.

<!-- For some time now, many researchers and companies have attempted to build AI models that understand and can recognize emotions either in the textual or visual context. A new [article](https://www.nature.com/articles/d41586-020-00507-5) reopens the debate that AI techniques that aim to recognize emotion directly from face images are not doing it right. The main argument, raised by prominent psychologists in the space, is that there is no evidence of universal expressions that can be used for emotion detection from face images alone. It would take a model better understanding of personality traits, body movement, among other things to really get closer to more accurately detecting the emotions displayed by humans. -->

\\
***Differential Privacy and Federated Learning Explicadas***

\\
<!-- One of the ethical considerations when building AI systems is to ensure privacy. Currently, this can be achieved in two ways, either using differential privacy or federated learning. If you want to know more about these topics, Jordan Harrod provides us a great introduction in this [video](https://www.youtube.com/watch?v=MOcTGM_UteM) which also includes a hands-on practice session with the use of a Colab notebook. -->

Uma das considerações éticas que devem ser levadas em consideração durante a construção de sistemas de IA é a garantia de privacidade. Atualmente, essa garantia pode ser obtida de duas maneiras: através da *differential privacy* ou do *federated learning*. Se você quiser saber mais sobre esses dois tópicos, Jordan Harrod produziu uma excelente introdução nesse [vídeo](https://www.youtube.com/watch?v=MOcTGM_UteM), que inclui uma sessão *hands-on* utilizando *notebooks* do Colab.

# Artigos e Postagens ✍️

***A Deep Dive into the Reformer***

\\
<!-- Madison May wrote a [new blog post](https://www.pragmatic.ml/reformer-deep-dive/) that provides a deep dive into [Reformer](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html), which is a new and improved Transformer-based model recently proposed by Google AI. We also featured Reformer in a [previous issue](https://medium.com/dair-ai/nlp-newsletter-reformer-deepmath-electra-tinybert-for-search-vizseq-open-sourcing-ml-68d5b6eed057) of the newsletter. -->

Madison May realizou uma [postagem](https://www.pragmatic.ml/reformer-deep-dive/) em seu *blog* que fornece uma análise mais profunda do [Reformer](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html), um novo modelo baseado no *Transformer*, proposto recentemente pela Google AI. O *Reformer* já havia aparecido numa [edição anterior](https://medium.com/dair-ai/nlp-newsletter-reformer-deepmath-electra-tinybert-for-search-vizseq-open-sourcing-ml-68d5b6eed057) da Newsletter.

\\
***Uma plataforma de blogs gratuita***

\\
A [fastpages](https://fastpages.fast.ai/fastpages/jupyter/2020/02/21/introducing-fastpages.html) permite a criação e configuração automática de um *blog* utilizando a *GitHub pages* de maneira gratuita. Essa solução simplifica o processo de publicação e também oferece suporte à utilização de documentos exportados e *Jupyter notebooks*.

<!-- allows you to automatically set up a blog using GitHub pages for free. This solution simplifies the process of publishing a blog and it also supports the use of exported word documents and Jupyter notebooks. -->

\\
***Dicas para entrevistas na Google***

\\
<!-- Pablo Castro, from the Google Brain team, published an [excellent blog post](https://psc-g.github.io/interviews/google/2020/02/25/interviewing-at-google.html) highlighting a list of tips for those interested in interviewing for a job at Google. Topics include advice on how to prepare for the interview, what to expect during the interview, and what happens after the interview. -->

Pablo Castro, do time da Google Brain, publicou uma [excelente postagem](https://psc-g.github.io/interviews/google/2020/02/25/interviewing-at-google.html) destacando as principais dicas para aqueles interessados em aplicar para uma posição na Google. Os tópicos abordados incluem dicas sobre o processo de entrevistas, como preparação, o que esperar durante e o que acontece depois delas.

\\
***Transformers are Graph Neural Networks***

\\
<!-- Both graph neural networks (GNNs) and Transformers have shown to be effective at different NLP tasks. To better understand the inner workings behind these approaches and how they relate, Chaitanya Joshi wrote a great [article](https://graphdeeplearning.github.io/post/transformers-are-gnns/) explaining the connection between GNNs and Transformers and different ways these methods can be combined in a sort of hybrid model. -->

*Graph Neural Networks (GNNs)* e *Transformers* mostraram-se bastante efetivos em diversas tarefas de NLP. Com o objetivo de compreender melhor o funcionamento interno dessas arquiteturas e como elas se relacionam, Chaitanya Joshi escreveu um excelente [artigo](https://graphdeeplearning.github.io/post/transformers-are-gnns/) em seu *blog*, evidenciando a conexão entre GNNs e *Transformers*, e as diversas maneiras pelas quais esses métodos podem ser combinados e utilizados em conjunto.

\\
![](https://cdn-images-1.medium.com/max/800/0*u-BkejfKSKcnWOBx.jpg)

*Representação de uma frase como um grafo completo de palavras —* [*fonte*](https://graphdeeplearning.github.io/post/transformers-are-gnns/)

\\
***CNNs e Equivariância***

\\
<!-- Fabian Fuchs and Ed Wagstaff [discuss](https://fabianfuchsml.github.io/equivariance1of2/) the importance of equivariance and how CNNs enforce it. The concept of equivariance is first defined and then discussed in the context of CNNs with respect to translation. -->

Fabian Fuchs e Ed Wagstaff [discutiram](https://fabianfuchsml.github.io/equivariance1of2/) a importância da equivariância e como as *Convolutional Neural Networks (CNNs)* garantem essa propriedade. O conceito é apresentado e discutido posteriormente no contexto de CNNs em relação à translação.

\\
***Self-supervised learning com imagens***

\\

A técnica de *self-supervised learning* foi amplamente discutida nas edições anteriores da Newsletter devido ao seu papel em modelos recentes para *language modeling*. Esse [*blog post*](https://datasciencecastnet.home.blog/2020/02/22/self-supervised-learning-with-image%e7%bd%91/), feito pelo Jonathan Whitaker, fornece uma explicação intuitiva da técnica de aprendizado no contexto de imagens. Se você deseja um conhecimento mais profundo sobre o assunto, o Amit Chaudhary também publicou um [artigo interessante](https://amitness.com/2020/02/illustrated-self-supervised-learning/) descrevendo o conceito de maneira visual.

<!-- Self-supervised has been discussed a lot in previous issues of the NLP Newsletter due to the role it has played in modern techniques for language modeling. This [blog post](https://datasciencecastnet.home.blog/2020/02/22/self-supervised-learning-with-image%e7%bd%91/) by Jonathan Whitaker provides a nice and intuitive explanation of self-supervision in the context of images. If you are really interested in the topic, Amit Chaudhary also wrote an excellent [blog post](https://amitness.com/2020/02/illustrated-self-supervised-learning/) describing the concept in a visual way. -->


# Educação 🎓

***Stanford CS330: Deep Multi-Task and Meta-Learning***

\\

A universidade de Stanford liberou recentemente suas vídeo-aulas, numa *playlist* no YouTube, para o [novo curso em *deep multi-task e meta-learning*](https://www.youtube.com/playlist?list=PLoROMvodv4rMC6zfYmnD7UG3LVvwaITY5). Os assuntos apresentados incluem *bayesian meta-learning*, *lifelong learning*, uma visão geral sobre aprendizado por reforço, *model-based reinforcement learning*, entre outros.

<!-- Stanford recently released video recordings, in the form of a YouTube playlist, for their new [course on deep multi-task and meta-learning](https://www.youtube.com/playlist?list=PLoROMvodv4rMC6zfYmnD7UG3LVvwaITY5). Topics include bayesian meta-learning, lifelong learning, a reinforcement learning primer, model-based reinforcement learning, among others. -->

\\
***PyTorch Notebooks***

\\

A dar.ai liberou recentemente um [compilado de *notebooks*](https://github.com/dair-ai/pytorch_notebooks) apresentando uma introdução à redes neurais profundas utilizando o PyTorch. O trabalho continua em desenvolvimento, e alguns dos tópicos já disponíveis incluem como implementar um modelo de regressão logística do zero, assim como a programação de redes neurais *feed-forward* e recorrentes. Notebooks no Colab estão disponíveis no GitHub.

<!-- dair.ai releases a [series of notebooks](https://github.com/dair-ai/pytorch_notebooks) that aim to get you started with deep neural networks using PyTorch. This is a work in progress and some current topics include how to implement a logistic regression model from scratch and how to program a neural network or recurrent neural network from scratch. Colab notebooks are also available in the GitHub repository. -->

\\
***The fastai book (draft)***

\\

Jeremy Howard e Sylvain Gugger liberaram uma [lista](https://github.com/fastai/fastbook) com alguns *notebooks* para um futuro curso que introduz conceitos de *Deep Learning* e como implementar diferentes métodos utilizando o PyTorch e a biblioteca da fastai.

<!-- Jeremy Howard and Sylvain Gugger release a [comprehensive list](https://github.com/fastai/fastbook) of draft notebooks for an upcoming course that introduces deep learning concepts and how to develop different methods using PyTorch and the fastai library. -->

\\
***Cursos gratuitos de Ciência de Dados***

\\
<!-- In case you missed it, Kaggle provides a series of [free micro-courses](https://www.kaggle.com/learn/overview) to get you started with your Data Science journey. Some of these courses include machine learning explainability, an intro to machine learning and Python, data visualization, feature engineering, and deep learning, among others. -->

O Kaggle disponibilizou uma série de [mini-cursos gratuitos]https://www.kaggle.com/learn/overview) para o pontapé inicial da sua carreira como Cientista de Dados. Os cursos abordam assuntos como Explicabilidade em ML, Introdução ao Aprendizado de Máquina e ao Python, Visualização de Dados, *Feature Engineering*, *Deep Learning*, entre outros.

\\
<!-- Here is another excellent [online data science course](https://lewtun.github.io/dslectures/) that provides a syllabus, slides, and notebooks on topics that range from exploratory data analysis to model interpretation to natural language processing. -->

Um outro [excelente curso online](https://lewtun.github.io/dslectures/) de Ciência de Dados disponibiliza notas de aulas, *slides* e *notebooks* sobre tópicos que vão desde análise exploratória até interpretação de modelos para Processamento de Linguagem Natural.

\\
<!-- ***8 Creators and Core Contributors Talk About Their Model Training Libraries From PyTorch Ecosystem*** -->

***8 Criadores e Colaboradores discutem suas bibliotecas de treinamento de modelos no ecossistema do PyTorch***

\\
<!-- nepture.ai published an [extensive article](https://neptune.ai/blog/model-training-libraries-pytorch-ecosystem?utm_source=twitter&utm_medium=tweet&utm_campaign=blog-model-training-libraries-pytorch-ecosystem) that contains detailed discussions with core creators and contributors about their journey and philosophy of building PyTorch and tools around it. -->

A nepture.ai publicou um [excelente artigo](https://neptune.ai/blog/model-training-libraries-pytorch-ecosystem?utm_source=twitter&utm_medium=tweet&utm_campaign=blog-model-training-libraries-pytorch-ecosystem) que contém discussões detalhadas com criadores e colaboradores sobre suas jornadas e a filosofia utilizada na criação do PyTorch e nas ferramentas construídas com base na biblioteca.

\\
***Visualizando Adaptive Sparse Attention Models***

\\
<!-- Sasha Rush shares an impressive [Colab notebook](http://Visualizing%20Adaptive%20Sparse%20Attention%20Models) that explains and shows the technical details of how to produce sparse softmax outputs and induce sparsity into the attention component of a Transformer model which helps to produce zero probability for irrelevant words in a given context, improving performance and interpretability all at once. -->

Sashs Rush compartilhou um [notebook impressionante](https://colab.research.google.com/drive/1EB7MI_3gzAR1gFwPPO27YU9uYzE_odSu) que explica e mostra os detalhes técnicos sobre como produzir saídas esparsas com a softmax e induzir esparsidade nos componentes de atenção do modelo *Transformer*, auxiliando na atribuição de probabilidade zero para palavras irrelevantes num dado contexto, melhorando simultaneamente o desempenho e a interpretabilidade.

\\
![](https://cdn-images-1.medium.com/max/800/1*7BB322LlVgt1zzk-cviSoA.png)

*Visualizando a distribuição de probabilidade da saída da softmax*
<!-- *Visualizing probability distribution of a softmax output* -->


# Menções Honrosas ⭐️

<!-- You can access the previous issue of the 🗞 NLP Newsletter [here](https://medium.com/dair-ai/nlp-newsletter-the-annotated-gpt-2-understanding-self-distillation-haiku-ganilla-sparkwiki-b0f47f595c82). -->

Você pode conferir a edição da passada da 🗞 Newsletter [aqui](https://medium.com/dair-ai/nlp-newsletter-the-annotated-gpt-2-understanding-self-distillation-haiku-ganilla-sparkwiki-b0f47f595c82).

\\
<!-- Conor Bell wrote this nice [python script](https://gist.github.com/connorbell/9269401d127f1e507cc9aaf2803067c4) that allows you to view and prepare a dataset that can be used for a StyleGAN model. -->

Conor Bell escreveu esse [script em Python](https://gist.github.com/connorbell/9269401d127f1e507cc9aaf2803067c4) que permite a visualização e preparação de uma base de dados que pode ser utilizada no modelo StyleGAN.

\\
<!-- Manu Romero [contributes](https://github.com/huggingface/transformers/tree/master/model_cards/mrm8488/bert-spanish-cased-finetuned-pos) a fine-tuned POS model for Spanish. The model is available for use in the Hugging Face Transformer library. It will be interesting to see this effort in other languages. -->

Manu Romero [compartilhou](https://github.com/huggingface/transformers/tree/master/model_cards/mrm8488/bert-spanish-cased-finetuned-pos) um modelo de POS tagging para o espanhol. O modelo está disponível para uso utilizando a biblioteca *Transformers* da Hugging Face. Será interessante acompanhar a divulgação de modelos para outros idiomas.

\\

Esse [repositório](https://github.com/tomohideshibata/BERT-related-papers) contém uma extensa lista de artigos, cuidadosamente selecionados, que possuem relação com o BERT e abordam diversos problemas como compressão de modelos, tarefas de domínios específicos, entre outros.

<!-- This [repo](https://github.com/tomohideshibata/BERT-related-papers) contains a long list of carefully curated BERT-related papers that approach different problems such as model compression, domain-specific, multi-model, generation, downstream tasks, etc. -->

\\
<!-- Connor Shorten published a short [15-minute video](https://www.youtube.com/watch?time_continue=79&v=-Bh_7tzyoR4&feature=emb_logo) explaining a new general framework that aims to reduce the effect of “shortcut” features in self-supervised representation learning. This is important because if not done right, the model can fail to learn useful semantic representations and potentially prove ineffective in a transfer learning setting. -->

Connor Shorten publicou um [vídeo de 15 minutos](https://www.youtube.com/watch?time_continue=79&v=-Bh_7tzyoR4&feature=emb_logo) explicando um novo *framework* que busca reduzir o efeito das *"shortcut" features* no *self-supervised representation learning*. Essa é uma tarefa importante porquê, caso não seja realizada corretamente, o modelo pode falhar em aprender representações semânticas úteis e potencialmente se tornar ineficiente durante o *transfer learning*.

\\

Sebastian Ruder publicou uma nova edição da newsletter *NLP News*, que apresenta tópicos e recursos como análises de artigos de ML e NLP em 2019, e apresentações sobre os fundamentos do *Deep Learning* e *Transfer Learning*. Confira [aqui](http://newsletter.ruder.io/issues/accelerating-science-memorizing-vs-learning-to-look-things-up-schmidhuber-s-2010s-greek-bert-arc-illustrated-reformer-annotated-gpt-2-olmpics-223195).

<!-- Sebastian Ruder published a new issue of the NLP News newsletter that highlights topics and resources that range from an analysis of NLP and ML papers in 2019 to slides for learning about transfer learning and deep learning essentials. Check it out [here](http://newsletter.ruder.io/issues/accelerating-science-memorizing-vs-learning-to-look-things-up-schmidhuber-s-2010s-greek-bert-arc-illustrated-reformer-annotated-gpt-2-olmpics-223195). -->


\\
[*Inscreva-se*](https://dair.ai/newsletter/) *🔖 para receber as próximas edições na sua caixa de entrada!*