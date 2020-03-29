---
layout: post
title: "NLP Newsletter #4 [FR]: PyTorch3D, DeepSpeed, Turing-NLG, Question Answering Benchmarks, Hydra, Sparse Neural Networks,…"
author: lbourdois
excerpt: ""
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_4.png
---

![](https://cdn-images-1.medium.com/max/1200/1*3vNKhz6K-oGQ8aLi3mo84Q.png)

# Publications 📙
***Turing-NLG: Un modèle linguistique de 17 milliards de paramètres par Microsoft***

\\
Turing Natural Language Generation (T-NLG) est un modèle de 17 milliards de paramètres [proposé](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/) par les chercheurs en IA de Microsoft. Il est à ce jour, le plus grand modèle de langage connu (illustré dans la figure ci-dessous) et est basé sur un Transformer à 78 couches qui surpasse les résultats précédents (détenus par Megatron-LM de NVIDIA) sur la perplexité de WikiText-103. Il a été testé sur des tâches telles que la réponse à des questions et le résumé abstrait. Le modèle est rendu possible par une librairie d'optimisation de l’entraînement appelée DeepSpeed avec ZeRO, qui est également présentée plus loin dans cette newsletter.

\\
![](https://cdn-images-1.medium.com/max/800/0*CAZm7uj8EaupnvnJ.png)

[*source*](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/)

\\
***Neural based Dependency Parsing***

\\
Miryam de Lhoneux a publié sa thèse de doctorat intitulée "[Linguistically Informed Neural Dependency Parsing for Typologically Diverse Languages](http://uu.diva-portal.org/smash/record.jsf?pid=diva2%3A1357373&dswid=7905)". Ce travail porte sur l'utilisation d'approches neurales pour l'[analyse des dépendances](http://nlpprogress.com/english/dependency_parsing.html) dans les langues typologiquement diverses (c'est-à-dire les langues qui construisent et expriment le sens de manière structurellement différente). Ce travail rapporte que les RNN et les couches récursives pourraient être utiles pour l'incorporation dans les parsers car elles aident à informer les modèles avec des connaissances linguistiques importantes nécessaires pour l'analyse. D'autres idées comprennent l'utilisation de l'analyse syntaxique polyglotte et des stratégies de partage de paramètres pour l'analyse syntaxique dans des langues apparentées et non apparentées.

\\
***Extraction d'informations de bout en bout dans le cloud avec BERT***

\\
Une équipe de chercheurs a publié un [article](https://arxiv.org/abs/2002.01861) décrivant comment des modèles de Transformers comme BERT peuvent aider à l'extraction d'informations de bout en bout dans des documents commerciaux spécifiques à un domaine, tels que les dépôts réglementaires et les contrats de location de propriété. Non seulement ce type de travail peut aider à optimiser les opérations commerciales, mais il montre également l'applicabilité et l'efficacité des modèles basés sur BERT sur des régimes avec très peu de données annotées. Une application, et ses détails de mise en œuvre, qui fonctionne sur le cloud est également proposée (voir figure ci-dessous).

\\
![](https://cdn-images-1.medium.com/max/800/1*KqViSLhP0otleDY-XFy3Bg.png)

[*source*](https://arxiv.org/abs/2002.01861)

\\
***Question Answering Benchmark***

\\
[Wolfson et al. (2020)](https://arxiv.org/abs/2001.11770v1) ont publié un benchmark pour la compréhension des questions ainsi qu’une méthode pour décomposer une question qui est nécessaire pour calculer une réponse appropriée. Ils s'appuient sur le crowdsourcing pour annoter les étapes nécessaires à la décomposition des questions. Pour montrer la faisabilité et l'applicabilité de l'approche, ils améliorent la réponse aux questions du domaine ouvert en utilisant l'ensemble de données HotPotQA.

\\
![](https://cdn-images-1.medium.com/max/800/1*AztG-Inqt6LGQ87lSufRcw.png)

 [*source*](https://arxiv.org/pdf/2001.11770v1.pdf)

\\
***Données radioactives : le traçage par l’entraînement***

\\
Les chercheurs de Facebook AI ont récemment publié un [travail](https://ai.facebook.com/blog/using-radioactive-data-to-detect-if-a-data-set-was-used-for-training/) qui vise à marquer les images (appelées données radioactives) afin de vérifier si un jeu de données particulier a été utilisé pour l'entraînement d’un modèle de ML. Ils ont découvert qu'il est possible d'utiliser un marqueur intelligent qui déplace les caractéristiques dans une direction, que le modèle utilise pour aider à détecter l'utilisation de données radioactives même si seulement 1 % des données d'entraînement sont radioactives. C’est un défi car tout changement dans les données peut potentiellement dégrader la précision du modèle. Selon les auteurs, ce travail peut « aider les chercheurs et les ingénieurs à savoir quel jeu de données a été utilisé pour entraîner un modèle, afin de mieux comprendre comment les différents ensembles de données affectent les performances des différents réseaux neuronaux ». Cette approche semble importante pour les applications critiques de ML. Consultez le document complet [ici](https://arxiv.org/pdf/2002.00937.pdf).


\\
***REALM: Retrieval-Augmented Language Model Pre-Training***


\\
[REALM](https://kentonl.com/pub/gltpc.2020.pdf) est une approche d'extraction à grande échelle qui utilise un corpus de connaissances textuelles pour pré-entraîner un modèle de langue de manière non supervisée. Les tâches abordées et évaluées à l'aide de REALM comprennent des questions ouvertes répondant à des critères de référence. Outre l'amélioration de la précision du modèle, les autres avantages comprennent les composantes de modularité et d'interprétabilité.

\\
![](https://cdn-images-1.medium.com/max/800/1*MJO-yzCwsB5ydKGz7hKHVA.png)

[*source*](https://kentonl.com/pub/gltpc.2020.pdf)

# Créativité et société 🎨

***Permettre la présentation à distance de documents et d'affiches lors de conférences scientifiques***

\\
La semaine dernière, une [pétition](https://www.change.org/p/organizers-of-data-science-and-machine-learning-conferences-neurips-icml-aistats-iclr-uai-allow-remote-paper-poster-presentations-at-conferences) a été lancée pour permettre la présentation à distance de documents et d'affiches lors de conférences scientifiques comme celles liées au ML. Il semble que Yoshua Bengio, plaide pour que les gens aillent signer la pétition. Il l'a clairement indiqué dans son nouveau [blog](https://yoshuabengio.org/2020/02/10/fusce-risus/).


\\
***Défi de l'abstraction et du raisonnement***

\\
François Chollet a récemment mis en ligne un [concours Kaggle](https://www.kaggle.com/c/abstraction-and-reasoning-challenge/overview) où il a publié le Corpus d'abstraction et de raisonnement (ARC). Il vise à encourager les utilisateurs à créer des systèmes d'IA capables de résoudre des tâches de raisonnement auxquelles ils n'ont jamais été exposés. L'espoir est de commencer à construire des systèmes d'IA plus robustes, capables de résoudre mieux et rapidement de nouveaux problèmes par eux-mêmes, ce qui pourrait aider à résoudre les applications du monde réel les plus difficiles, comme l'amélioration des voitures autonomes.

\\
***Publications de ML et NLP en 2019***

\\
Marek Rei publie son [analyse annuelle]( https://www.marekrei.com/blog/ml-and-nlp-publications-in-2019/) sur les statistiques en lien avec l'apprentissage machine et le NLP pour l’année 2019. Les conférences incluses dans l'analyse sont ACL, EMNLP, NAACL, EACL, COLING, TACL, CL, CoNLL, NeurIPS, ICML, ICLR, et AAAI.

\\
***La croissance d’automates cellulaires neuronaux***

\\
La morphogenèse est un processus d'auto-organisation par lequel certaines créatures comme les salamandres peuvent se régénérer ou réparer des dommages corporels. Ce processus est robuste aux perturbations et de nature adaptative. Inspirés par ce phénomène biologique et par le besoin de mieux comprendre le processus, les chercheurs ont publié un [article](https://distill.pub/2020/growing-ca/) intitulé "Growing Neural Cellular Automata", qui adopte un modèle différenciable pour la morphogenèse visant à reproduire les comportements et les propriétés des systèmes d'autoréparation. L'espoir est de pouvoir construire des machines autoréparatrices qui possèdent la même robustesse et plasticité que la vie biologique. En outre, cela permettrait de mieux comprendre le processus de régénération lui-même. Les applications qui peuvent en bénéficier comprennent la médecine régénératrice et la modélisation des systèmes sociaux et biologiques.

\\
![](https://cdn-images-1.medium.com/max/800/1*2p62h1RaHD6d11LX8olnTA.png)

[*source*](https://distill.pub/2020/growing-ca/)

\\
***Visualiser l'attention des Transformers***

\\
Hendrik Strobelt a partagé ce [repertoire](https://github.com/SIDN-IAP/attnvis) qui montre comment construire rapidement une visualisation interactive simple de l'attention d’un Transformer à travers une application web en utilisant la bibliothèque HuggingFace et d3.js.

\\
***SketchTransfer : Une nouvelle tâche stimulante pour explorer l'invariance des détails et les abstractions apprises par les réseaux***

\\
[SketchTransfer](https://arxiv.org/pdf/1912.11570.pdf) propose une nouvelle tâche pour tester la capacité des réseaux neuronaux à supporter l'invariance en présence/absence de détails. On a longtemps débattu du fait que les réseaux ne peuvent pas se généraliser à des variations qui n'ont pas encore été observées pendant l’entraînement, comme par exemple traiter les détails visuels manquants lorsqu'ils regardent des dessins animés. Le document examine et publie un ensemble de données pour aider les chercheurs à étudier attentivement le problème de « l'invariance des détails » en fournissant des croquis non étiquetés et des exemples étiquetés d'images réelles.

\\
![](https://cdn-images-1.medium.com/max/800/1*jdYuMoHiu2yya5rHzZyjwQ.png)

[*source*](https://arxiv.org/pdf/1912.11570.pdf)


# Outils et jeux de données ⚙️

***DeepSpeed + ZeRO***

\\
Microsoft a dévoilée une librairie d'optimisation pour l’entrainement appelée DeepSpeed. Elle est compatible avec PyTorch et peut permettre l’entrainement d'un modèle de 100 milliards de paramètres. La librairie se concentre sur quatre aspects importants de l’entrainement d'un modèle : l'échelle, la vitesse, le coût et la convivialité. DeepSpeed a été [lancé](https://www.microsoft.com/en-us/research/blog/zero-deepspeed-new-system-optimizations-enable-training-models-with-over-100-billion-parameters/) en même temps que ZeRO. ZeRO est une technologie d'optimisation de la mémoire qui permet de faire du deep learning distribué à grande échelle sur GPU tout en améliorant le débit de trois à cinq fois plus que le meilleur système actuel.

\\
![](https://cdn-images-1.medium.com/max/800/0*MXDI1f3cSBrY5w2g.gif)

[*source*](https://www.microsoft.com/en-us/research/blog/zero-deepspeed-new-system-optimizations-enable-training-models-with-over-100-billion-parameters/)

\\
***Une librairie pour mener des recherches rapides et efficaces sur le DL en 3D***

\\
[PyTorch3D](https://ai.facebook.com/blog/-introducing-pytorch3d-an-open-source-library-for-3d-deep-learning/) est une boîte à outils open-source pour la recherche sur le DL en 3D. La librairie consiste en des implémentations rapides et optimisées d'opérateurs 3D et de fonctions de perte fréquemment utilisés. Elle est également dotée d'un moteur de rendu modulaire et différenciable qui permet de mener des recherches sur des entrées 3D complexes et de faire des prévisions 3D de haute qualité.

\\
![](https://cdn-images-1.medium.com/max/800/1*VbspKMmPBUsgpdnIkd5jYA.png)

[*source*](https://ai.facebook.com/blog/-introducing-pytorch3d-an-open-source-library-for-3d-deep-learning/)

\\
***Gestion de la configuration de projets de ML***

\\
Hydra est un outil pour gérer plus efficacement les projets de ML complexes. Il est destiné à aider les chercheurs de PyTorch en offrant une réutilisation fonctionnelle des configurations. Son principal avantage est qu'il permet au programmeur de gérer la configuration comme du code de composition, ce qui signifie que le fichier de configuration peut être facilement écrasé. Hydra peut également aider à gérer automatiquement le répertoire de travail des résultats de votre projet de ML, ce qui est utile lorsque vous avez besoin de sauvegarder et d'accéder aux résultats de plusieurs expériences pour des travaux multiples. Pour en savoir plus, cliquez [ici](https://medium.com/pytorch/hydra-a-fresh-look-at-configuration-for-machine-learning-projects-50583186b710).

\\
***Une boîte à outils pour l'inférence causale avec les réseaux bayésiens***

\\
[CausalNex](https://causalnex.readthedocs.io/en/latest/01_introduction/01_introduction.html) est une boîte à outils pour "l'inférence causale avec les réseaux bayésiens". L'outil vise à combiner l'apprentissage machine et le raisonnement causal pour découvrir des relations structurelles dans les données. Les auteurs ont également préparé un guide d'introduction sur le pourquoi et le comment de l'inférence causale avec les réseaux bayésiens en utilisant la librairie Python proposée.

\\
![](https://cdn-images-1.medium.com/max/800/1*EYwKhdnscR7ZLuNkTqCS2Q.png)

[*source*](https://causalnex.readthedocs.io/en/latest/01_introduction/01_introduction.html)

\\
***Google Colab Pro est maintenant disponible***

\\
Google Colab propose désormais une édition Pro, qui offre des avantages tels qu'un accès exclusif à des GPU et TPU plus rapides, des durées d'exécution plus longues et plus de mémoire.


\\
***TyDi QA: Un benchmark pour le Question/Anwsering multilingues***

\\
Google AI publie [TyDi QA](https://ai.googleblog.com/2020/02/tydi-qa-multilingual-question-answering.html), un ensemble de données multilingues qui peut encourager les chercheurs à répondre à des questions dans des langues plus typologiquement diverses. C’est à dire qui construisent et expriment le sens de différentes manières. L'idée est de motiver les chercheurs à construire des modèles plus robustes sur des langues typologiquement éloignées, telles que l'arabe, le bengali, le coréen, le russe, le télougou et le thaï, afin de généraliser à encore plus de langues.

\\
![](https://cdn-images-1.medium.com/max/800/1*1dZv5you3jigdrQ2uAKzUw.png)

[*source*](https://ai.googleblog.com/2020/02/tydi-qa-multilingual-question-answering.html)

\\
***Question Answering pour Node.js***

\\
Hugging Face publie une [librairie](https://github.com/huggingface/node-question-answering) de questions/réponses basée sur DistilBERT. Ce modèle peut fonctionner en production en utilisant Node.js avec seulement 3 lignes de code. Le modèle tire parti de la mise en œuvre rapide de Tokenizers, et de TensorFlow.js (une bibliothèque populaire pour l'utilisation de modèles d'apprentissage machine avec Javascript).

# Ethique en IA 🚨

***Identifier les biais subjectifs dans les textes***

\\
Ce [podcast](https://podcasts.apple.com/us/podcast/will-ai-help-identify-bias-or-perpetuate-it-with-diyi-yang/id1435564422?i=1000464141922) présente Diyi Yang, chercheur en sciences sociales computationnelles, qui explique comment les systèmes d'IA peuvent aider à identifier les biais subjectifs dans les informations textuelles. Il s'agit d'un domaine de recherche important impliquant les systèmes d'IA et de NLP. En particulier lorsque nous discutons de la consommation de médias textuels tels que les news qui peuvent être facilement encadrés pour biaiser les consommateurs alors qu'en réalité ils devraient viser à être plus objectifs. Du point de vue de l'application, il devient essentiel d'identifier automatiquement le biais subjectif présent dans les médias textuels afin d'aider les consommateurs à devenir plus conscients du contenu qu'ils consomment. L'épisode traite également de la manière dont l'IA peut également perpétuer le biais.

\\
***Intelligence artificielle, valeurs et alignement***

\\
L'essor des systèmes d'IA et la manière dont ils s’alignent sur les valeurs humaines est un domaine de recherche actif qui implique l'éthique dans les systèmes d'IA. DeepMind a récemment publié un [papier](https://deepmind.com/research/publications/Artificial-Intelligence-Values-and-Alignment) qui examine plus en profondeur les questions philosophiques entourant l'alignement de l'IA. Le rapport se concentre sur deux parties :  technique (c'est-à-dire comment coder les valeurs qui rendent les résultats des agents d'IA fiables) et normative (quels principes seraient justes à coder dans l'IA). Le document préconise une approche fondée sur des principes visant à préserver à préserver un traitement équitable malgré la différence de croyances et d'opinions.

\\
***Sur l'audit des systèmes d'IA***

\\
VentureBeat rapporte que Google Researchers, en collaboration avec d'autres groupes, a créé un framework appelé SMACTR qui permet aux ingénieurs de vérifier les systèmes d'IA. La raison de ce travail est de combler le fossé de responsabilité qui existe avec les systèmes d'IA actuels qui sont mis dans la nature pour être utilisés par les consommateurs. Pour plus d’informations, lire les deux documents suivants :  [ici](https://venturebeat.com/2020/01/30/google-researchers-release-audit-framework-to-close-ai-accountability-gap/) et [ici](https://dl.acm.org/doi/abs/10.1145/3351095.3372873).

# Articles et Blog ✍️

***La distillation de modèle en NLP***

\\
Dans un [podcast](https://soundcloud.com/nlp-highlights/104-model-distillation-with-victor-sanh-and-thomas-wolf) de NLP Highlights, Thomas Wolf et Victor Sanh parlent de la distillation de modèles et de la façon dont elle peut être utilisée comme une approche réalisable pour comprimer de grands modèles comme BERT. Ce concept est discuté plus en détail dans la méthode qu'ils proposent, appelée [DistilBERT](https://arxiv.org/abs/1910.01108), dans laquelle ils construisent des modèles plus petits (basés sur la même architecture qu'un modèle plus grand) pour essayer d'imiter le comportement du modèle plus grand. En substance, le petit modèle (l'étudiant) essaie de s'adapter à la distribution de probabilité de l'enseignant.

\\
***BERT, ELMo, & GPT-2: Dans quelle mesure les représentations contextuelles des mots sont-elles contextualisées ? ***

\\
On a beaucoup parlé du succès des méthodes contextualisées comme BERT pour aborder une grande variété de tâches complexes de NLP. Dans cet [article](https://kawine.github.io/blog/nlp/2020/02/03/contextual.html), Kawin Ethayarajh tente de répondre à la question qui consiste à savoir comment sont contextualisés les mots dans les modèles comme BERT, ELMo et le GPT-2. Les sujets abordés comprennent les mesures de la contextualité, la spécificité du contexte et les comparaisons entre les embeddings statiques et les représentations contextualisées.

\\
![](https://cdn-images-1.medium.com/max/800/0*70aIv1Fkkz4rnHgQ.png)

[*source*](https://kawine.github.io/blog/nlp/2020/02/03/contextual.html)

\\
***Sparsity in Neural Networks***

\\
François Lagunas, a écrit cet [article Medium](https://medium.com/huggingface/is-the-future-of-neural-networks-sparse-an-introduction-1-n-d03923ecbd70) pour discuter de son optimisme quant à l'adoption de tenseurs clairsemés dans les modèles de réseaux de neurones. L'espoir est d'utiliser une forme de rareté pour réduire la taille des modèles actuels qui, à un moment donné, deviennent peu pratiques en raison de leur taille et de leur vitesse. Ce concept pourrait être intéressant à explorer en ML en raison de la taille même des modèles actuels comme les Transformers. Cependant, les détails de mise en œuvre ne sont pas aussi clairs du point de vue des outils de développement disponibles, et c'est quelque chose sur lequel la communauté travaille déjà.

\\
***Entraîner votre propre modèle linguistique***

\\
Si vous souhaitez apprendre à entrainer un modèle de zéro, consultez ce [tutoriel](https://huggingface.co/blog/how-to-train) d’Hugging Face. Ils utilisent évidemment leurs propres bibliothèques Transformers et Tokenizers pour entraîner le modèle.


\\
***Tokenizers: Comment les machines lisent***

\\
Cathal Horan a publié un [article](https://blog.floydhub.com/tokenization-nlp/) sur la manière dont les modèles de NLP les plus récents utilisent les tokenizers. Il explique également pourquoi la tokenisation est un domaine de recherche actif, passionnant et important. L'article vous montre même comment entraîner vos propres tokenizers en utilisant des méthodes de tokenisation comme SentencePiece et WordPiece.

\\
![](https://cdn-images-1.medium.com/max/800/1*Vkjw5n9Sz0Was43haVNJMg.png)

[*source*](https://blog.floydhub.com/tokenization-nlp/%27)


# Education 🎓

***ML à l'université d'Amsterdam***

\\
Vous pouvez désormais suivre en ligne le [cours d'apprentissage machine 2020 MLVU](https://mlvu.github.io/), qui comprend des diapositives, des [vidéos](https://www.youtube.com/watch?v=excCZSTJEPs&feature=youtu.be) et le programme. Il s'agit d'une introduction au ML, mais il comporte également d'autres sujets liés à l'apprentissage approfondi, tels que les VAE et les GAN.


\\
![](https://cdn-images-1.medium.com/max/800/1*zFpU2rQL5Fby7X3boJyQNg.png)

[*source*](https://mlvu.github.io/)

\\
***Ressources mathématiques pour le ML***

\\
Suzana Ilić et le Machine Learning Tokyo (MLT) ont fait un travail remarquable en termes de démocratisation de l'éducation au ML. Par exemple, consultez ce [répertoire](https://github.com/Machine-Learning-Tokyo/Math_resources) qui présente une collection de ressources en ligne gratuites pour apprendre les fondements des concepts mathématiques utilisés en ML.

\\
***Introduction au Deep Learning***

\\
Suivez le cours "Introduction to Deep Learning" du MIT sur ce [site](http://introtodeeplearning.com/). De nouveaux cours seront publiés chaque semaine et toutes les diapositives, vidéos et codes seront publiés.

\\
***Deep Learning avec PyTorch***

\\
Alfredo Canziani a publié les diapositives et les notebooks pour son mini-cours sur l'apprentissage profond avec PyTorch. Le dépôt contient également un [site web complémentaire](https://atcold.github.io/pytorch-Deep-Learning/) qui comprend des descriptions textuelles des concepts enseignés dans le cours.

\\
***Missing Semester of Your CS***

\\
Le "[Missing Semester of Your CS](https://missing.csail.mit.edu/)" est un cours en ligne pouvant être utile aux spécialistes des données ayant une formation autre que celle du développement. Il comprend des sujets tels que les outils shell, les scripts et le contrôle de version. Le cours a été publié par des membres du corps enseignant du MIT.

\\
![](https://cdn-images-1.medium.com/max/800/1*weUnTXxmHxYf-B2DDaslvw.png)

[*source*](https://missing.csail.mit.edu/2020/shell-tools/)

\\
***Deep Learning avancé***

\\
La CMU a publié les diapositives et le programme du cours "[Advanced Deep Learning](https://andrejristeski.github.io/10707-S20/syllabus.html)" qui comprend des sujets tels que les modèles autorégressifs, les modèles générateurs et l'apprentissage autosurveillé/prédictif. Le cours s'adresse aux étudiants de master ou de doctorat ayant une formation avancée en ML.

# Mentions spéciales ⭐️

Xu et ses collaborateurs (2020) ont proposé une [méthode]( https://arxiv.org/abs/2002.02925) pour remplacer et compresser progressivement un modèle BERT en le divisant en ses composantes d'origine. Le modèle proposé surpasse les autres approches de distillation sur le référentiel GLUE.

\\
Le cours "[Introduction à l'apprentissage machine](https://compstat-lmu.github.io/lecture_i2ml/index.html)" couvre les bases du ML, la régression supervisée, les forêts aléatoires, le tuning des paramètres et bien d'autres sujets fondamentaux du ML.

\\
Le modèle grec de BERT ([GreekBERT](https://huggingface.co/nlpaueb/bert-base-greek-uncased-v1)) est maintenant disponible sur Transformers.


\\
Jeremy Howard publie un [article](https://arxiv.org/abs/2002.04688) décrivant la librairie fastai. Il s'agit d'une lecture recommandée aux développeurs de logiciels qui travaillent à la création et à l'amélioration des librairies d'apprentissage profond et de ML.

\\
Deeplearning.ai complète la publication des quatre cours de TensorFlow : [Data and Deployment Specialization](https://www.coursera.org/specializations/tensorflow-data-and-deployment). Cette spécialisation vise principalement à apprendre aux développeurs comment déployer efficacement des modèles dans différents scénarios et utiliser les données de manière intéressante.

\\
Sebastian Raschka a récemment publié un [article](https://arxiv.org/abs/2002.04803) intitulé "Machine Learning in Python" : Principaux développements et tendances technologiques en matière de science des données, d'apprentissage automatique et d'intelligence artificielle". Ce document est un examen complet du paysage des outils d'apprentissage machine. Il permet de comprendre les avantages de certaines librairies et les concepts utilisés dans l'ingénierie ML. En outre, un mot sur l'avenir des bibliothèques d'apprentissage machine basées sur Python est fourni.

----------

Vous pouvez retrouver la précédente newsletter [ici](https://dair.ai/NLP_Newsletter_-3_-FR/)

\\
Si vous avez des jeux de données, des projets, des articles de blog, des tutoriels ou des documents que vous souhaitez partager dans la prochaine édition de la newletter, n'hésitez pas à me contacter à ellfae@gmail.com ou par message sur [Twitter](https://twitter.com/omarsar0).

\\
[Abonnez-vous]( https://dair.ai/newsletter/) pour recevoir les prochains numéros dans votre boîte mail.
