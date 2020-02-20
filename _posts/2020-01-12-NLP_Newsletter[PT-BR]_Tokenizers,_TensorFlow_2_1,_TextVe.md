<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
	"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">

<head>
<title>[pt-br]NLP_Newsletter_Tokenizers,_TensorFlow_2_1,_TextVe.html</title>
<meta http-equiv="Content-Type" content="text/html;charset=utf-8"/>

</head>

<body>

<h1>NLP Newsletter: <strong>Tokenizadores, TensorFlow 2.1, Vetorização de Texto, TorchIO, Déficits de NLP, …</strong></h1>

<hr />

<p><img src="https://cdn-images-1.medium.com/max/2400/1*gLVPodYjYd4YaF9sJbSpjg.png" alt="" /></p>

<p>Olá e Feliz Ano Novo! Devido a vários pedidos, eu decidi trazer de volta a <strong>Newsletter de NLP</strong>. Dessa vez irei mantê-la pequena e focada (também mantida no <a href="https://github.com/dair-ai/nlp_newsletter">repositório</a>). O objetivo dessa newsletter é te manter informado em alguns dos mais recentes e interessantes tópicos relacionados a NLP e ML (em algumas categorias) sem tomar muito tempo do seu dia ocupado.</p>

<h1>Publicações 📙</h1>

<p><strong><em>Sistema de IA para ressonância de câncer de mama </em></strong>
A DeepMind publicou um novo artigo na Nature intitulado “<a href="https://www.nature.com/articles/s41586-019-1799-6">International evaluation of an AI system for breast cancer screening</a>” (Avaliação internacional de um sistema de IA para ressonância de câncer de mama). De acordo com os autores, o trabalho é sobre a avaliação de um sistema de IA que ultrapassa especialistas humanos na ressonância de câncer de mama. Se isso é realmente alcançável pelos sistemas de IA atuais ainda está em debate e há uma crítica contínua nesse tipo de sistema e como ele é avaliado. Aqui está um <a href="https://www.nature.com/articles/d41586-019-03822-8">pequeno resumo</a> do artigo.</p>

<p><strong><em>Extração de Informação</em></strong>
O Pankaj Gupta liberou publicamento sua tese de Ph.D. intitulada “<a href="https://www.researchgate.net/publication/336739252_PhD_Thesis_Neural_Information_Extraction_From_Natural_Language_Text">Neural Information Extraction From Natural Language Text</a>” (Extração neural de informação de texto de linguagem natural). A discussão principal é como extrair eficientemente as relações semânticas de texto em linguagem natural usando abordagens neurais. Tal esforço em pesquisa visa contribuir com a construção estruturada de bases de conhecimento, que possam ser usadas em uma série de aplicações de NLP como busca na web, respostas de questões, dentre outras.</p>

<p><strong><em>Recomendações Melhoradas</em></strong>
Pesquisadores no MIT e na IBM desenvolveram um <a href="http://news.mit.edu/2019/finding-good-read-among-billions-of-choices-1220">método</a> (publicado na NeurIPS ano passado) para categorização, surgimento, e busca de documentos relevantes baseados numa combinação de três ferramentas altamente usadas para análise de texto: <em>modelagem de tópicos</em>, <em>embeddings de palavras</em>, e <em>transporte ideal</em>. O método também dá resultados promissores para a classificação de documentos. Tais métodos são aplicáveis em uma grande variedade de cenários que requerem sugestões melhoradas e mais rápidas em grande escala tal como sistemas de busca e recomendação.</p>

<h1>ML e NLP Criatividade e Sociedade 🎨</h1>

<p><strong><em>Carreiras em IA</em></strong>
O <a href="https://hai.stanford.edu/sites/g/files/sbiybj10986/f/ai_index_2019_report.pdf">relatório</a> do índice de IA de 2019 sugere que há mais demanda que suprimento de praticantes de IA. Entretanto, há vários aspectos de empregos relacionados a IA como transições de carreira e entrevistas que ainda não são propriamente definidas.</p>

