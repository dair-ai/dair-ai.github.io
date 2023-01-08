---
layout: post
title: "Boletín informativo NLP #5 [ES]: GPT-2 Explicado, Entendiendo ‘Self-Distillation’, Haiku, GANILLA, Sparkwiki, Ética en el NLP, Torchmeta,..."
author: naraquev
modified:
comments: true
excerpt: ""
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_5.png
---


![](https://cdn-images-1.medium.com/max/1200/1*YIhZsPaiBFkRMMWo5FAhGw.png)

\\
Post Original en Ingles: [https://dair.ai/NLP_Newsletter_The_Annotated_GPT-2,_Understanding/](https://dair.ai/NLP_Newsletter_The_Annotated_GPT-2,_Understanding/)

\\
Primero que todo, no puedo agradecerles lo suficiente a todos por el increible animo y soporte para continuar con el boletín informativo de NLP. Este esfuerzo requiere una investigación y edición tediosa, la cual encuentro gratificante y útil para proveer el mejor contenido. Espero que lo estén disfrutando tanto como yo.

\\
[Suscríbete](https://dair.ai/newsletter/) al Boletín Informativo de NLP para recibir futuras ediciones en tu email. Este boletin lo desarrolla Elvis Saravia, editor de dair.ai

# Publicaciones📙

***Un entendimiento teórico del self-distillation***

\\
En el contexto del Deep Learning, self-distillation es el proceso de transferir conocimiento de una arquitectura a otra arquitectura idéntica. Las predicciones del modelo original son alimentadas como valores objetivo al otro modelo mientras se entrena. Además de tener propiedades deseables (como reducir el tamaño del modelo) resultados empíricos demuestran que esta aproximación trabaja bastante bien en sets de datos del tipo held-out. Un grupo de investigadores recientemente publicó una investigación que provee un análisis teórico con foco en entender mejor qué está pasando en el proceso de destilación del conocimiento y por que es efectivo. Los resultados muestran que unas pocas rondas de self-distillation amplifica la regularización ([limitando progresivamente el número de funciones básicas que representan la solución](https://twitter.com/TheGradient/status/1228132843630387201?s=20)) lo que tiende a reducir el over-fitting. (Lee la investigación completa [aquí](https://arxiv.org/abs/2002.05715))

\\
![](https://cdn-images-1.medium.com/max/800/1*nWYO71awfooL4MrGK-tFww.png)

\\
*Traducción: Figura 1. Ilustración esquemática del proceso de self-distillation por dos iteraciones. Fuente: [https://arxiv.org/abs/2002.05715](https://arxiv.org/abs/2002.05715)*

\\
***Los 2010: La década del Deep Learning / Mirada al 2020***

\\
[Jürgen Schmidhuber,](http://people.idsia.ch/~juergen/) un pionero en la inteligencia artificial, publicó recientemente un [artículo](http://people.idsia.ch/~juergen/2010s-our-decade-of-deep-learning.html) titulado “Foco en proveer un resumen histórico del Deep Learning desde el 2010”. Algunos de los temas incluyen LSTMs, redes neuronales feedforward, GANs, DeepRL, Meta-Learning, World Models, distillings NNs, Attention Learning, etc. El artículo concluye con una mirada al 2020, donde llama la atención a temas como la privacidad y los mercados de datos.

\\
***Utilizando Redes Neuronales para resolver ecuaciones matemáticas avanzadas.***

\\
Investigadores de Facebook AI publicaron una [investigación](https://arxiv.org/abs/1912.01412) que dice proponer un modelo entrenado en problemas matemáticos y sus soluciones para aprender a predecir posibles soluciones en problemas cómo resolver integrales matematicas. El acercamiento está basado en un novedoso framework similar al usado en neural machine translation donde una expresión matemática es representada como una especie de lenguaje y la solución es tratada como su traducción. Por esto, en vez de que el resultado sea una traducción, es la solución al problema matematico. Con esto, los investigadores concluyen que las redes neuronales profundas no solo son buenas para el razonamiento simbólico sino también para tareas más diversas.

\\
![](https://cdn-images-1.medium.com/max/800/1*P_JtxoC8pYkXuXCp3e3QeQ.png)

*Ecuaciones incluidas como entrada con su correspondiente solución. [Fuente](https://ai.facebook.com/blog/using-neural-networks-to-solve-advanced-mathematics-equations/)*

# Creatividad y Sociedad 🎨

***IA para el descubrimiento científico***

\\
Mattew Hutson [reporta](https://www.sciencemag.org/news/2020/02/models-galaxies-atoms-simple-ai-shortcuts-speed-simulations-billions-times) cómo la inteligencia artificial (IA) puede ser usada para producir emuladores con la capacidad de modelar fenómenos naturales complejos. Estos modelos pueden a su vez apuntar a diferentes tipos de descubrimientos científicos. El desafío al construir estos emuladores es que necesitan una gran cantidad de datos y una búsqueda extensiva de parámetros. Una [investigación](https://arxiv.org/abs/2001.08055) reciente propone una técnica llamada DENSE, basada en [neural architecture search](https://en.wikipedia.org/wiki/Neural_architecture_search) para construir emuladores precisos utilizando una cantidad de datos de entrenamiento limitada. Los investigadores hicieron distintas pruebas construyendo simuladores para caso como astrofísica, ciencia climática, energía de fusión, etc.

\\
***Mejorando la traducción imagen-a-ilustración***

\\
GANILLA es una aproximación que propone el uso de las GANs para mejorar la transferencia de estilo y contenido en la tarea de convertir una imagen en una ilustración. En particular, un modelo para [imagen-a-ilustración](https://paperswithcode.com/task/image-to-image-translation) es propuesto (con una red generadora mejorada) y evaluado basado en un nuevo framework para evaluación cuantitativa que considera tanto el contenido como el estilo de la imagen generada. La novedad de esta investigación es en la red generadora propuesta que considera un balance entre estilo y contenido que anteriores intentos fallaron en alcanzar. El código y modelo pre entrenado están disponibles en [línea](https://github.com/giddyyupp/ganilla). [Aquí](https://arxiv.org/abs/2002.05638) se puede encontrar la investigación completa.

\\
![](https://cdn-images-1.medium.com/max/800/1*l_B4vfaHVkXDwzM7SldiqQ.png)

*Traducción: Ejemplos de salida de CycleGAN, DualGAN, y nuestro método (GANILLA) utilizando diferentes estilos. CycleGAN y GANILLA generan imágenes en un estilo de ilustración, pero DualGAN falla en transferir el estilo. Sin embargo, CycleGAN falle en preservar el contenido de la imagen original, por ejemplo, aleatoriamente coloca caras de animales en el aire. Nuestro método preserva contenido así como también transfiere el estilo de la imagen original.*

\\
***Andrew Ng habla sobre su interés en self-supervised learning***

\\
Andrew Ng, fundador de [deeplearning.ai](http://deeplearning.ai/), participa en el podcast Artificial Inteligence de Lex Friedman para [hablar](https://www.youtube.com/watch?v=0jspaMLxBig) de diferentes temas como sus comienzos en el ML, el futuro del AI y la educación, recomendaciones de uso para ML, sus metas personales y a cuáles técnicas de ML prestar atención en el 2020.

\\
Andrew tambien explico por que está muy emocionado sobre el self-supervised representation learning. [Self-supervised learning](https://lilianweng.github.io/lil-log/2019/11/10/self-supervised-learning.html) se trata sobre enfocar un problema de aprendizaje que intenta obtener la supervisión de los datos en sí mismos para hacer uso de grandes cantidades de datos no clasificados, escenario más común que datos limpios y clasificados. Las representaciones aprendidas, opuesto al rendimiento de la tarea, son importantes y pueden ser usadas en tareas más adelante, similar a lo que está siendo usado en modelos de lenguaje natural como [BERT](https://lilianweng.github.io/lil-log/2019/01/31/generalized-language-models.html#bert).

\\
Hay mucho interés en usar el self-supervised learning para aprender representaciones visuales generales que hagan al modelo más preciso en situaciones de bajos recursos. Por ejemplo, un nuevo método llamado [SimCLR](https://arxiv.org/abs/2002.05709) (Dirigido por Geoffrey Hinton) propone un framework para el *constrastive self-supervised learning* de representaciones visuales para mejorar el resultado de la clasificación de imágenes en diferentes contextos como el *transfer learning* y el *semi-supervised learning*.

\\
![](https://cdn-images-1.medium.com/max/800/1*8zLzHFCyM3goc9y7KApHfg.png)

*Traducción: ImageNet top-1 accuracy de clasificadores lineales entrenados en representaciones aprendidas con diferentes métodos de auto-aprendizaje (pre entrenados en ImageNet). La cruz gris indica un modelo ResNet-50 supervisado. Nuestro método, SimCLR, es mostrado en negrita.*

# Herramientas y Set de Datos ⚙️

***Librerías JAX***

\\
[JAX](https://github.com/google/jax) es una nueva librería que combina NumPy y diferenciación automática para realizar investigación de alto rendimiento en ML. Para simplificar procesos para construir redes neuronales usando JAX, DeepMind lanzó [Haiku](https://github.com/deepmind/dm-haiku) y [RLax](https://github.com/deepmind/rlax). RLAx simplifica la implementación de agentes de reinforcement learning y Haiku simplifica la construcción de redes neuronales utilizando paradigmas familiares de programación orientada a objetos.

\\
***Una herramienta para procesar datos de Wikipedia***

\\
[Spakwiki](https://github.com/epfl-lts2/sparkwiki) es una herramienta para procesar datos de Wikipedia. Este lanzamiento es parte de muchos esfuerzos para permitir análisis interesantes de comportamiento como [capturar tendencias y sesgos de lenguaje en ediciones de distinto idioma en Wikipedia](https://arxiv.org/abs/2002.06885). Los autores descubrieron que independientemente del lenguaje, el comportamiento de búsqueda de los usuarios de Wikipedia es muy parecido en categorías como películas, música y deportes pero que las diferencias se vuelven más aparentes con eventos locales y particularidades de cultura.

\\
![](https://cdn-images-1.medium.com/max/800/1*K7N9KbQlbuqowUeePjLtdw.jpeg)

\\
***Tokenizadores, caso DistilBERT y modelos***

\\
Una [nueva entrega de Transformers](https://github.com/huggingface/transformers/releases/tag/v2.5.0) de Hugging Face ahora incluye la integración de su rápida librería de tokenización que intenta mejorar el tiempo de ejecución de modelos como BERT, RoBERTa, GPT2, y otro modelos construidos por la comunidad.

# Ética en la Inteligencia Artificial 🚨

***Consideraciones éticas para modelos de NLP y ML.***

\\
En un nuevo [episodio](https://soundcloud.com/nlp-highlights/106-ethical-considerations-in-nlp-research-emily-bender) de [NLP Highlights](https://soundcloud.com/nlp-highlights), Emily Bender habla sobre algunas consideraciones éticas cuando se desarrollan modelos de Procesamiento de Lenguaje Natural y tecnologías tanto en el contexto de la academia como de industria. Algunos de los tópicos discutidos incluyen consideraciones éticas cuando se diseñan tareas, recolección de datos, y eventualmente publicación de resultados.

\\
Adicionalmente a todas las consideraciones mencionadas anteriormente, una preocupación que siempre se discute en la comunidad de AI es enfocarse demasiado en optimizar una métrica, lo que va en contra de los cimientos de lo que el campo trata de alcanzar. Rachel Thomas y David Uminsky discuten cómo esto puede salir mal a través de un [análisis](https://arxiv.org/abs/2002.08512) con diferentes casos de uso. Además, proponen un framework simple para mitigar el problema que involucra el uso y combinación de múltiples métricas, seguido del involucramiento directo de los usuarios afectados por la tecnología que se está desarrollando.

# Artículos y Blogs ✍️

***GPT-2 Explicado***

\\
Aman Arora recientemente publicó un artículo excepcional titulado “[**El GPT-2 Explicado**](https://amaarora.github.io/2020/02/18/annotatedGPT2.html)” explicando el funcionamiento interno del modelo basado en la técnica del Transformer llamado GPT-2. Su aproximación fue inspirada por el artículo [El Transformer Explicado](https://nlp.seas.harvard.edu/2018/04/03/attention.html) que tomó una aproximación a explicar las partes más importantes del modelo siguiendo ejemplos fáciles de seguir y código comentado. Amant realizó un gran esfuerzo para re implementar GPT-2 de OpenAI utilizando PyTorch y la librería de Transformers de Hugging Face. Es un trabajo brillante.

\\
![](https://cdn-images-1.medium.com/max/800/1*oRFMJTEojyQ-uocVES5GYA.png)

*[Fuente](https://amaarora.github.io/2020/02/18/annotatedGPT2.html)*

\\
***Más allá de BERT?***

\\
[Opinión](https://towardsdatascience.com/beyond-bert-6f51a8bc5ce1) interesante de Sergi Castella en que hay más allá de BERT. El tema principal incluye mejorar métricas, como la librería Transformer de Hugging Face empodera la investigación, set de datos interesantes para revisar, utilización de modelos, etc.

\\
***Operador para comprimir Matrices***

\\
El blog the TensorFlow publico un [articulo](https://blog.tensorflow.org/2020/02/matrix-compression-operator-tensorflow.html?linkId=82298016) donde explican las técnicas para compresión de matrices y su importancia en un modelo de red neuronal. La compresión de matrices puede ayudar a construir modelos más eficientes y reducidos que pueden ser incorporados en dispositivos más pequeños como teléfonos y asistentes del hogar. Enfocarse en la comprensión por métodos como low-rank-approximation y quantization significa que no debemos comprometer la calidad del modelo

\\
![](https://cdn-images-1.medium.com/max/800/1*fpAdJvBIf4SKxF3gTIpe_g.png)

*[Fuente](https://blog.tensorflow.org/2020/02/matrix-compression-operator-tensorflow.html?linkId=82298016)*

# Educación🎓

***Fundamentos del NLP***

\\
Estoy emocionado de liberar un borrador del capítulo 1 de mi nueva serie llamado [Fundamentos del NLP](https://medium.com/dair-ai/fundamentals-of-nlp-chapter-1-tokenization-lemmatization-stemming-and-sentence-segmentation-b362c5d07684). Enseña conceptos comenzando desde lo más básico, compartiendo buenas prácticas, referencias importantes, errores comunes a evitar, y cuál es el futuro del NLP. Un [Colab Notebook](https://colab.research.google.com/drive/18ZnEnXKLQkkJoBXMZR2rspkWSm9EiDuZ) está incluido y el proyecto será mantenido [aquí](https://github.com/dair-ai/nlp_fundamentals)

\\
![](https://cdn-images-1.medium.com/max/800/1*mS5NcoJ_c8hYTjiJsuu_8g.gif)

\\
***[En línea] Revisión/Discusión: Parte 1 Sesión de lectura de Fundamentos Matemáticos***

\\
Machine Learning Tokio está organizando una discusión en línea para revisar los capítulos que fueron cubiertos en su más reciente sesión de estudio. El grupo ha estudiado previamente capítulos del libro [Matemáticas para el Machine Learning](https://mml-book.github.io/) escrito por Marc Peter Deisenroth, A Aldo Faisal, y Cheng Soon Ong. El [evento](https://www.meetup.com/Machine-Learning-Tokyo/events/268817313/) está pautado para el 8 de Marzo de 2020.

\\
***Libros Recomendados***

\\
En un segmento previo discutimos la importancia de la compresión de matrices para construir modelos de ML compactos. Si estás interesado en aprender más sobre como construir redes neuronales más pequeñas para sistemas embebidos te recomiendo este gran libro llamado [TinyML](https://tinymlbook.com/?linkId=82595412) por Pete Warden y Daniel Situnayake.

\\
![](https://cdn-images-1.medium.com/max/800/0*omOa3aw2bfMzX2Qm.jpg)

*[Fuente](https://www.amazon.com/TinyML-Learning-TensorFlow-Ultra-Low-Micro-Controllers/dp/1492052043)*

\\
Otro libro interesante a tener en cuenta es “[Deep Learning para programadores con fastai y pyTorch: Aplicaciones AI sin un PhD](https://www.amazon.com/Deep-Learning-Coders-fastai-PyTorch/dp/1492045527)” por Jeremy Howard y Sylvain Gugger. El libro trata de proveer la matemática necesaria para construir y entrenar modelos que resuelvan tareas en el área de visión por computador y Entendimiento natural de texto.

\\
![](https://cdn-images-1.medium.com/max/800/0*i2OmtWOncatOYsZv.jpg)

*[Fuente](https://www.amazon.com/Deep-Learning-Coders-fastai-PyTorch/dp/1492045527)*

# Menciones a considerar ⭐️

Puedes acceder a las versiones anteriores de este boletín [aquí](https://medium.com/dair-ai/nlp-newsletter-pytorch3d-deepspeed-turing-nlg-question-answering-benchmarks-hydra-sparse-322f018ee096).

\\
[Torchmeta](https://arxiv.org/abs/1909.06576) es una librería que permite el uso de data loaders para la investigación en meta-learning. El creador es Tristan Deleu.

\\
Manuel Tonneau escribió una [pieza](https://creatext.ai/blog-posts/machine-text-writing-gpt2-beam-search?utm_medium=newsletter) ofreciendo una mirada más detallada a alguna de la maquinaria involucrada en el modelamiento del lenguaje. Algunos tópicos incluyen búsquedas greedy y beam, así como también nucleus sampling.

\\
El MIT [liberó](http://introtodeeplearning.com/) el programa de estudio completo del curso titulado “Introducción al Deep Learning”, incluye videos de las clases que ya se dictaron. Están apuntando a liberar videos y presentaciones todas las semanas.

\\
Aprende a entrenar un modelo para reconocimiento de entidades nombradas (NER) utilizando una aproximación vía Transformers en menos de [300 líneas de código](https://github.com/huggingface/transformers/blob/master/examples/ner/run_pl_ner.py). Puedes encontrar el Google Colab que lo acompaña [aquí](https://colab.research.google.com/drive/184LPlygvdGGR64hgQl3ztqzZJu8MmITn).
