---
layout: post
title: "NLP Newsletter: GPT-2 Anotado, Entendendo self-distillation, Haiku, GANILLA, Sparkwiki, Ética em NLP, Torchmeta,…"
author: fclesio
modified:
comments: true
excerpt: "Esta edição abrange tópicos como a compreensão de self-distillation, tradução de imagem para ilustração, considerações éticas para modelos de NLP, etc."
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_5.png
---


![](https://cdn-images-1.medium.com/max/1200/1*YIhZsPaiBFkRMMWo5FAhGw.png)

\\
Antes de tudo, gostaria de agradecer de ❤️ a todos vocês pelo incrível apoio e incentivo para continuar com a NLP Newsletter. Esse esforço requer pesquisa, edição, e tradução tediosas, mas que considero gratificantes e úteis para fornecer o melhor conteúdo. Espero que você esteja gostando deste conteúdo. 😉

\\
[*Assine a NLP Newsletter*](https://dair.ai/newsletter/) *🔖 para receber edições futuras via e-mail.*

# Publicações 📙

***Um entendimento teórico do self-distillation***

\\
No contexto de Deep Learning, [*self-distillation*](https://arxiv.org/pdf/1503.02531.pdf) (*NT: auto-destilação*) é o processo de transferência de conhecimento de uma arquitetura para outra. As previsões do modelo original são alimentadas como valores de destino para o outro modelo durante o treinamento. Além de ter propriedades desejáveis como a redução do tamanho dos modelos, os resultados empíricos mostram que essa abordagem funciona bem em conjuntos de dados não vistos anteriormente pelo modelo (NT: amostras _held out_). Um grupo de pesquisadores publicou recentemente um artigo que fornece uma análise teórica com o foco em um melhor entendimento sobre o que está acontecendo neste processo de _destilação do conhecimento_ e o porque ele é eficaz. Os resultados mostram que alguns poucos ciclos de destilação amplificam a regularização (devido ao fato que a técnica [*progressivamente ajuda a limitar o número de funções base que representam a solução*](https://twitter.com/TheGradient/status/1228132843630387201?s=20)) as quais tendem a reduzir o over-fitting. (Leia o paper [**aqui**](https://arxiv.org/abs/2002.05715))


\\
![](https://cdn-images-1.medium.com/max/800/1*nWYO71awfooL4MrGK-tFww.png)

[*Fonte*](https://arxiv.org/abs/2002.05715)

\\
***Os anos 2010s: Nossa década de Deep Learning / Perspectivas para os 2020s***

\\
[Jürgen Schmidhuber,](http://people.idsia.ch/~juergen/) um dos pioneiros em Inteligência Artificial,  [**postou recentemente em seu blog**](http://people.idsia.ch/~juergen/2010s-our-decade-of-deep-learning.html) uma visão histórica sobre Deep Learning desde o ano de 2010. Alguns tópicos incluem [LSTMs](https://en.wikipedia.org/wiki/Long_short-term_memory), [feedforward neural networks](https://en.wikipedia.org/wiki/Feedforward_neural_network), [GANs](https://en.wikipedia.org/wiki/Generative_adversarial_network), [deep reinforcement learning](https://en.wikipedia.org/wiki/Deep_reinforcement_learning), [meta-learning](https://en.wikipedia.org/wiki/Meta_learning_(computer_science)), world models, [distilling NNs](https://arxiv.org/abs/1503.02531), [attention learning](https://towardsdatascience.com/intuitive-understanding-of-attention-mechanism-in-deep-learning-6c9482aecf4f), etc. O artigo traz algumas perspectivas futuras para os anos 2020 chamando atenção para questões como privacidade e mercado de dados.

\\
***Usando Redes Neurais para a resolução de equações matemáticas***

\\
Pesquisadores do Facebook AI publicaram um [**paper**](https://arxiv.org/abs/1912.01412) em que apresentam um modelo treinado em problemas de matemática para prever possíveis soluções para inúmeras tarefas como, por exemplo, problemas de integração. A abordagem é baseada em uma nova estrutura semelhante à usada na [neural machine translation](https://en.wikipedia.org/wiki/Neural_machine_translation) (*NT: tradução automática neural*), em que expressões matemáticas são representadas como um tipo de linguagem e as soluções tratadas como um problema de tradução. Assim, ao invés do modelo produzir uma tradução, a saída desta tradução é a própria solução do problema. Com isso, os pesquisadores afirmam que as redes Deep Learning não são apenas boas em raciocínio simbólico, mas podem ser usadas também para tarefas mais diversas.

\\
![](https://cdn-images-1.medium.com/max/800/1*P_JtxoC8pYkXuXCp3e3QeQ.png)

*Equações sendo usadas como entrada, juntamente com a solução correspondente gerada pelo modelo—* [*fonte*](https://ai.facebook.com/blog/using-neural-networks-to-solve-advanced-mathematics-equations/)


# Criatividade e Sociedade 🎨

***Inteligência Artificial para descobertas científicas***

\\
Mattew Hutson [**informa**](https://www.sciencemag.org/news/2020/02/models-galaxies-atoms-simple-ai-shortcuts-speed-simulations-billions-times) como a inteligência artificial (IA) pode ser utilizada para produzir emuladores que têm um uso importante na modelagem de fenômenos naturais complexos e que, por sua vez, podem levar a diferentes tipos de *descobertas científicas*. A mudança na construção desses emuladores acontece devido ao fato de que estes modelos geralmente exigem dados em larga escala e uma vasta exploração de parâmetros. Um [**paper recente**](https://arxiv.org/abs/2001.08055) propõe um método chamado DENSE que é uma abordagem baseada em [*neural architecture search (NAS)*](https://en.wikipedia.org/wiki/Neural_architecture_search) (NT: Exploração e busca de arquitetura de Redes Neurais) para criar emuladores precisos, contando apenas com uma quantidade limitada de dados de treinamento. Eles o testaram executando simulações para casos que incluem astrofísica, ciência climática e energia de fusão, entre outros.

\\
***Melhorando a tradução de imagem para imagem***

\\
[GANILLA](https://arxiv.org/abs/2002.05638) é uma abordagem que propõe o uso de [GANs](https://en.wikipedia.org/wiki/Generative_adversarial_network) para melhorar a transferência de estilo e conteúdo em pares para tarefas de tradução [*image-to-image*](https://paperswithcode.com/task/image-to-image-translation) (NT: imagem para imagem). A abordagem propōe um modelo de imagem para imagem (com uma rede de geradores aprimorada) e este modelo é avaliado com base em uma nova estrutura de avaliação quantitativa que considera tanto o conteúdo quanto o estilo. A novidade do trabalho está na rede de geradores proposta, que considera um equilíbrio entre estilo e conteúdo que os modelos anteriores não conseguem. O código e os modelos pré-treinados estão [disponíveis](https://github.com/giddyyupp/ganilla). Leia o artigo completo [**aqui**](https://arxiv.org/abs/2002.05638).

\\
![](https://cdn-images-1.medium.com/max/800/1*l_B4vfaHVkXDwzM7SldiqQ.png)

\\
***Andrew Ng fala sobre o interesse em aprendizagem auto-supervisionada***

\\
Andrew Ng, o fundador do [deeplearning.ai](deeplearning.ai), falou no [**podcast de Inteligência Artificial do Lex Friedman**](https://www.youtube.com/watch?v=0jspaMLxBig) sobre os seguintes tópicos: seus primeiros anos em ML, o futuro da IA, educação em IA, recomendações para o uso adequado da ML, seus objetivos pessoais e quais técnicas de ML que devemos prestar atenção nesta década de 2020.

\\
Andrew explicou o motivo da sua animação em relação ao *self-supervised representation learning.* [**Self-supervised learning**](https://lilianweng.github.io/lil-log/2019/11/10/self-supervised-learning.html) (NT: aprendizado de representação auto-supervisionado) envolve a estruturação de um problema de aprendizagem que visa obter supervisão dos próprios dados para fazer uso de grandes quantidades de dados não rotulados, o que é mais comum que os dados rotulados limpos. As representações são importantes e podem ser usadas para lidar com tarefas posteriores, semelhantes às usadas em modelos de linguagem como o [BERT](https://lilianweng.github.io/lil-log/2019/01/31/generalized-language-models.html#bert).


\\
Também há muito interesse em usar o aprendizado auto-supervisionado para treinamento de representações visuais generalizadas que tornam os modelos mais precisos em ambientes com poucos recursos. Por exemplo, um método recente chamado [**SimCLR**](https://arxiv.org/abs/2002.05709) (liderado por [Geoffrey Hinton](https://en.wikipedia.org/wiki/Geoffrey_Hinton)) propõe uma estrutura para *aprendizagem auto-supervisionada contrastante* (*NT: contrastive self-supervised learning*) de representações visuais para melhorar a classificação de imagens em diferentes configurações, como transferência de aprendizado (NT: [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning)) e aprendizado semi-supervisionado.

\\
![](https://cdn-images-1.medium.com/max/800/1*8zLzHFCyM3goc9y7KApHfg.png)

[*fonte*](https://arxiv.org/abs/2002.05709)


# Ferramentas e Datasets ⚙️

***Bibliotecas JAX***

\\
[JAX](https://github.com/google/jax) é uma nova biblioteca que combina o NumPy e [diferenciação automática](https://en.wikipedia.org/wiki/Automatic_differentiation) para realizar pesquisas de ML de alto desempenho. Para simplificar os pipelines para a construção de redes neurais usando JAX, a [DeepMind](https://deepmind.com/) lançou o [**Haiku**](https://github.com/deepmind/dm-haiku) e [**RLax**](https://github.com/deepmind/rlax). O RLax simplifica a implementação de agentes de aprendizado por reforço e o Haiku simplifica a construção de redes neurais usando *modelos familiares com o paradigma de programação orientada a objetos.*

\\
***Uma ferramenta para processar dados da Wikipédia***

\\
[**Sparkwiki**](https://github.com/epfl-lts2/sparkwiki) é uma ferramenta para processar dados da Wikipédia. Esta versão faz parte de muitos esforços para permitir pesquisas interessantes de análise comportamental, como [a captura de tendências e preconceitos em diferentes idiomas na Wikipédia](https://arxiv.org/abs/2002.06885). Os autores descobriram que, independentemente do idioma, o comportamento de navegação dos usuários da Wikipédia mostra que eles tendem a compartilhar interesses comuns por categorias como filmes, música e esportes, mas as diferenças se tornam mais aparentes com eventos locais e particularidades culturais.

\\
![](https://cdn-images-1.medium.com/max/800/1*K7N9KbQlbuqowUeePjLtdw.jpeg)

\\
***Tokenizers em Rust, DistilBERT e outros***

\\
Um novo release dos [**Transformers**](https://github.com/huggingface/transformers/releases/tag/v2.5.0) da Hugging Face inclui a integração de sua biblioteca de tokenização rápida, que visa acelerar modelos como o [BERT](https://towardsdatascience.com/bert-explained-state-of-the-art-language-model-for-nlp-f8b21a9b6270), [RoBERTa](https://arxiv.org/abs/1907.11692), [GPT-2](https://openai.com/blog/better-language-models/) e outros modelos criados pela comunidade.


# Ética em Inteligência Artificial 🚨

***Considerações éticas para modelos de NLP (Processamento de Linguagem Natural) e Machine Learning***

\\
Em um novo [**episódio**](https://soundcloud.com/nlp-highlights/106-ethical-considerations-in-nlp-research-emily-bender) do postcast [NLP Highlights,](https://soundcloud.com/nlp-highlights) [Emily Bender](https://twitter.com/emilymbender) e os hosts conversaram sobre algumas considerações éticas no desenvolvimento de modelos e tecnologias de NLP no contexto da academia e do seu uso no mundo real. Alguns dos tópicos da discussão incluem considerações éticas nas tarefas de NLP, abordagens sobre coleta de dados e eventualmente considerações na publicação de resultados.


\\
Além de todas as considerações acima, uma preocupação discutida é que a comunidade de IA está se concentrando demais na otimização de métricas específicas, o que contraria os objetivos que a IA pretende alcançar. Rachel Thomas e David Uminsky discutem os problemas dessa abordagem através de uma [**análise completa**](https://arxiv.org/abs/2002.08512) de diferentes casos de uso. Eles também propõem uma estrutura simples para mitigar este problema, que envolve o uso e a combinação de várias métricas, seguidas pelo envolvimento das pessoas afetadas diretamente pela tecnologia.


# Artigos e Blog posts ✍️

**"The Annotated GPT-2"**

\\
Aman Arora publicou recentemente uma postagem no blog excepcionalmente intitulada ["The Annotated GPT-2“](https://amaarora.github.io/2020/02/18/annotatedGPT2.html) explicando o funcionamento interno do modelo baseado em [Transformer](https://en.wikipedia.org/wiki/Transformer_(machine_learning_model)) chamado [GPT-2](https://openai.com/blog/better-language-models/). Sua abordagem foi inspirada em [The Annotated Transformer](https://nlp.seas.harvard.edu/2018/04/03/attention.html) que adotou uma abordagem de anotação para explicar as partes importantes do modelo. Aman fez um grande esforço para reimplementar o [GPT-2](https://openai.com/blog/better-language-models/) da [OpenAI](https://openai.com/) usando o [PyTorch](https://pytorch.org/) e a biblioteca [Transformers da Hugging Face](https://huggingface.co/transformers/). É um trabalho brilhante!

\\
![](https://cdn-images-1.medium.com/max/800/1*oRFMJTEojyQ-uocVES5GYA.png)

[*fonte*](https://amaarora.github.io/2020/02/18/annotatedGPT2.html)

\\
***Além do BERT?***

\\
[**Um ponto interessante foi levantado**](https://towardsdatascience.com/beyond-bert-6f51a8bc5ce1) por Sergi Castella sobre o que está além do [BERT](https://towardsdatascience.com/bert-explained-state-of-the-art-language-model-for-nlp-f8b21a9b6270). Os principais tópicos incluem o aprimoramento das métricas, uma reflexão de como a biblioteca [Transformers da Hugging Face](https://huggingface.co/transformers/) ajuda na pesquisa, alguns conjuntos de dados interessantes para análise, etc.

\\
***Operador de Compressão de Matrizes***

\\
O Blog do TensorFlow publicou um [**post**](https://blog.tensorflow.org/2020/02/matrix-compression-operator-tensorflow.html?linkId=82298016) explicando as técnicas e a importância por trás da compressão matrizes em um modelo de Deep Learning. *A compactação matricial* (*NT: Matrix compression*) pode ajudar a criar modelos menores e mais eficientes que podem ser incorporados a dispositivos menores, como telefones e assistentes domésticos. Concentrar-se na compressão dos modelos por meio de métodos como [low-rank-approximation](https://en.wikipedia.org/wiki/Low-rank_approximation) e [quantização](https://en.wikipedia.org/wiki/Quantization_(signal_processing)) significa que não precisamos comprometer a qualidade do modelo.

\\
![](https://cdn-images-1.medium.com/max/800/1*fpAdJvBIf4SKxF3gTIpe_g.png)

[*fonte*](https://blog.tensorflow.org/2020/02/matrix-compression-operator-tensorflow.html?linkId=82298016)


# Educação 🎓

***Fundamentos de NLP***

\\
Estou animado por lançado um rascunho do Capítulo 1 da minha nova série chamado [**Fundamentos de NLP**](https://medium.com/dair-ai/fundamentals-of-nlp-chapter-1-tokenization-lemmatization-stemming-and-sentença-segmentação-b362c5d07684). Esta série ensina conceitos de NLP a partir do básico, compartilhando boas práticas, referências importantes, erros comuns a serem evitados e o que está por vir no que se refere a NLP. Um [notebook no Colab](https://colab.research.google.com/drive/18ZnEnXKLQkkJoBXMZR2rspkWSm9EiDuZ) foi incluído e o projeto será mantido [aqui](https://github.com/dair-ai/nlp_fundamentals).

\\
![](https://cdn-images-1.medium.com/max/800/1*mS5NcoJ_c8hYTjiJsuu_8g.gif)

\\
***Revisão/Discussão Online: Parte I sessão de leitura para fundamentos da matemática***

\\
O time do [Meetup "Machine Learning Tokyo"](https://www.meetup.com/Machine-Learning-Tokyo/) está hospedando uma discussão on-line remota, revisando capítulos que foram abordados em suas recentes sessões de estudo on-line. O grupo já havia estudado capítulos com base no livro [Mathematics For Machine Learning](https://mml-book.github.io/) escrito por Marc Peter Deisenroth, A Aldo Faisal e Cheng Soon Ong. O [**evento**](https://www.meetup.com/Machine-Learning-Tokyo/events/268817313/) está programado para 8 de março de 2020.

\\
***Recomendações de livros***

\\
Em um segmento anterior, discutimos a importância da compressão de matriz para a construção de modelos pequenos (em termos de espaço) de ML. Se você estiver interessado em aprender mais sobre como construir redes neurais profundas menores para sistemas embarcados, confira este ótimo livro chamado [**TinyML**](https://tinymlbook.com/?linkId=82595412) de Pete Warden e Daniel Situnayake.

\\
![](https://cdn-images-1.medium.com/max/800/0*omOa3aw2bfMzX2Qm.jpg)

[*fonte*](https://www.amazon.com/TinyML-Learning-TensorFlow-Ultra-Low-Micro-Controllers/dp/1492052043)

\\
Outro livro interessante para ficar de olho é o próximo título  **“**[**Deep Learning for Coders with fastai and PyTorch: AI Applications Without a PhD**](https://www.amazon.com/Deep-Learning-Coders-fastai-PyTorch/dp/1492045527)**”** de Jeremy Howard e Sylvain Gugger. O livro tem como objetivo fornecer a base matemática necessária para criar e treinar modelos para abordar tarefas nas áreas de visão computacional e NLP.

\\
![](https://cdn-images-1.medium.com/max/800/0*i2OmtWOncatOYsZv.jpg)


[*source*](https://www.amazon.com/Deep-Learning-Coders-fastai-PyTorch/dp/1492045527)


# Menções honrosas ⭐️

Você pode acessar a NLP Newsletter anterior em PT-BR [aqui](https://dair.ai/NLP_Newsletter-PT-BR-_PyTorch3D,_DeepSpeed,_Turing-NLG/).

\\
[**Torchmeta**](https://arxiv.org/abs/1909.06576) é uma biblioteca para pesquisa em meta-aprendizado. Esta biblioteca é de autoria de Tristan Deleu.

\\
Manuel Tonneau escreveu um [**post**](https://creatext.ai/blog-posts/machine-text-writing-gpt2-beam-search?utm_medium=newsletter) oferecendo uma visão mais detalhada em relação ao hardware envolvido em modelagem de linguagem. Alguns tópicos incluem *greedy* e [beam search](https://en.wikipedia.org/wiki/Beam_search) e [nucleus sampling](https://openreview.net/forum?id=rygGQyrFvH).

\\
O MIT [**lançou**](http://introtodeeplearning.com/) o plano de estudos completo e a programação do curso intitulado "Introdução ao Deep Learning", incluindo vídeos das palestras já ministradas. Eles pretendem lançar palestras em vídeo e slides uma vez por semana.

\\
Aprenda a treinar um modelo para [reconhecimento de entidade (NER)](https://en.wikipedia.org/wiki/Named-entity_recognition) usando uma abordagem baseada no Transformer em [**300 linhas de código**](https://github.com/huggingface/transformers/blob/master/examples/ner/run_pl_ner.py). Você pode encontrar o Google Colab em anexo [aqui](https://colab.research.google.com/drive/184LPlygvdGGR64hgQl3ztqzZJu8MmITn).

----------

Se você tiver datasets, projetos, postagens de blog, tutoriais ou documentos que deseja compartilhar na próxima edição da NLP Newsletter, entre em contato conosco pelo e-mail ellfae@gmail.com ou via [**DM no Twitter**](https://twitter.com/omarsar0).

\\
[*Assine a NLP Newsletter*](https://dair.ai/newsletter/) *🔖 para receber edições futuras via e-mail.*