<p>Nesse <a href="https://towardsdatascience.com/how-i-found-my-current-job-3fb22e511a1f">post</a>, Vladimir Iglovivok detalha sua carreira e aventura em ML desde a construção de sistemas de recomendação tradicionais a construção de modelos espetaculares de visão computacional que ganharam competições no Kaggle. Ele agora trabalha em veículos autônomos na Lyft, mas a <a href="https://towardsdatascience.com/how-i-found-my-current-job-3fb22e511a1f">jornada</a> de chegar lá não foi tão fácil.</p>

<p>Se você está realmente interessado e sério em uma carreira em IA, a companhia do Andrew Ng, deeplearning.ai, fundou Workera, que visa a especificamente ajudar cientistas de dados e engenheiros de aprendizado de máquina com suas carreiras em IA. Obtenha o relatório oficial <a href="https://workera.ai/candidates/report">aqui</a>.</p>

<h1>Ferramentas e Base de Dados de ML/NLP ⚙️</h1>

<p><strong><em>Um tokenizador ultrarrápido</em></strong>
Hugging Face, a startup de NLP por trás dos Transformers, liberou de forma open-sourced os Tokenizers, uma implementação ultrarrápida de tokenização que pode ser usada em pipelines modernos de NLP. Cheque o <a href="https://github.com/huggingface/tokenizers">repositório no GitHub </a> para a documentação em como usar os Tokenizers.</p>

<p><img src="https://cdn-images-1.medium.com/max/1600/1*BGcXk6Yf9fXGZlEtxz1hcg.jpeg" alt="" /></p>

<p><em>Tokenizers — Python</em></p>

<p>O TensorFlow 2.1 incorpora uma nova camada de <a href="https://www.tensorflow.org/api_docs/python/tf/keras/layers/experimental/preprocessing/TextVectorization">Vetorização de Texto</a> que permite que você lide facilmente com strings brutas e execute eficientemente uma normalização de texto, tokenização, geração de n-gramas, e indexação de vocabulário. Leia o lançamento aqui e cheque o <a href="https://colab.research.google.com/drive/1RvCnR7h0_l4Ekn5vINWToI9TNJdpUZB3">notebook Colab do Chollet</a> demonstrando como usar a feature para classificação de texto fim-a-fim.</p>

<p><strong><em>NLP e ML para Busca</em></strong>
Um dos campos que fez tremendo progresso no ano passado foi NLP  com uma gama de melhoras e direções novas de pesquisa. Um dos domínio que pode potencialmente se beneficiar de transfer learning em NLP é a <em>busca</em>.</p>

<p>Apesar de a busca pertencer ao campo de recuperação da informação, há uma oportunidade para construir engines que melhores a busca semântica usando técnicas modernas de NLP como representações contextualizadas de um modelo baseado em transformer como <a href="https://arxiv.org/abs/1810.04805">BERT</a>. O Google liberou um <a href="https://www.blog.google/products/search/search-language-understanding-bert/">post de blog</a> alguns meses atrás discutindo como eles estão alavancando modelos BERT para melhorar e entender buscas.</p>

<p>Se você está curioso sobre como representações contextualizadas podem ser aplicadas à busca usando tecnologias abertas tais como Elasticsearch e Tensorflow, você pode dar uma olhada ou nesse <a href="https://towardsdatascience.com/elasticsearch-meets-bert-building-search-engine-with-elasticsearch-and-bert-9e74bf5b4cf2">post</a> ou <a href="https://towardsdatascience.com/building-a-search-engine-with-bert-and-tensorflow-c6fdc0186c8a">aqui</a>.</p>

<p><strong><em>Análise médica de imagem</em></strong></p>

<p><a href="https://github.com/fepegar/torchio">TorchIO</a> é um pacote de Python baseado na biblioteca popular chama PyTorch. TorchIO oferece funcionalidades para fácil e eficientemente ler e amostrar imagems médicas 3D. Características incluem transformações espaciais para aumento e pré-processamento de dados.</p>

<p><img src="https://cdn-images-1.medium.com/max/1600/0*FSPuSC8TK9X-NQ2q.gif" alt="" /></p>

<p><a href="https://github.com/fepegar/torchio">fonte</a></p>

<h1>Ética em IA 🚨</h1>

