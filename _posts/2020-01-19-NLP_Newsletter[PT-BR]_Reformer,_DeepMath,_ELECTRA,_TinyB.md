---
layout: post
title: "NLP Newsletter #2 [PT-BR]: Reformer, DeepMath, ELECTRA, TinyBERT para busca, VizSeq, Open-Sourcing ML,…"
author: fclesio
modified:
comments: true
excerpt: "Esta segunda newsletter aborda topics que vão de interpretabilidade de modelos para enovelamento de proteínas (protein folding) até active transfer learning"
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_2.png
---

![](https://cdn-images-1.medium.com/max/1200/1*mgWc3FhHPRfCxdPir6wSeg.png)

\\
Bem vindo novamente à NLP Newsletter! 👋 Esta segunda newsletter aborda topicos que vão de interpretabilidade de modelos para enovelamento de proteínas (protein folding) até active transfer learning. *Você pode encontrar a versão Markdown desta edição no final.*


# Publicações 📙

***Confiando na incerteza dos modelos***

\\
Um artigo recente do Google AI, publicado na NeurIPS, analisa se as probabilidades de um modelo refletem a sua capacidade de prever dados fora de distribuição ou mudança no conjunto de dados (shifted data).

\\
Ensembles profundos (Deep ensembles) tiveram um melhor desempenho (_i.e._, melhoraram a incerteza do modelo) no dataset com mudança no conjunto de dados (data shift), enquanto outros modelos não tornaram-se mais incertos com o mesmo data shift, mas ao contrario transformaram-se confidentemente errados(Leia o paper [aqui](https://arxiv.org/abs/1906.02530) e o sumário [aqui](https://ai.googleblog.com/2020/01/can-you-trust-your-models-uncertainty.html).).

\\
![](https://cdn-images-1.medium.com/max/800/0*NrsUnHS1thKq3ChK.png)

*Corrupção da imagem —* [*fonte*](https://ai.googleblog.com/2020/01/can-you-trust-your-models-uncertainty.html)

\\
***Generalização Sistemática***

\\
Um [trabalho interessante](https://www.semanticscholar.org/paper/Systematic-Generalization%3A-What-Is-Required-and-Can-Bahdanau-Murty/6c7494a47cc5421a7b636c244e13586dc2dab007) publicado na ICLR apresenta uma comparação entre modelos modulares e modelos genéricos e as suas respectivas efetividades para *generalização sistematica* em entendimento de linguagem (language understanding). Com base na avaliação do _reasoning_ realizada em uma tarefa em que se [respondia uma pergunta visual](https://arxiv.org/abs/1909.01860), os autores concluem que pode haver a necessidade de regularizadores e priorizadores explícitos para se conseguir uma generalização sistemática.


\\
***Um modelo eficiente baseado em Transformer chamado Reformer***

\\
É bem conhecido que um modelo Transformer é bastante limitado em relação à janela de contexto que pode ser coberta, devido aos cálculos de algo custo computacional realizados na camada de [Attention](https://mlexplained.com/2017/12/29/attention-is-all-you-need-explained/). Assim, só pode ser possível aplicar o modelo Transformer a tamanhos de texto limitados ou gerar frases curtas e/ou peças musicais. O GoogleAI publicou recentemente uma variante eficiente de um modelo Transformer chamado [Reformer](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html). O foco principal deste método é ser capaz de lidar com janelas de contexto muito mais altas e, ao mesmo tempo, reduzir os requisitos computacionais com a melhoria da eficiência do uso de memória. O Reformer usa o "locality-sensitive-hashing" ([LSH](https://en.wikipedia.org/wiki/Locality-sensitive_hashing)) para agrupar vetores similares e criar segmentos a partir deles, o que permite o processamento paralelo. A camada de Attention é então aplicada a estes segmentos menores e em partes vizinhas correspondentes - isto é, o que reduz a carga computacional. A eficiência de memória é obtida usando camadas reversíveis que permitem que as informações de entrada de cada camada sejam recalculadas sob demanda durante o treinamento via backpropagation. Esta é uma técnica simples que evita que o modelo tenha a necessidade de armazenar as ativações em memória. Confira este [notebook no Colab](https://colab.research.google.com/github/google/trax/blob/master/trax/models/reformer/image_generation.ipynb) para ver como um modelo Reformer pode ser aplicado a uma tarefa de geração de imagens.

\\
![](https://cdn-images-1.medium.com/max/800/0*Q6FHJ5bqZRCrBAp9.png)

*"Locality-sensitive-hashing: O Reformer assume uma sequência de palavras de entrada, onde cada palavra é na verdade um vetor representando palavras individuais (ou pixels, no caso das imagens) na primeira camada e contextos maiores nas camadas subsequentes. O LSH é aplicado à sequência, depois que as palavras são ordenadas pelo seu hash e particionadas. O Attention é aplicado apenas dentro de um único pedaço e dos seus vizinhos imediatos". - [fonte](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html)*

\\
 ***Adaptação de Dominio de forma não-supervisionada para Classificação de Textos***

\\
Este [trabalho](https://arxiv.org/abs/2001.04362) propõe uma combinação de medidas de distância incorporadas em uma função de perda adicional, para treinar um modelo e melhorar a adaptação não-supervisionada do domínio. O modelo é estendido a um DistanceNet Bandit que otimiza os resultados para "transferência para o domínio alvo de poucos recursos". O principal problema abordado com este método é como lidar com a disparidade entre os dados de diferentes domínios, especificamente no que diz respeito à tarefas de NLP, como a análise de sentimentos (sentiment analysis).

\\
***Melhoria de Representações Contextualizadas***

\\
Este [artigo](https://openreview.net/forum?id=r1xMH1BtvB) propõe uma tarefa de pré-treino mais eficiente em termos de amostragem chamada *detecção de token*. Esta tarefa pode ser utilizada para treinar um modelo linguístico que é mais eficiente do que métodos de pré-treino com modelagem de linguagem mascarada, como o BERT. O modelo é chamado ELECTRA e suas representações contextualizadas superam as do BERT e XLNET com os mesmos dados e tamanho de modelo. O método funciona particularmente bem no regime de baixa computação. Este é um esforço para construir modelos de linguagem menores e mais baratos.

\\
***Interpretabilidade de Modelos***

\\
A publicação mais recente da Distill intitulada "[Visualizing the Impact of Feature Attribution Baselines](https://distill.pub/2020/attribution-baselines/)" discute os [gradientes integrados](https://medium.com/@kartikeyabhardwaj98/integrated-gradients-for-deep-neural-networks-c114e3968eae) que são usados para interpretar redes neurais em vários problemas, identificando quais recursos são relevantes para prever um determinado ponto. O problema é definir e preservar corretamente uma noção de *falta* que é o que se pretende com a entrada de base dos gradientes integrados. O desafio aqui, no contexto da interpretabilidade de modelos, é que o método deve assegurar que o modelo não destaque as características em falta como importantes, evitando ao mesmo tempo dar zero importância às entradas de _baseline_, o que pode facilmente acontecer. O autor propõe avaliar quantitativamente os diferentes efeitos de algumas escolhas de _baseline_ previamente utilizadas e propostas que melhor preservem a noção de falta.


# Criatividade e Sociedade 🎨

***Incompatibilidade de sentimentos***

\\
Este [estudo longitudinal](https://ieeexplore.ieee.org/abstract/document/8952437) descobre que a emoção extraída através do uso de algoritmos baseados em texto, muitas vezes não é a mesma que as emoções auto-relatadas.

\\
***Compreensão da dopamina e o enovelamento de proteínas (protein folding)***

\\
A DeepMind lançou recentemente **dois** artigos interessantes na revista Nature. O primeiro [artigo](https://deepmind.com/blog/article/Dopamine-and-temporal-difference-learning-A-fruitful-relationship-between-neuroscience-and-AI) visa entender melhor como funciona a dopamina no cérebro usando a aprendizagem por reforço. O segundo [paper](https://deepmind.com/blog/article/AlphaFold-Using-AI-for-scientific-discovery) está mais relacionado com [enovelamento de proteínas](https://en.wikipedia.org/wiki/Protein_folding) e tenta compreendê-lo melhor para ser capaz de potencialmente descobrir tratamentos para uma ampla gama de doenças. Estes são grandes exemplos de como sistemas de IA poderiam potencialmente ser aplicados em aplicações do mundo real para ajudar a sociedade.

\\
![](https://cdn-images-1.medium.com/max/800/1*0mfEtacqGLSrmaUlNjJa0g.png)

*“Formas 3D complexas emergem de um conjunto de aminoácidos.” —* [*fonte*](https://deepmind.com/blog/article/AlphaFold-Using-AI-for-scientific-discovery)

\\
***Entrevistas sobre o ML na sociedade***

\\
Em uma [entrevista](https://www.youtube.com/watch?v=I-EIVlHvHRM&feature=youtu.be) com a Wired, Refik Anadol discute o potencial dos algoritmos de aprendizagem de máquina para criação de arte. Este é um excelente exemplo de como Machine Learning pode ser usado de forma a criativa.

\\
Um dos setores em que a IA pode ter um grande impacto é na educação. Em um novo [episódio](https://engineering.stanford.edu/magazine/article/emma-brunskill-amped-education-ai?sf115875862=1), que faz parte de "_The Future of Everything_", Russ Altman e Emma Brunskill têm uma discussão profunda sobre a aprendizagem assistida por computador.

# Ferramentas e Datasets ⚙️

***Modelos PyTorch em produção***

\\
O Cortex é uma ferramenta para automatizar a infra-estrutura e implementar modelos PyTorch como APIs em produção com AWS. Saiba mais sobre como isso é feito [aqui](https://medium.com/pytorch/how-to-build-production-software-with-pytorch-9a8725382f2a).

\\
***Visualizando Sequências de Geração de Texto***

\\
O time do Facebook AI lançou o [VizSeq](https://ai.facebook.com/blog/vizseq-a-visual-analysis-toolkit-for-accelerating-text-generation-research/), que é uma ferramenta que auxilia na avaliação visual de seqüências de geração de texto sob métricas como BLUE e METEOR. O principal objetivo desta ferramenta é fornecer uma análise mais intuitiva dos conjuntos de dados de texto, alavancando visualizações e tornando-as mais escaláveis e produtivas para todos os pesquisadores. Leia o artigo completo [aqui](https://www.aclweb.org/anthology/D19-3043.pdf).


\\
![](https://cdn-images-1.medium.com/max/800/1*Ff7BTxmEjUXHtYu9JkfClg.jpeg)

[*Fonte*](https://ai.facebook.com/blog/vizseq-a-visual-analysis-toolkit-for-accelerating-text-generation-research/)

\\
***Estado da arte em reconhecimento de fala online***

\\
O FacebookAI tornou open-source o [wav2letter@anywhere](https://ai.facebook.com/blog/online-speech-recognition-with-wav2letteranywhere/) que é um framework de inferência que é baseado em um modelo acústico que usa o Transformer como base para reconhecimento de fala online de última geração. Grandes melhorias estão em torno do tamanho do modelo e reduzindo a latência entre o áudio e a transcrição, o que é importante para seja obtida uma inferência mais rápida em tempo real.

\\
![](https://cdn-images-1.medium.com/max/800/1*4_2Obuu8u8l2Vtp8UMHe7Q.gif)

*Processamento de fala —* [*fonte*](https://ai.facebook.com/blog/online-speech-recognition-with-wav2letteranywhere/)

# Ética em IA 🚨

***Implicações de IA***

\\
Em um esforço para evitar abusos e ações antiéticas dos sistemas de IA sobre o público, a União Européia está considerando proibir a tecnologia de reconhecimento facial do público por cinco anos. ([História completa](https://www.reuters.com/article/us-eu-ai/eu-mulls-five-year-ban-on-facial-recognition-tech-in-public-areas-idUSKBN1ZF2QL))

\\
***Os custos ambientais de NLP***

\\
Talvez negligenciado na maioria das vezes, este [documento](https://arxiv.org/abs/1906.02243) discute as considerações energéticas e políticas para abordagens modernas de deep learning em NLP. É amplamente conhecido que os modelos atuais dependem de bilhões de parâmetros e que, por sua vez, dependem de grandes recursos computacionais que demandam um consumo substancial de energia. Os autores esperam espalhar mais consciência sobre os custos ambientais envolvidos no treinamento desses modernos modelos de NLP.

\\
Zachary Lipton discute equidade(fairness), interpretabilidade e os perigos do solucionismo em Machine Learning nesta [palestra](https://c4ejournal.net/2020/01/16/zack-lipton-fairness-interpretability-and-the-dangers-of-solutionism-ethics-of-ai-in-context2020-c4ej-2/) proferida na Universidade de Toronto. Os principais tópicos giraram em torno de considerações cuidadosas e implicações das abordagens de equidade em ML.


# Artigos e posts de blogs ✍️

***Open-Sourcing ML***

\\
Thomas Wolf, líder científico da Hugging Face, compartilha excelentes conselhos para aqueles que planejam fazer código ML open-source ou pesquisa. Encontre o tópico do Twitter [aqui](https://twitter.com/Thom_Wolf/status/1216990543533821952?s=20).

\\
***Introdução para aprendizagem auto-supervisionada para computer vision****

\\
Jeremy Howard escreveu este grande [blog post](https://www.fast.ai/2020/01/13/self_supervised/) introduzindo brevemente o conceito de aprendizagem auto-supervisionada no contexto de computer vision. Eu adoro estes pequenos resumos, pois ajudam a dar uma introdução confiável no caso de você estar interessado em aplicar técnicas deste domínio ao seu próprio problema.

\\
***TinyBERT para problemas de busca***

\\
Já vimos o sucesso de muitas variantes de modelos BERT (por exemplo, [DistilBERT](https://medium.com/huggingface/distilbert-8cf3380435b5)) que utilizam alguma forma de [destilação do conhecimento](https://nervanasystems.github.io/distiller/knowledge_distillation.html) para diminuir substancialmente o tamanho do modelo e melhorar a velocidade. Algumas pessoas usaram uma variante do BERT chamada, [TinyBERT](https://github.com/huawei-noah/Pretrained-Language-Model/tree/master/TinyBERT), e aplicaram-na a uma [solução de busca baseada em palavras-chave](https://towardsdatascience.com/tinybert-for-search-10x-faster-and-20x-smaller-than-bert-74cd1b6b5aec). Este projeto foi inspirado por esta [solução de busca](https://www.blog.google/products/search/search-language-understanding-bert/) para compreender as buscas propostas pelo Google. A maior parte da arquitetura que ela funciona é em uma CPU padrão e pode ser usada para melhorar e entender os resultados das buscas.

\\
***Active Transfer Learning***

\\
Rober Monarch escreveu este excelente [blog post](https://medium.com/pytorch/https-medium-com-robert-munro-active-learning-with-pytorch-2f3ee8ebec) sobre _Active Transfer Learning_ que faz parte de seu próximo livro chamado [Human-in-the-loop Machine Learning](https://www.manning.com/books/human-in-the-loop-machine-learning). Ele está escrevendo ótimos posts em seu blog sobre métodos para combinar inteligência humana e máquinas para resolução de problemas. Ele também fornece implementações em PyTorch dos métodos discutidos.

\\
***Revelando os segredos ocultos do BERT***

\\
Anna Roger escreveu este divertido e interessante [blog post](https://text-machine-lab.github.io/blog/2020/bert-secrets/) que fala sobre o que realmente acontece com um BERT otimizado, e se os alegados pontos fortes são usados para abordar tarefas posteriores, tais como análise de sentimentos, vinculação textual e inferência da linguagem natural, entre outras. Os resultados das análises propostas sugerem que o BERT está excessivamente superparametrizado (overparameterized) e que os benefícios identificados do componente de _self-attention_ da estrutura podem não ser necessariamente benéficos como se imagina. Em particular no que diz respeito à informação linguística que está sendo codificada e utilizada para a parte de inferência.


# Educação 🎓

***Redes Neurais para NLP***

\\
Graham Neubig, professor de PNL na CMU, tem [lançado alguns vídeos](https://www.youtube.com/playlist?list=PL8PYTP1V4I8CJ7nMxMC8aXv8WqKYwj-aJ) para a aula "Redes Neurais para NLP" que está sendo ministrada neste semestre. Eu recomendo altamente esta playlist para aqueles interessados em aprender sobre os métodos modernos de NLP.

\\
***Deep Learning Math (DeepMath)***

\\
Quer mergulhar profundamente na matemática por trás dos métodos de deep learning? Aqui está uma [série de vídeo-palestras](https://www.youtube.com/playlist?list=PLWQvhvMdDChzsThHFe4lYAff3pu2m0v2H) com uma vasta gama de palestrantes.

\\
***Cursos de Python e Tutoriais***

\\
Python tornou-se uma das linguagens de programação mais requisitadas não só na indústria de TI, mas também no espaço da ciência dos dados. Em um esforço para qualificar alunos de todo o mundo com conhecimentos práticos de Python, o Google lançou o "Google IT Automation with Python Professional Certificate". Saiba mais sobre o lançamento [aqui](https://blog.google/outreach-initiatives/grow-with-google/new-certificate-help-people-grow-careers) e veja o curso [aqui](https://www.coursera.org/professional-certificates/google-it-automation). Embora o curso não esteja diretamente relacionado ao ML ou à IA, é definitivamente um bom curso de fundamentos para deseja tornar-se proficiente com a linguagem Python. Bolsas de estudo também estão disponíveis.

\\
Aqui está outra [série de vídeos](https://www.youtube.com/watch?v=fMqL5vckiU0&list=PL-wATfeyAMNrtbkCNsLcpoAyBBRJZVlnf) promissora chamada "Deep Learning (for Audio) with Python" com foco no uso de Tensorflow e Python para construção de aplicações relacionadas a áudio/música, e alavancando o uso de deep learning.

\\
![](https://cdn-images-1.medium.com/max/800/1*N5d8-1La8khZ6-XwHL68sg.png)

[*fonte*](https://www.youtube.com/watch?v=fMqL5vckiU0&list=PL-wATfeyAMNrtbkCNsLcpoAyBBRJZVlnf)

\\
Andrew Trask lançou um conjunto de [notebooks com tutoriais passo-a-passo](https://c4ejournal.net/2020/01/16/zack-lipton-fairness-interpretability-and-the-dangers-of-solutionism-ethics-of-ai-in-context2020-c4ej-2/) para alcançar deep learning de forma descentralizada com objetivo de preservação da privacidade. Todos os notebooks contêm implementações PyTorch e são destinados a iniciantes.

\\
***Estado da arte em Deep Learning***

\\
Confira esta [palestra em vídeo](https://www.youtube.com/watch?v=0VH1Lim8gL8) de Lex Fridman sobre a recente pesquisa e desenvolvimento em Deep Learning. Ele fala sobre os principais avanços em tópicos como perceptrons, redes neurais, backpropagation, CNN, deep learning, ImageNet, GANs, AlphaGo, e Transformers. Esta palestra faz parte da Série de Deep Learning do MIT.

\\
***Online learning e pesquisa***

\\
Há muitas e grandes iniciativas online para colaboração tanto em pesquisa quanto em aprendizagem. Os meus favoritos são a sessão de leitura de matemática [MLT's](https://twitter.com/__MLT__) e este novo esforço de colaboração distribuída em pesquisa AI iniciado por [nightai](https://www.nightai.co/). Recentemente, tem havido muitos grupos de estudo como este online e estes grupos de estudos são ótimas maneiras de mergulhar no mundo do ML.

\\
***Perspectivas em aprendizagem por reforço***

\\
Aprenda com a Dra. Katja Hofmann os principais conceitos e métodos de aprendizagem por reforço nesta [série de webinars](https://note.microsoft.com/MSR-Webinar-RL-Algorithm-to-Adoption-Registration-Live.html?wt.mc_id=twitter_MSR-WBNR_post_v3).

# Menções honrosas ⭐️
Confira [esta implementação limpa e auto-contida em PyTorch](https://gist.github.com/y0ast/d91d09565462125a1eb75acc65da1469) da ResNet-18 aplicada ao CIFAR-10, que atinge ~94% de precisão.

\\
PyTorch 1.4 é lançado! Confira as notas de lançamento [aqui](https://github.com/pytorch/pytorch/releases/tag/v1.4.0).

\\
Elona Shatri escreveu este excelente [resumo](_COPY11@e.shatri1/what-is-optical-music-recognition-6515d8a53e01) sobre como ela pretende abordar o reconhecimento da música óptica usando deep learning.

\\
O título para este post no blog é auto-explicativo: ["The Case for Bayesian Deep Learning"](https://cims.nyu.edu/~andrewgw/caseforbdl/)".

\\
Chris Said compartilha sua [experiência](https://chris-said.io/2020/01/10/optimizing-sample-sizes-in-ab-testing-part-I/) na otimização de tamanhos de amostras para testes A/B, uma parte importante em se tratando de Data Science de forma aplicada. Os tópicos incluem os custos e benefícios de grandes tamanhos de amostras e melhores práticas para os profissionais.

\\
Neural Data Server (NDS) is a dedicated search engine for obtaining transfer learning data. Read about the method [here](https://arxiv.org/abs/2001.02799) and the service [here](http://aidemos.cs.toronto.edu/nds/).

O Neural Data Server (NDS) é um mecanismo de busca dedicado à obtenção de dados via _transfer learning_. Leia sobre o método [aqui](https://arxiv.org/abs/2001.02799) e o serviço [aqui](http://aidemos.cs.toronto.edu/nds/).
