---
layout: post
title: "NLP Newsletter #9 [PT-BR]: Guia Ilustrado de GNN, TextVQA e TextCaps, KeraStroke, SyferText, torchlayers,…"
author: haneybarg
excerpt: "A edição inclui tópicos que variam de uma ferramenta de NLP que preserva a privacidade a ferramentas interativas para pesquisar artigos relacionados ao COVID-19 até um guia ilustrado para representar graficamente redes neurais."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_9.png
---


![](https://cdn-images-1.medium.com/max/1200/1*Vq-bFSTjqYjDGAR4Ja1abw.png)

\\
Bem-vindo à 9ª edição da *NLP Newsletter*. Esperamos que você e seus entes queridos
estejam bem e se mantenham seguros. Esta edição inclui tópicos que variam de uma
ferramenta de *NLP* que preserva a privacidade a ferramentas interativas para pesquisar
artigos relacionados ao COVID-19 até um guia ilustrado para representar graficamente redes
neurais.


# Pesquisas e Publicações 📙

***Neuroevolution of Self-Interpretable Agents***

\\
Tang et al. (2020) apresentam um [trabalho](https://attentionagent.github.io/)
interessante e criativo que visa desenvolver um agente para absorver uma fração de sua
entrada visual com o objetivo de sobreviver a uma tarefa (por exemplo, evitar bater em um
curva e esquivar de bolas de fogo, como pode ser visto na figura abaixo). Usando
[neuroevolution](https://en.wikipedia.org/wiki/Neuroevolution) para treinar
*self-attention architectures* , os autores foram capazes de treinar agentes de
aprendizado por reforço para executar tarefas diferentes, permitindo apenas uma fração da
entrada. Os benefícios do modelo incluem uma redução substancial no tamanho dos
parâmetros, interpretabilidade e permitir que o modelo atenda apenas às *task-critical
visual hints.*

\\
![](https://cdn-images-1.medium.com/max/800/1*Gm8jlCUvP_JECEPspDypWg.png)

\\
***Introducing RONEC — the Romanian Named Entity Corpus***

\\
[RONEC](https://arxiv.org/abs/1909.01247) é um corpus *named entity* para o idioma
romeno que contém mais de 26.000 entidades em ~ 5.000 frases rotuladas, pertencentes a 16
classes distintas. As frases foram extraídas de um jornal sem direitos autorais, cobrindo
vários estilos. Esse corpus representa a primeira iniciativa de língua romena
especificamente direcionada ao reconhecimento de *named entity*. Está disponível nos
formatos BIO e CoNLL-U Plus e é gratuito para usar e estender
[aqui](https://github.com/dumitrescustefan/ronec).

\\
***Scaling Laws for Neural Language Models***

\\
Pesquisadores de John Hopkins e da OpenAI conduziram um
[estudo](https://arxiv.org/abs/2001.08361) empírico para entender as leis de escala para o
desempenho de modelos de linguagem. Esse tipo de estudo pode ser usado como um guia para
tomar melhores decisões sobre como usar os recursos de maneira mais eficaz. No geral,
verificou-se que modelos maiores são significativamente mais eficientes em termos de
amostra; se houver computação e dados limitados, é melhor treinar um modelo grande com
algumas etapas de treinamento, em vez de treinar um modelo menor até convergir (consulte
os resultados sumarizados na figura abaixo). Os autores fornecem mais descobertas e
recomendações ao treinar modelos de linguagem grandes (por exemplo, *Transformers*) nos
aspectos de *overfitting*, escolhendo o tamanho ideal do *batch size*, o *fine-tuning*, as
decisões de arquitetura, etc.

\\
![](https://cdn-images-1.medium.com/max/800/1*plbjqswVe4Cq8UVggqPH1w.png)

[*Kaplan et al. (2020)*](https://arxiv.org/abs/2001.08361)

\\
***Calibration of Pre-trained Transformers***

\\
Com *Transformers* pré-treinados sendo cada vez mais usados em aplicações do mundo
real, é importante entender quão *confiáveis* são suas saídas. Recente
[trabalho](https://arxiv.org/abs/2003.07892) de UT Austin mostra que as probabilidades
posteriores do *BERT* e do *RoBERTa* são relativamente calibradas (isto é, consistentes
com resultados empíricos) em três tarefas (inferência de linguagem natural, detecção de
paráfrase e *commonsense reasoning*) com conjuntos de dados *em domínio* e desafiadores
*fora do domínio*.  Os resultados mostram que: (1) quando usados fora da caixa, modelos
pré-treinados e prontos para uso são calibrados *em domínio*; e (2) escala de temperatura
é eficaz na redução adicional de erros de calibração *em domínio*, enquanto *label
smoothing* para aumentar a incerteza empírica ajuda a calibrar posteriores *fora do
domínio*.


\\
![](https://cdn-images-1.medium.com/max/800/1*ose0s-G0WfPFoleZJ1htrQ.png)

[*Desai and Durrett (2020)*](https://arxiv.org/pdf/2003.07892.pdf)

\\
***Statistical Mechanics of Deep Learning***

\\
Um recente
[artigo](https://www.annualreviews.org/doi/abs/10.1146/annurev-conmatphys-031119-050745)
examina mais de perto a conexão entre tópicos físicos/matemáticos e aprendizado
profundo. Os autores têm como objetivo discutir tópicos mais profundos que intersectam
mecânica estatística e aprendizado de máquina com o objetivo de responder perguntas que
ajudam a entender o lado teórico das redes neurais profundas e por que elas foram
bem sucedidas.

\\
***Towards an ImageNet Moment for Speech-to-Text***

\\
Em um novo
[artigo](https://thegradient.pub/towards-an-imagenet-moment-for-speech-to-text/) publicado
no *The Gradient*, Alexander Veysov explica por que eles acreditam que o momento do
ImageNet para *Speech-to-Text (STT)* chegou no contexto da língua russa. Nos últimos dois
anos, os pesquisadores também fizeram essa afirmação sobre NLP. No entanto, para para
alcançar esse momento em STT, Alexander afirma que muitas peças precisam se unir, como
disponibilizar amplamente os modelos, minimizar os requisitos computacionais e melhorar a
acessibilidade de modelos grandes pré-treinados.

# Criatividade, Ética, e Sociedade 🌎

***Browsing and searching COVID-19 related articles***

\\
Na semana passada, apresentamos um conjunto de dados públicos chamado
[CORD-19](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) que
contém documentos relacionados ao COVID. Gabriele Sarti escreveu [uma ferramenta
interativa](https://github.com/gsarti/covid-papers-browser), que permite que você pesquise
e navegue com mais eficiência tais documentos, utilizando um [modelo SciBERT com
*fine-tuning*](https://huggingface.co/gsarti/scibert-nli).

\\
![](https://cdn-images-1.medium.com/max/800/0*tu8nzUIEuSizuW5-.gif)

\\
A reciTAL também lançou um projeto chamado [COVID-19 *Smart Search
Engine*](https://covidsmartsearch.recital.ai/) para ajudar a melhorar na pesquisa e
navegação de artigos relacionados ao COVID-19, com o objetivo de ajudar pesquisadores e
profissionais de saúde a encontrar e descobrir informações com rapidez e eficiência
relacionadas ao COVID-19.

\\
![](https://cdn-images-1.medium.com/max/800/1*Y5W3sib4y6UxSr3YkQSu5Q.png)

\\
***SyferText***

\\
A OpenMined liberou a [SyferText](https://github.com/OpenMined/SyferText), uma nova
biblioteca de NLP que visa preservar a privacidade e segurança em NLP, e o processamente
de texto para conjuntos de dados privados. Ainda está em estados iniciais, mas acreditamos
que isso é um esforço muito importante para sistemas de IA mais seguros e éticos. Aqui
estão alguns [tutoriais](https://github.com/OpenMined/SyferText/tree/master/tutorials)
para começar.

\\
***David over Goliath: towards smaller models for cheaper, faster, and greener NLP***

\\
Maior é sempre melhor? Ao analisar a evolução do tamanho de modelos de linguagem nos
últimos anos, pode-se pensar que a resposta é sim. No entanto, o custo financeiro e
ambiental de treinar tais monstros é muito alto. Além disso, maior nesse caso geralmente
significa mais lento, mas a velocidade é crítica na maioria das aplicações. Isso motiva a
tendência atual de NLP a optar por modelos menores, mais rápidos e mais ecológicos, com o
desempenho preservado. Neste *post* de blog, [Manuel
Tonneau](https://www.linkedin.com/in/ACoAABs605YB_jMmGA0iLFongpVm1iKjFmKLSts/) apresenta
essa nova tendência que favorece modelos menores, com foco em três modelos recentes e
populares, *DistilBERT* da [Hugging Face](https://www.linkedin.com/company/huggingface/),
*PD-BERT* da [Google](https://www.linkedin.com/company/google/) e *BERT-of-Theseus* da
[Microsoft](https://www.linkedin.com/company/microsoft/).

\\
***A Survey of Deep Learning for Scientific Discovery***

\\
Muitas das grandes empresas hoje que concentraram esforços na pesquisa de IA acreditam que
aprendizado profundo pode ser usado como uma ferramenta para a descoberta científica. Este
[artigo científico](https://arxiv.org/abs/2003.11755) fornece uma visão abrangente de
modelos de aprendizado profundo comummente usados para diferentes casos de uso
científico. O artigo também compartilha dicas de implementação, tutoriais, outros sumários
de pesquisa e ferramentas.


# Ferramentas e Conjunto de Dados ⚙️

***TextVQA and TextCaps***

\\
Em um esforço para encorajar a construção de modelos que possam detectar e ler melhor
textos em imagens e depois argumentar para responder perguntas e gerar legendas, a
*Facebook AI* está hospedando duas competições separadas. As competições são chamadas
[TextVQA](https://textvqa.org/challenge) *Challenge* e
[TextCaps](https://textvqa.org/textcaps/challenge) *Challenge* para abordar a tarefa de
*visual question answering* e geração de legendas, respectivamente.

\\
***KeraStroke***

\\
Um dos maiores obstáculos a superar ao projetar redes neurais é o *overfitting*. Técnicas
atuais de aprimoramento da generalização, como *Dropout*, regularização e *Early Stopping*
são muito eficazes para a maioria dos casos de uso; no entanto, elas tendem a ficar aquém
ao usar modelos grandes ou conjuntos de dados menores. Em resposta a isso, Charles Averill
desenvolveu a [KeraStroke](https://pypi.org/project/kerastroke/#description), um novo
conjunto de técnicas de melhoria de generalização úteis para modelos grandes ou pequenos
conjuntos de dados. Ao alterar os valores de peso em certos casos durante o treino, os
modelos se adaptam dinamicamente aos dados de treino a que eles estão sendo alimentados.

\\
***torchlayers***

\\
[torchlayers](https://github.com/szymonmaszke/torchlayers) é uma nova ferramenta criada
em cima do PyTorch, que permite a inferência automática de forma e dimensionalidade das
camadas disponível no módulo *torch.nn*, como convolucional, recorrente, *transformer*
etc.  Isso significa que você não precisa definir explicitamente a forma das *features* de
entrada que devem ser especificadas manualmente nas camadas. Isso simplifica a definição
de um modelo em PyTorch. Veja um exemplo de um classificador básico implementado com a
*torchlayers* abaixo:

\\
![](https://cdn-images-1.medium.com/max/800/1*tHOme2pZ39sNziqdUCsn4g.png)

*Podemos ver no snippet de código que a camada Linear requer apenas o tamanho das features
de entrada, e não ambos tamanhos de saída e de entrada. Isto é inferido pela torchlayers com base
no tamanho da entrada.*


\\
***Haystack: Open-Source Framework for Question Answering at Scale***

\\
[Haystack](https://github.com/deepset-ai/haystack/) permite que você use modelos de
*transformers* em escala para *question-answering*. Ele usa um
*Retriever-Reader-Pipeline*, onde o *Retriever* é um algoritmo rápido para encontrar
documentos candidatos e o *Reader* é um *Transformer* que extrai a resposta
granular. Baseia-se nos *Transformers* da Hugging Face e da Elasticsearch. É
*open-source*, altamente modular e fácil de estender.

\\
***Teaching an AI to summarise news articles: A new dataset for abstractive summarisation***

\\
A Curation Corp está fornecendo 40.000 resumos de notícias escritos por profissionais.
Este
[artigo](https://medium.com/curation-corporation/teaching-an-ai-to-abstract-a-new-dataset-for-abstractive-auto-summarisation-5227f546caa8)
fornece uma boa introdução à sumarização de texto e aos desafios que existem com esta
tarefa particular. Além disso, apresenta o conjunto de dados, os problemas que podem ser
abordados, incluindo uma discussão sobre métodos de *fine-tuning* e de métricas de
avaliação para resumir o texto, e encerra com uma discussão para trabalhos
futuros. Instruções para acessar o conjunto de dados podem ser encontradas neste
[repositório do Github](https://github.com/CurationCorp/curation-corpus), juntamente com
[exemplos](https://github.com/CurationCorp/curation-corpus/tree/master/examples) do uso
do conjunto de dados para o *fine-tuning*.

\\
No tópico de *text summarization*, a equipe da HuggingFace adicionou ambos
[BART](https://github.com/pytorch/fairseq/blob/master/examples/bart/README.md) e
[T5](https://github.com/dair-ai/nlp_paper_summaries/blob/master/Language%20Modeling/t5-text-to-text-transformer.md)
como parte de sua biblioteca de
[Transformers](https://github.com/huggingface/transformers/releases) . Essas adições
permitem todos os tipos de tarefas de NLP, como *abstractive summarization*, tradução e
*question answering*, entre outras.


# Artigos e Postagens ✍️

***An Illustrated Guide to Graph Neural Networks***

\\
As redes neurais em grafo (*GNN*) recentemente tiveram mais adoção em tarefas como
melhorar modelos de visão computacional e previsão de efeitos colaterais devido a
interações medicamentosas. Nessa [visão
geral](https://dair.ai/An_Illustrated_Guide_to_Graph_Neural_Networks/), Rish apresenta um
guia intuitivo e ilustrado para GNNs. (*Apresentado na* [*dair.ai*](https://dair.ai/))

\\
![](https://cdn-images-1.medium.com/max/800/1*Ru3CizrB14hvpZQ7ZtgIag.png)

\\
***Finetuning Transformers with JAX + Haiku***

\\
No mês passado, a DeepMind deixou o código de Haiku livre, a versão JAX da Sonnet, sua
bliblioteca de redes neurais em TensorFlow. Esta [postagem](https://www.pragmatic.ml/finetuning-transformers-with-jax-and-haiku/) percorre a fonte
completa de uma porta do modelo pré-treinado *RoBERTa* para JAX + Haiku, depois demonstra
o *fine-tuning* do modelo para resolver uma tarefa especpifica (*downstream*). Ele
pretende ser um guia prático de uso das utilidades expostas pelo Haiku para permitir o uso
"módulos" de luz orientados a objetos, dentro do contexto das restrições de programação
funcional do JAX.

\\
***A small journey in the valley of Natural Language Processing and Text Pre-Processing for German language***

\\
Flávio Clésio escreveu um
[artigo](https://flavioclesio.com/2020/02/17/a-small-journey-in-the-valley-of-natural-language-processing-and-text-pre-processing-for-german-language/)
sobre os desafios de lidar com os problemas de NLP no idioma alemão. Ele compartilha
muitas lições aprendidas, o que funcionou e o que não funcionou, discute vários métodos
estado da arte, problemas comuns a serem evitados e uma tonelada de recursos de
aprendizado, documentos e postagens de blog.

\\
***French language keeping pace with AI: FlauBERT, CamemBERT, PIAF***

\\
Nos últimos meses, foram desenvolvidos recursos interessantes de NLP em francês. Estamos
falando sobre o *CamemBERT*, *FlauBERT* e *PIAF* (Pour une IA Francophone, para uma IA
francesa falante). Os dois primeiros são modelos de linguagem pré-treinados e o último é
conjunto de dados native de *question-answering*(*QA*) em francês. Esta
[postagem](https://piaf.etalab.studio/francophonie-ia-english/) discute todos esses três
projetos e alguns dos desafios apresentados ao longo do caminho. Essa é uma boa leitura e
guia para aquelas pessoas que trabalham em modelos diferentes no seu próprio idioma.

\\
***Custom classifier on top of BERT-like language model***

\\
Marcin escreveu outro excelente
[guia](https://zablo.net/blog/post/custom-classifier-on-bert-model-guide-polemo2-sentiment-analysis/)
mostrando como criar seu próprio classificador (por exemplo, um classificador de
sentimentos) em cima de modelos de linguagem como o BERT. É um ótimo tutorial, porque
também mostra como usar outras bibliotecas para as diferentes partes do modelo, como o
*HuggingFace Tokenizer* e *PyTorchLightning*. Encontre o notebbok do Google Colab
[aqui](https://colab.research.google.com/drive/1sajgpLTrTJDzRSlxycy8aE6ysxGqaT18).

\\
![](https://cdn-images-1.medium.com/max/800/0*66IKvwYU2Lq1kjyn.png)

[*Fonte*](https://zablo.net/blog/post/custom-classifier-on-bert-model-guide-polemo2-sentiment-analysis/)


# Educação 🎓

***Exploratory Data Analysis for Text Data***

\\
Neste [passo a passo do código](https://dair.ai/Exploratory_Data_Analysis_for_Text_Data/),
Yonathan Hadar passa por alguns métodos para análise exploratória de dados textuais com
vários exemplos de código. Apresentamos este tutorial na dair.ai porque é um tutorial
muito abrangente que usa métodos padrão para analisar dados que qualquer *data scientist*
achará útil. É um bom ponto de partida para quem começa a brincar
dados textuais.

\\
***Embeddings in Natural Language Processing***

\\
Mohammad Taher Pilehvar e Jose Camacho-Collados publicaram seu primeiro rascunho de seu
próximo
[livro](https://medium.com/r/?url=http%3A%2F%2Fjosecamachocollados.com%2Fbook_embNLP_draft.pdf)
chamado "*Embeddings in Natural Language Processing*". A ideia deste livro é discutir o
conceito de *embeddings*, que representam algumas das técnicas mais amplamente usadas em
NLP. Como
[declarado](https://medium.com/r/?url=https%3A%2F%2Ftwitter.com%2FCamachoCollados%2Fstatus%2F1246013768074747906%3Fs%3D20)
pelos autores, o livro inclui "noções básicas de modelos de espaço vetorial e *word
embeddings* a técnicas mais recentes de *embbedings* contextualizados com base em modelos
de linguagem pré-treinados."

\\
***A Brief Guide to Artificial Intelligence***

\\
O Dr. James V Stone publicou seu novo [livro](https://jim-stone.staff.shef.ac.uk/AIGuide/)
sobre Um Guia Breve para a Inteligência Artificial (*“A Brief Guide to Artificial
Intelligence”*) com o objetivo de prover uma análise geral de sistemas de IA atuais e suas
conquistas para atuar em uma sére de tarefas. Como dito no sumário, o livro é escrito em
um estilo informal, com um glossário amplo e uma lista de leituras posteriores, o que faz
dele uma introdução ideal para o campo de evolução rápida que é a IA.

\\
![](https://cdn-images-1.medium.com/max/800/0*I2YYXTCQTBmk_YiF.jpg)

\\
***Cursos de ML e Aprendizado Profundo***

\\
Sebastian Raschka lançou dois
[episódios](https://www.youtube.com/watch?time_continue=1&v=QQD9Y2FiotQ&feature=emb_logo)
gravados para seu curso sobre "Introdução ao Aprendizado Profundo e Modelos
Generativos". Você pode encontrar notas de aula e outros materiais neste
[repositório](https://github.com/rasbt/stat453-deep-learning-ss20).

\\
Aqui está outro excelente conjunto de
[palestras](https://www.youtube.com/watch?v=e-erMrqBd1w&feature=youtu.be) no tópico de
"Geometria Discreta Diferencial".

\\
Peter Bloem liberou o [catálogo](https://mlvu.github.io/) inteiro, incluindo vídeos e
slides de palestras, de seu curso introdutório de Aprendizado de Máquina, ministrado na
*VU University Amsterdam*. Os tópicos vão desde modelos lineares, busca e modelos
probabilísticos até modelos para dados sequenciais.

\\
***CNN Architecture — Implementations***

\\
Dimitris Katsios fornece um conjunto de excelentes
[tutoriais](https://github.com/Machine-Learning-Tokyo/CNN-Architectures/tree/master/Implementations)
que fornecem orientações sobre como implementar arquiteturas de redes neurais
convolucionais (CNN) de seus artigos originais. Ele propõe uma receita sobre como proceder para
implementá-las enquanto compartilha o passo a passo que inclui diagramas e código com a
capacidade de inferir o estrutura do modelo. Há muito a aprender com esses guias em termos
de orientação sobre a implementação de artigos de forma mais eficiente.


# Menções Honrosas ⭐️

Você pode encontrar as edições atenriores da *newsletter*
[aqui](https://dair.ai/NLP_Newsletter_8/). Você também pode encontrar as versões
traduzidas das edições anteriores da *NLP Newsletter*
[aqui](https://github.com/dair-ai/nlp_newsletter).

\\
Há alguns meses, apresentamos o excelente livro do Luis Serrano sobre *Grokking Machine
Learning*. [Ouça](https://content.alegion.com/podcast/grokking-machine-learning-with-luis-serrano)
Luis discutindo um pouco mais sobre seu livro e sua jornada para se tornar um educador na
área de *ML*. pode valer sua atenção

\\
Aqui estão muitas *newsletters* que podem valer sua atenção: [Sebastian Ruder’s NLP
News](http://newsletter.ruder.io/), [Made With
ML](https://madewithml.com/blog/newsletter/2020-03-25/), [SIGTYP’s
newsletter](https://sigtyp.github.io/sigtyp-newsletter-Mar-2020.html), [MLT
Newsletter](https://mailchi.mp/c70ebcf424b2/mlt-newsletter-6), [Nathan’s AI
newsletter](http://newsletter.airstreet.com/issues/your-guide-to-ai-in-q1-2020-part-1-2-212335),
etc…

\\
Jupyter agora vem com um [*debugger*
visual.](https://blog.jupyter.org/a-visual-debugger-for-jupyter-914e61716559) Isso irá
permitir que essa popular plataforma de ciência de dados seja usada mais facilmente para
fins gerais.

\\
![](https://cdn-images-1.medium.com/max/800/0*FE5Fj5DFb0U9565a.gif)

\\
Abhishek Thakur tem um ótimo
[canal](https://www.youtube.com/channel/UCBPRJjIWfyNG4X-CRbnv78A) no youtube por onde ele
percorre código mostrando como usar métodos modernos em aprendizado de máquina e
NLP. Alguns vídeos dele vão desde o *fine-tuning* dos modelos *BERT* até a classificação de
grafemas manuscritos até a construção um *framework* de aprendizado de máquina.

\\
David Silver, renomado professor e pesquisador de aprendizado por reforço, foi
[premiado](https://awards.acm.org/about/2019-acm-prize) com o Prêmio ACM em computação
para avanços inovadores em jogos de computador. Prata lidera a equipe Alpha Go que venceu
Lee Sedol em Go.

\\
Para aqueles interessados em aprender as diferenças e o trabalho interno por trás de
métodos populares de NLP , como *BERT* e *word2vec*, Mohd
[fornece](https://www.analyticsvidhya.com/blog/2019/09/demystifying-bert-groundbreaking-nlp-framework/)
uma visão geral excelente, acessível e detalhada dessas abordagens.

\\
O TensorFlow 2.2.0-rc-1 foi
[liberado](https://github.com/tensorflow/tensorflow/releases/tag/v2.2.0-rc1?linkId=85073218). Ele
inclui recursos como um *Profiler* que ajuda a identificar gargalos em modelos de ML e
orientar a otimização dos mesmos. Além disso, o Colab agora usa o TensorFlow 2 por
[padrão](https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/tutorials/quickstart/advanced.ipynb?linkId=85251566).

\\
Gabriel Peyré fornece um bom conjunto de
[notas](https://mathematical-tours.github.io/book-sources/optim-ml/OptimML.pdf) do seu
curso sobre otimização de ML. As notas incluem análise convexa, *SGD*, *autodiff*, *MLP*,
entre outros tópicos.


----------

## dair.ai updates
- ***Call for Contributions to Open Science:*** Abrimos uma solicitação
   contribuições para a ciência livre (*open science*). Existem muitas colaborações
   interessantes no *pipeline*. Queremos abrir o convite para qualquer pessoa interessada
   em contribuir para a ciência livre. Estamos procurando por voluntários, escritores,
   revisores, editores, desenvolvedores, palestrantes, pesquisadores, e interessados em
   manter projetos,…  [Junte-se a nós](https://github.com/dair-ai/dair-ai.github.io/issues/54)!

- ***NLP Research Highlights Issue #1:*** Caso você não tenha visto, nesse
  [artigo](https://dair.ai/NLP_Research_Highlights_-_Issue_-1/) nós destacamos algumas
  tendências e tópicos de NLP com um foco em sumarizar o que, o como e o porquê de uma
  seleção de artigos de NLP interessantes e importantes, publicados nos últimos meses.

----------

Se você conhece alguma base de dados, projetos, postagens, tutoriais ou artigos que
gostaria de ver na próxima edição da *Newsletter de NLP*, por favor submeta-os diretamente
aqui usando esse [formulário](https://forms.gle/3b7Q2w2bzsXE6uYo9).

\\
[*Inscreva-se*](https://dair.ai/newsletter/) *🔖 para receber as próximas edições na sua caixa de entrada.*