<p><strong><em>Comportamento fraudulento na comunidade de ML</em></strong>
Isso acabou de sair! O primeiro lugar de uma competição do Kaggle foi desqualificado por uma atividade fraudulenta. O time usou uma tática esperta mas irresponsável e inaceitável ao vencer o primeiro lugar da competição. Aqui está a <a href="https://www.kaggle.com/c/petfinder-adoption-prediction/discussion/125436">história completa</a>. Essa história realça um dos muitos dos comportamentos inaceitávies que a comunidade de aprendizado de máquina quer mitigar. O uso apropriado e ético de tecnologias de ML é o único caminho a seguir.</p>

<p><strong><em>Viés de gênero em tradução de máquina</em></strong>
A respeito do tópico se tradução de máquina reflete viés de gênero, um grupo de pesquisadores publicou esse excelente <a href="https://arxiv.org/abs/1809.02208">artigo</a> apresentando um estudo de caso usando o tradutor do Google. Uma das descobertas dos autores afirma que o tradutor do Google “exibe uma tedência forte a padrões masculinos, em particular para campos ligados a distribuições desbalanceadas de gênero tal como trabalhos STEM.”</p>

<p><strong><em>Viés e Justiça em ML</em></strong>
Se você quer se atualizar com tudo de ética e justiça em IA, esse é um ótimo <a href="https://twimlai.com/twiml-talk-336-trends-in-fairness-and-ai-ethics-with-timnit-gebru/">episódio de podcast</a> com a participação de Timnit Gebru e apresentado por TWIML.</p>

<p>Timit é uma pesquisadora proeminente em justiça em ML que, junto com Eun Seo Jo, publicou um <a href="https://arxiv.org/abs/1912.10389">artigo</a> onde identificam cinco abordagens chave em práticas de coleta de documentos em arquivos que podem prover métodos mais confiáveis para coleta de dados em ML sociocultural. Isso pode potencialmente levar a um método de coleta de dados mais sistemático, ganhado de uma pesquisa colaborativa.</p>

<p>Sina Fazelpour e Zachary Lipton recentemente publicaram um <a href="http://zacklipton.com/media/papers/fairness-non-ideal-fazelpour-lipton-2020.pdf">artigo</a> onde argumentam que, devido à natureza de como nosso mundo não ideal surgiu, é possível que ML justo, baseado no pensamento ideal, pode potencialmente levar a políticas e intervenções mal guiadas. Na verdade, suas análises demonstraram “que deficiências em algoritmos de ML refletem problemas maiores encarados pela abordagem ideal.”</p>

<h1>Artigos e posts de blogs ✍️</h1>

<p><strong><em>Déficits em NLP</em></strong>
Benjamin Heinzerling publicou um artigo interessante no The Gradient onde eles discute áreas onde NLP falha, como compreensão de argumentos e raciocínio de senso comum. Benjammin faz referência ao <a href="https://www.aclweb.org/anthology/P19-1459/">artigo</a> recente por Nivin &amp; Kao, que desafia e questiona as capacidades de transfer learning e modelos de lingauem para entendimento de linguagem natural (NLU) em alto nível. <a href="https://thegradient.pub/nlps-clever-hans-moment-has-arrived/">Leia</a> mais sobre esse excelente resumo da análise executada na pesquisa.</p>

<p><strong><em>Destaques de NLP e ML em 2019</em></strong>
Para o ano novo, eu liberei um <a href="https://medium.com/dair-ai/nlp-year-in-review-2019-fb8d523bcb19">relatório</a> documentando alguns dos destaques mais interessantes em NLP e ML pelos quais passei em 2019.</p>

<p>Sebastian Ruder também escreveu recentemente um <a href="https://ruder.io/research-highlights-2019/">post de blog</a> excelente e detalhado sobre as top dez direções de pesquisa em ML e NLP que ele achou impactante em 2019. Na lista estão tópicos como pré treino não supervisionado e universal, ML e NLP aplicados à ciência, aumentando modelos pré treinados, Transformers eficientes e de longo alcance, entre outros.</p>

<p><img src="https://cdn-images-1.medium.com/max/1600/0*8zoPc5OnYERIaaMP.png" alt="" /></p>

<p><em>“VideoBERT (</em><a href="https://arxiv.org/abs/1904.01766"><em>Sun et al., 2019</em></a><em>), uma variante recente multimodal do BERT que gera “tokens” de vídeos dado uma receita (acima) e prediz os tokens futuros em escalas de tempo diferentes dado um token de vídeo(abaixo).” —</em> <a href="https://arxiv.org/pdf/1904.01766.pdf"><em>fonte</em></a></p>

<p>A Google AI de pesquisa publicou um <a href="https://ai.googleblog.com/2020/01/google-research-looking-back-at-2019.html">resumo</a> da pesquisa conduzida por eles durantes o ano, e as direções futuras de pesquisa que eles estão prestando atenção.</p>

<h1>Educação em ML/NLP  🎓</h1>

<p><strong><em>Democratizando educação em IA</em></strong>
Num esforço de democratizar educação em IA e para educar as massas sobre as implicações de tecnologia de IA, a Universidade de Helsinki fez uma parceria com a Reaktor para lançar um curso brilhante (de graça) que cobre os fundamentos de IA. O <a href="https://www.elementsofai.com/">curso popular</a> se chama “Elementos de AI” e inclui tópicos tal como ética em IA, filosofia em IA, redes neurais, regra de Naive Bayes, dentre outros tópicos.</p>

<p>Stanford CS224N está de volta com outra <a href="http://web.stanford.edu/class/cs224n/">iteração</a> do popular curso de “Natural Language Processing with Deep Learning”. O curso oficialmente começou em 7 de Janeiro dessa ano, então se você quiser acompanhar, vai para o site para o programa completo, slides, vídeos, sugestões de leitura de paper, etc.</p>

<p><strong><em>Top livros de NLP e ML</em></strong>
Eu tweetei meus top livros de ML e NLP práticos e teóricos, e foi bem recebido. Eu gostaria de compartilhar aquela lista aqui via tweet: https://twitter.com/omarsar0/status/1214547402838986754?s=20</p>

<p><strong><em>Machine Learning com Métodos de Kernel</em></strong>
Métodos de Kernel tais como PCA e k-means estão por aqui há muito tempo, e isso é porque eles têm sido aplicados com sucesso a uma variedade grande de aplicações tal quais grafos e sequências biológicas. Cheque esse conjunto compreensível de <a href="http://members.cbio.mines-paristech.fr/~jvert/svn/kernelcourse/slides/master2017/master2017.pdf">slides</a> cobrindo um alcance grade de métodos de kernel e suas aplicações internas. Aqui está também um ótimo <a href="https://francisbach.com/cursed-kernels/">blog</a> (mantido por Francis Bach) discutindo aspectos de métodos de kernel e outros tópicos de aprendizado de máquina.</p>

<h1>Menções Honrosas ⭐️</h1>

<p>Aqui está uma lista de histórias dignas de nota e da sua atenção:</p>

<ul>
<li>John Langford cuida desse incrível <a href="https://hunch.net/">blog</a> que discute teoria de aprendizado de máquina</li>
<li>Muitas das tecnologias da indústria orientadas a ML têm usado máquinas de Gradient Boosting por anos. Cheque esse <a href="https://opendatascience.com/xgboost-enhancement-over-gradient-boosting-machines/?utm_campaign=Learning%20Posts&amp;utm_content=111061559&amp;utm_medium=social&amp;utm_source=twitter&amp;hss_channel=tw-3018841323">post</a> introduzindo uma das bibliotecas usadas para aplicar o gradient boosting chamado XGBoost.

<ul>
<li>Se você está interessado em aprender como fazer o design e construir aplicações de aprendizado de máquina e levá-las à produção, Emmanual Ameisen cobre isso com esse <a href="https://www.amazon.com/Building-Machine-Learning-Powered-Applications/dp/149204511X/">livro</a>.</li>
</ul>
</li>
</ul>


<hr />

<p><em>Se você tem uma história que gostaria de ser publicada na próxima edição da Newsletter de NLP, por favor mande um email para ellfae@gmail ou me mande uma mensagem via</em> <a href="https://twitter.com/omarsar0"><em>Twitter</em></a><em>.</em></p>

</body>
</html>
