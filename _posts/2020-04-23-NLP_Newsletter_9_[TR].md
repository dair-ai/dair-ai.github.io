---
layout: post
title: "NLP Haber Bülteni #9 [TR]: Görselleştirilmiş GNN Rehberi, TextVQA ve TextCaps, KeraStroke, SyferText, torchlayers…"
author: harunuz
excerpt: "Bu sayı, mahremiyeti korumaya yönelik NLP araçları, COVID-19 ile ilgili bildirileri araştırmak için etkileşimli araçlar ve çizge sinir ağları için illüstrasyon destekli rehber gibi konu başlıklarını içermektedir."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_9.png
---


![](https://cdn-images-1.medium.com/max/1200/1*Vq-bFSTjqYjDGAR4Ja1abw.png)

\\
NLP Haber Bülteni'nin 9. sayısına hoş geldiniz. Umarız siz ve sevdikleriniz iyi ve güvendesinizdir. Bu sayı, mahremiyeti korumaya yönelik bir NLP aracından COVID-19'la ilgili bildirileri bulabilmek için geliştirilmiş etkileşimli araçlara ve çizge sinir ağları oluşturmaya yönelik illüstrasyon destekli bir kılavuza kadar uzanan konuları içermektedir. 


# Araştırma and Yayınlar 📙

***Kendi-Yorumlayabilen Ajanların Nöroevrimi***

\\
[Burada](https://attentionagent.github.io/) (Tang et al. 2020), bir görevi sürdürebilmek hedefiyle bir görsel girdi parçasından  yararlanabilen bir ajan geliştirmeyi amaçlayan (örn; aşağıdaki şekilde görüldüğü gibi virajları çarpmadan geçebilmek veya kurşunlardan kaçınabilmek için) ilginç ve yaratıcı bir çalışma sunuluyor. Çalışmayı yapanlar, girdilerin sadece bir parçasını kullanma kısıtı altında farklı görevleri icra edebilmek için takviyeli öğrenme ajanlarını, self-attention yapıları eğitebilmek için Nöroevrim'i ([neuroevolution](https://en.wikipedia.org/wiki/Neuroevolution)) kullanarak, eğitmeyi başardılar. Modelin faydaları arasında; parametrelerin boyutunda önemli bir azalma, hareket tarzı yorumlanabilirliği ve modelin sadece *görev açısından kritik görsel ipuçlarının değerlendirmesini sağlamak* yer alıyor.

\\
![](https://cdn-images-1.medium.com/max/800/1*Gm8jlCUvP_JECEPspDypWg.png)

\\
***RONEC'e Giriş: the Romanian Named Entity Corpus***

\\
[RONEC](https://arxiv.org/abs/1909.01247), Rumen dili için, 16 farklı sınıfa ait ~5000 açıklamalı cümlede 26000'den fazla varlık içeren, adlandırılmış bir varlık derlemidir (corpus). Cümleler, çeşitli biçimleri kapsayan, telifsiz bir gazeteden alınmıştır. Bu derlem, Romence dil alanındaki, özellikle adlandırılmış varlık tanıma amaçlı ilk girişimidir. Derlemin BIO ve CoNLL-U Plus formatları da mevcut ve [burada](https://github.com/dumitrescustefan/ronec) erişilen bu derlemi kullanmak ve genişletmek serbettir.

\\
***Yapay Sinir Modelleri İçin Ölçekleme Kanunları***

\\
John Hopkins ve OpenAI'den araştırmacılar, dil modeli performansı için ölçekleme yasalarını (scaling laws) anlamak için ampirik bir [çalışma](https://arxiv.org/abs/2001.08361) yaptılar. Bu tür bir çalışma, kaynakların nasıl daha etkin kullanılacağı konusunda daha iyi kararlar almak için bir rehber niteliğinde. Genel olarak, daha büyük modellerin örneklem açısından belirgin şekilde daha verimli olduğu görülmüştü. Eğer veri veya hesaplamalar limitliyse, küçük bir modeli eğitmek yerine bir büyük modelin yakınsama gerçekleşene kadar birkaç aşamalı şekilde eğitilmesi daha iyidir (aşağıdaki şekilde özetlenen sonuçlara göz atın). Araştırmacılar, aşırı öğrenme (overfitting), optimum yığın boyutu seçme, ince-ayarlama, mimari seçimi vb. açısından büyük dil modellerinin eğitimiyle ilgili (örn; Transformatörler) birçok bulgu ve öneri sunuyorlar. 

\\
![](https://cdn-images-1.medium.com/max/800/1*plbjqswVe4Cq8UVggqPH1w.png)

[*Kaplan et al. (2020)*](https://arxiv.org/abs/2001.08361)

\\
***Ön-eğitim'e Tabi Tutulmuş Transformatörlerin Kalibrasyonu***

\\
Ön-eğitim'e tabi tutulmuş transformatörlerin pratik uygulamalarının artışıyla birlikte, bu transformatörlerin ne denli *güvenilir* çıktılar verdiklerini anlamak önem kazandı. UT Austin tarafından yapılan son [çalışma](https://arxiv.org/abs/2003.07892), BERT ve RoBERTa’nın posterior olasılıklarının hem alan (domain) içi hem de alan dışı zorlu veri kümeleriyle üç görevde (doğal dil çıkarımı, yorumlama algılama, sağduyulu akıl yürütme) nispeten kalibre edildiğini (yani ampirik sonuçlarla tutarlı) göstermektedir. Sonuçlar şunu göstermektedir: (1) hazır olarak kullanıldığında, ön-eğitim'e tabi tutulmuş modeller alan içinde kalibre edilmiştir; ve (2) sıcaklık ölçeklendirme (temperature scaling), alan içi kalibrasyon hatasını daha da azaltmada etkilidir, ampirik belirsizliği artırmak için etiket yumuşatma, posteriorları alan dışında kalibre etmeye yardımcı olur.

\\
![](https://cdn-images-1.medium.com/max/800/1*ose0s-G0WfPFoleZJ1htrQ.png)

[*Desai ve Durrett (2020)*](https://arxiv.org/pdf/2003.07892.pdf)

\\
***Derin Öğrenmenin İstatistiksel Mekaniği***

\\
Yakın tarihli bir [bildiri](https://www.annualreviews.org/doi/abs/10.1146/annurev-conmatphys-031119-050745)de fiziksel / matematiksel konular ile derin öğrenme arasındaki bağlantıya daha yakından bakılıyor. Araştırmacılar, istatistiksel mekanik ve makine öğrenimi ile kesişen daha derin konuları, derin sinir ağlarının teorik yönünü ve neden başarılı olduklarını anlamaya yardımcı olan soruları yanıtlamak amacıyla tartışmayı amaçlamaktalar.

\\
***Konuşmanın Metne Çevrimi'nde Bir ImageNet Başarımına Doğru***

\\
The Gradient'de yayımlanan yeni bir [makale](https://thegradient.pub/towards-an-imagenet-moment-for-speech-to-text/)de Alexander Veysov Rus Dili bağlamında neden ImageNet başarımına ulaşılmış olabileceğine inandıklarını anlatıyor. Son birkaç yıldır, araştırmacılar NLP konusunda da benzer ifadelerde  bulunuyorlar. Yine de, Konuşmanın Metne Çevrimi'nde böyle bir başarıma ulaşmak için, Alexander, modelleri yaygın olarak kullanılabilir hale getirmek, hesaplama gereksinimlerini en aza indirmek ve ön-eğitim'e tabi tutulmuş büyük modellerin erişilebilirliğini artırmak gibi birçok parçanın bir araya gelmesi gerektiğini belirtiyor.


# Yaratıcılık, Etik ve Toplum 🌎

***COVID-19 İle İlgili Yayınları Taramak***

\\
Geçen hafta COVID'le ilgili bildirilerin bulunduğu [CORD-19](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) olarak isimlendirilen herkese açık bir veri setinden bahsetmiştik. Gabriel Sarti, [SciBERT ince-ayar'a tabi tutulmuş model](https://huggingface.co/gsarti/scibert-nli)'inden yararlanarak, bu bildirileri daha iyi inceleyebilmeniz için etkileşimli bir araç geliştirdi. Araca [buradan](https://github.com/gsarti/covid-papers-browser) erişebilirsiniz.

\\
![](https://cdn-images-1.medium.com/max/800/0*tu8nzUIEuSizuW5-.gif)

\\
Diğer yandan reciTAL, araştırmacıların ve sağlık uzmanlarının COVID-19 ile ilgili bilgileri hızlı ve verimli bir şekilde bulmalarına ve keşfetmelerine yardımcı olmak amacıyla ilgili makalelerde arama ve göz atmaya özelleşmiş [COVID-19 Akıllı Arama Motoru](https://covidsmartsearch.recital.ai/) adlı bir proje de yayınladı.

\\
![](https://cdn-images-1.medium.com/max/800/1*Y5W3sib4y6UxSr3YkQSu5Q.png)

\\
***SyferText***

\\
OpenMind, gizli veri setleri için mahremiyeti korumaya yönelik güvenli ve özel NLP işlemlerinin yapılmasını hedefleyen yeni NLP kütüphanesi [SyferText](https://github.com/OpenMined/SyferText)'i yayınladı. Çalışma henüz erken evrelerinde; ancak bunun daha etik ve güvenli AI sistemleri için harcanmış önemli bir efor olduğuna inanıyoruz. Başlamak için [şurada](https://github.com/OpenMined/SyferText/tree/master/tutorials) birkaç rehber bulabilirsiniz.


\\
***Daha ucuz, daha hızlı ve daha çevreci NLP için daha küçük modellere doğru***

\\
Daha büyük modeller her zaman daha mı iyidir? Geçtiğimiz birkaç yıldaki dil modeli boyutlarının evriminine bakılırsa, bu soru evet diye cevaplanabilir; ancak bu canavarları eğitmenin finansal ve çevresel maliyeti oldukça yüksek. Ayrıca, bu durumda daha büyük genellikle daha yavaş anlamına gelmektedir ve hız birçok uygulamada hayati önem taşımaktadır. Bu da NLP'deki gidişatı, mevcut performansı korurken daha küçük, daha hızlı ve daha çevreci modeller için uğraşmaya motive etmektedir. Şu blog gönderisinde, [Manuel Tonneau](https://www.linkedin.com/in/ACoAABs605YB_jMmGA0iLFongpVm1iKjFmKLSts/), küçük modelleri tercih eden bu yeni akımı, güncel ve popüler üç modele odaklanarak tanıtmaktadır: [HuggingFace](https://www.linkedin.com/in/ACoAABs605YB_jMmGA0iLFongpVm1iKjFmKLSts/)'den DistilBERT, [Google](https://www.linkedin.com/company/google/)'dan PD-BERT ve [Microsoft](https://www.linkedin.com/company/microsoft/)'tan BERT-of-Theseus.


\\
***Bilimsel keşif için Derin Öğrenme Üzerine Derleme***

\\
Günümüzde yapay zeka araştırmaları üzerine odaklanmış birçok şirket, derin öğrenmenin bilimsel keşiflerde bir araç olarak kullanılabileceğine inanmaktadır. Şu [bildiri](https://arxiv.org/abs/2003.11755), farklı bilimsel kullanım senaryoları için yaygın olarak kullanılan derin öğrenme modelleri üzerine kapsamlı bir genel bakış sağlamaktadır. Aynı zamanda geliştirme ipuçları, rehberler, farklı araştırma özetleri ve araçlar da tanıtmaktadır.


# Araçlar ve Veri Setleri ⚙️

***TextVQA ve TextCaps***

\\
Görüntülerdeki metinleri daha iyi tespit edip okuyan modeller geliştirmeyi ve bu modelleri soru cevaplama, altyazı oluşturma gibi işlemlerde kullanmayı teşvik etme amacıyla, Facebook AI iki adet yarışmaya ev sahipliği yapmaktadır. Yarışmaların isimleri [TextVQA](https://textvqa.org/challenge) Challenge ve [TextCaps](https://textvqa.org/textcaps/challenge) Challenge; sırasıyla görsel soru cevaplama ve altyazı üretme görevlerine hitap etmektedirler.

\\
***KeraStroke***

\\
Bir sinir ağı tasarlarken üstesinden gelinmesi gereken en büyük güçlüklerden birisi aşırı öğrenmedir (overfitting). Dropout, Regularization ve erken durdurma gibi güncel genelleştirme-geliştirme teknikleri birçok kullanım senaryosunda oldukça etkilidir; ancak büyük modeller ya da küçük veri setleri kullanıldığında yetersiz kalma eğilimindedirler. Bu duruma cevap olarak, Charles Averill, büyük modeller ya da küçük veri setlerinde oldukça kullanışlı yeni bir genelleştirme-geliştirme tekniği [KeraStroke](https://pypi.org/project/kerastroke/#description)'u geliştirdi. Bu teknik sayesinde eğitim esnasındaki belirli durumlarda ağırlık değerlerini değiştirerek, modeller aldıkları eğitim verisine dinamik olarak adapte olabilmektedirler.


\\
***torchlayers***

\\
[torchlayers](https://github.com/szymonmaszke/torchlayers), torch.nn modülünde bulunan evrişimli ağ, tekrarlayan ağ, transformatör vb. katmanlarının biçim ve boyutlarının otomatik anlamlandırılmasına olanak sağlayan PyTorch'un üzerine kurulmuş yeni bir araçtır. Bu sayede katmanlarda elle belirtilmesi gereken girdi özelliklerinin (input features) boyutlarını açıkça tanımlamaya gerek kalmamaktadır. PyTorch'ta bir modelin tanımlanması oldukça basitleşmektedir. torchlayers ile gerçeklenmiş basit bir sınıflandırıcı örneğini aşağıda görebilirsiniz.

\\
![](https://cdn-images-1.medium.com/max/800/1*tHOme2pZ39sNziqdUCsn4g.png)

*Kod parçasından görüldüğü üzere Linear katman hem output hem de input boyutunun aksine yalnızca output boyutunun belirtilmesine ihtiyaç duymaktadır. Input boyutu torchlayers tarafından otomatik bir şekilde çıkarılmaktadır.*


\\
***Haystack: Farklı Ölçeklerde Soru Cevaplama için Açık Kaynaklı kütüphane***

\\
[Haystack](https://github.com/deepset-ai/haystack/), farklı ölçeklerde soru cevaplama için transformatör modellerinin kullanılmasına olanak sağlamaktadır. Bulucu-Okuyucu-Pipeline'ını (Retriever-Reader-Pipeline) kullanmaktadır. Bu yaklaşımda Bulucu, aday belgeleri bulan hızlı bir algoritma; Okuyucu ise cevabı parça parça çıkaran bir transformatördür. Elasticsearch ve HuggingFace'in Transformers kütüphanesi üzerine kurulmuştur. Açık kaynaklı, oldukça modüler ve kolay genişletilebilir bir yapıdadır.


\\
***Bir yapay zekaya haber makalelerini özetlemeyi öğretmek: Soyutlayıcı özetleme için yeni bir veri seti***

\\
Curation Corp 40.000 adet profesyonelce yazılmış haber makalesi özetlerini açık kaynak olarak kullanıma sundu. Bu [makale](https://medium.com/curation-corporation/teaching-an-ai-to-abstract-a-new-dataset-for-abstractive-auto-summarisation-5227f546caa8), metin özetleme ve işlemin zorluklarına güzel bir giriş sağlamaktadır. Ek olarak, veri setini ve veri seti ile ele anılabilecek problemleri tanıtmaktadır, metin özetlemede değerlendirme metrikleri ve ince ayar(fine-tuning) teknikleri üzerine bir tartışmayı içermektedir. Gelecek çalışmalar üzerine bir tartışma ile de makale sonlanmaktadır. Veri setine nasıl erişileceğine dair açıklamalar şu [GitHub reposunda](https://github.com/CurationCorp/curation-corpus), veri setini ince ayar işlemlerinde kullanmak için örnek çalışmalar da [burada](https://github.com/CurationCorp/curation-corpus/tree/master/examples) bulunabilir.

\\
Metin özetleme konusunda, HuggingFace takımı [Transformers](https://github.com/huggingface/transformers/releases) kütüphanelerinin bir parçası olarak [BART](https://github.com/pytorch/fairseq/blob/master/examples/bart/README.md) ve [T5](https://github.com/dair-ai/nlp_paper_summaries/blob/master/Language%20Modeling/t5-text-to-text-transformer.md)'i eklediler. Bu eklemeler soyutlayıcı özetleme, çeviri ve soru cevaplama ve daha birçok NLP işleminin gerçeklenmesine olanak sağlamaktadır.


# Makaleler ve Blog gönderileri ✍️

***İllüstrasyon Destekli Çizge Sinir Ağları(Graph Neural Networks) Rehberi***

\\
Çizge sinir ağları son zamanlarda ilaç kullanımının yan etkilerini tahmin etme ve bilgisayarla görü modellerinin başarımını artırma gibi birçok işlemde benimsenmiş vaziyettedirler. Şu [yazıda](https://dair.ai/An_Illustrated_Guide_to_Graph_Neural_Networks/), Rish, çizge sinir ağlarına(GNN) resimli bir kullanışlı rehber ortaya koymaktadır. (*[*dair.ai*](https://dair.ai/)'da öne çıkanlar*)

\\
![](https://cdn-images-1.medium.com/max/800/1*Ru3CizrB14hvpZQ7ZtgIag.png)

\\
***JAX ve Haiku ile Transformer'lara ince ayar(Fine-tuning)***

\\
Geçtiğimiz ay DeepMind, kendi TensorFlow yapay sinir ağı kütüphaneleri olan Sonnet'in JAX versiyonu Haiku'yu açık kaynaklı olarak kullanıma sundu. Şu [gönderi](https://www.pragmatic.ml/finetuning-transformers-with-jax-and-haiku/) ön-eğitime tabi tutulmuş RoBERTa modelinin JAX + Haiku'ya açılan kapısı olan kaynak kodun üzerinden geçmektedir. Ardından modeli ince ayara tabi tutarak bir alt görevi(downstream task) çözmeyi göstermektedir. Gönderinin, düşük maliyetli nesne tabanlı modüllerin JAX'ın fonksiyonel programlama kısıtlamaları bağlamında kullanılmasına olanak sağlamak için Haiku'nun ortaya koyduklarından faydalanmayı gösteren kullanışlı bir rehber olması amaçlanmaktadır.

\\
***Doğal Dil İşleme vadisinde küçük bir gezinti: Metin önişleme ve Almanca***

\\
Flávio Clésio, Almanca'da NLP sorunlarıyla başa çıkarken karşılaşılan zorlukları anlatan oldukça detaylı bir [makale](https://flavioclesio.com/2020/02/17/a-small-journey-in-the-valley-of-natural-language-processing-and-text-pre-processing-for-german-language/) yazdı. Yazısında, öğrendiği dersleri, nelerin işe yarayıp nelerin yaramadığını, birçok state-of-the-art tekniğin tartışmasını, kaçınılması gereken yaygın hataları ve bildiriler, bloglar gibi tonlarca öğrenme kaynakları paylaşmaktadır. 

\\
***Fransızca yapay zekaya ayak uyduruyor: FlauBERT, CamemBERT, PIAF***

\\
Geçtiğimiz birkaç ayda, ilgi çekici Fransızca NLP kaynakları geliştirildi. CamemBERT, FlauBERT ve PIAF(Pour une IA Francophone, Fransızca Konuşan bir AI için)'dan bahsetmekteyiz. İlk iki model ön-eğitime tabi tutulmuş dil modelleridir; sonuncu ise Fransızca soru-cevap(QA) veri setidir. Şu [blog gönderisi](https://piaf.etalab.studio/francophonie-ia-english/), üç projeyi ve projelerin süreçlerinde karşılaşılan bazı zorlukları ele almaktadır. Kendi dillerinde farklı modeller üzerinde çalışan insanlar için güzel bir yazı ve rehber niteliği taşımaktadır.


\\
***BERT-tarzı dil modeli için özel sınıflandırıcı***

\\
Marcin, BERT-tarzı modeller üzerine kendi sınıflandırıcınızı(duygu sınıflandırıcı gibi) nasıl inşa edebileceğinizi anlatan harika bir [rehber](https://zablo.net/blog/post/custom-classifier-on-bert-model-guide-polemo2-sentiment-analysis/) daha yazdı. Oldukça güzel bir rehber; çünkü rehber aynı zamanda modelin farklı kısımları için HuggingFace Tokenizer ve PyTorchLightning gibi modern kütüphaneleri nasıl kullanabileceğinizi de açıklamaktadır. Google Colab notebook'unu [burada](https://colab.research.google.com/drive/1sajgpLTrTJDzRSlxycy8aE6ysxGqaT18) bulabilirsiniz.


\\
![](https://cdn-images-1.medium.com/max/800/0*66IKvwYU2Lq1kjyn.png)

[*Kaynak*](https://zablo.net/blog/post/custom-classifier-on-bert-model-guide-polemo2-sentiment-analysis/)


# Eğitim 🎓

***Metin Verisi için Keşifsel Veri Analizi***

\\
Bu kod [örneklerinde]((https://dair.ai/Exploratory_Data_Analysis_for_Text_Data/)), Yonathan Hadar, metinsel verinin keşifsel analizi üzerine birçok tekniğin üzerinden geçmektedir. Bu rehbere dair.ai'da yer vermemizin sebebi veri analizinde herhangi bir veri bilimciniin faydalı bulacağı kabul görmüş teknikleri detaylı bir şekilde anlatmasıdır. Metinsel veri ile uğraşacak birinin başlaması için oldukça iyi bir noktadır.

\\
***Doğal Dil İşlemede Gömmeler***

\\
Mohammed Taher Pilehvar ve Jose Camacho-Collados, "Embeddings in Natural Language Processing (Doğal Dil İşlemede Gömmeler)" adlı yeni gelecek [kitaplarının](https://medium.com/r/?url=http%3A%2F%2Fjosecamachocollados.com%2Fbook_embNLP_draft.pdf) ilk taslağını kamuya sundular. Kitabın ana odak noktası NLP alanında kullanılan en yaygın teknikleri temsil eden gömme konseptini tartışmaktır. Yazarlar tarafından [belirtildiği](https://medium.com/r/?url=https%3A%2F%2Ftwitter.com%2FCamachoCollados%2Fstatus%2F1246013768074747906%3Fs%3D20) üzere, kitap "vektör uzay modellerinin temelleri, daha güncel cümleye göre kelime gömmeleri ve ön-eğitime tabi tutulmuş modellere dayalı bağlamsal gömme tekniklerini" içermektedir.

\\
***A Brief Guide to Artificial Intelligence(Yapay Zekaya Kısa Bir Rehber)***

\\
Dr. James V Stone, güncel AI sistemleri ve birçok görevi yerine getirmedeki başarımları hakkında kapsamlı bir genel bakış sağlamak amacıyla yeni [kitabı](https://jim-stone.staff.shef.ac.uk/AIGuide/) "A Brief Guide to Artificial Intelligence(Yapay Zekaya Kısa Bir Rehber)"ı kısa süre önce yayımladı. Özetinde belirtildiği üzere: "kitap resmiyetten uzak bir tarzda, kapsamlı bir açıklayıcı sözlük ve ileride okunması gerekenlerin listesi ile yazılmıştır; bu da kitabı, hızla evrimleşen AI alanına ideal bir giriş yapmaktadır.".

\\
![](https://cdn-images-1.medium.com/max/800/0*I2YYXTCQTBmk_YiF.jpg)

\\
***Makine Öğrenmesi ve Derin Öğrenme Kursları***

\\
Sebastian Raschka, "Introduction to Deep Learning and Generative Models(Derin Öğrenme ve Üretken Modellere Giriş)" adlı kursunun iki [bölümünü](https://www.youtube.com/watch?time_continue=1&v=QQD9Y2FiotQ&feature=emb_logo) yayınladı. Ders notlarını ve materyallerini şu [repoda](https://github.com/rasbt/stat453-deep-learning-ss20) bulabilirsiniz.

\\
"Ayrık Diferansiyal Geometri" alanındaki bu muhteşem [derslere](https://www.youtube.com/watch?v=e-erMrqBd1w&feature=youtu.be) göz gezdirebilirsiniz.

\\
Peter Bloem, VU University Amsterdam'da verdikleri Makine Öğrenmesi'ne giriş dersinin ders sunuları ve videolarını da içeren bütün [ders müfredatını](https://mlvu.github.io/) yayınladı. Konular, lineer modeller ve olasılıksal modellerden sıralı veri modellerine kadar uzanmaktadır.

\\
***CNN Yapısı — Uygulamaları***

\\
Dimitris Katsios, orijinal bildirilerde önerilmiş evrişimli sinir ağı(CNN) yapılarının nasıl gerçeklenebileceğini anlatan bir dizi harika [rehber](https://github.com/Machine-Learning-Tokyo/CNN-Architectures/tree/master/Implementations) sağlamaktadır. Yazılarında, modelin yapısını çıkarma yeterliğinde, adım adım işlemleri diyagram ve kodlar ile paylaşırken CNN modellerinin nasıl gerçekleneceğini tarif etmektedir.


# Bunlara da göz atın ⭐️

Bir önceki haber bülteninin orjinial halini [şurada](https://dair.ai/NLP_Newsletter_8/); çevirilerini ise şu GitHub [reposunda](https://github.com/dair-ai/nlp_newsletter) bulabilirsiniz.

\\
İki ay önce Luis Serrano'nun "Grokking Machine Learning(Grokking Makine Öğrenmesi)" adlı kitabına yayınlarımızda yer vermiştik. Luis'in kendi kitabı hakkındaki fikirlerini ve makine öğrenmesi alanında nasıl iyi bir eğitmen olduğunu anlatan hikayesini [şuradan](https://content.alegion.com/podcast/grokking-machine-learning-with-luis-serrano) dinleyebilirsiniz.

\\
İşte ilginize değebilecek birkaç haber bülteni: [Sebastian Ruder’in NLP Haberleri](http://newsletter.ruder.io/), [Made With ML(Makine Öğrenmesi ile Yapıldı](https://madewithml.com/blog/newsletter/2020-03-25/), [SIGTYP’in Haber Bülteni](https://sigtyp.github.io/sigtyp-newsletter-Mar-2020.html), [MLT Haber Bülteni](https://mailchi.mp/c70ebcf424b2/mlt-newsletter-6), [Nathan’ın AI bülteni](http://newsletter.airstreet.com/issues/your-guide-to-ai-in-q1-2020-part-1-2-212335), vb...

\\
Jupyter artık bir [görsel hata ayıklayıcıya](https://blog.jupyter.org/a-visual-debugger-for-jupyter-914e61716559) sahip. Bu sayede, popüler veri bilimi aracı genel amaçlar için daha kolay kullanılabilir olmaktadır.

\\
![](https://cdn-images-1.medium.com/max/800/0*FE5Fj5DFb0U9565a.gif)

\\
Abhishek Thakur, modern makine öğrenmesi ve NLP tekniklerinin nasıl kullanılacağını kodların üzerinden geçerek gösterdiği harika bir YouTube [kanalına](https://www.youtube.com/channel/UCBPRJjIWfyNG4X-CRbnv78A) sahip. Bazı videoları, BERT modellerine ince ayar yaparak el yazısı karakterlerini sınıflandırmaktan bir makine öğrenmesi aracı inşa etmeye kadar uzanmaktadır.

\\
Ünlü takviyeli/pekiştirmeli öğrenme profesörü ve araştırmacı David Silver, bilgisayar oyunlarına getirdiği çığır açan yenilikler için ACM Prize in Computing ile [ödüllendirildi](https://awards.acm.org/about/2019-acm-prize). David, Lee Sedol'u Go'da yenen Alpha Go takımına liderlik etmişti.

\\
BERT ve word2vec gibi popüler NLP tekniklerinin çalışma prensipleri arasındaki farkları öğrenmek isteyenler için Mohd, bu yaklaşımlara harika, kolay ulaşılabilir ve detaylı genel bakış yazıları [sağlamaktadır](https://www.analyticsvidhya.com/blog/2019/09/demystifying-bert-groundbreaking-nlp-framework/).

\\
TensorFlow 2.2.0-rc-1 [yayınlandı](https://github.com/tensorflow/tensorflow/releases/tag/v2.2.0-rc1?linkId=85073218). ML modellerinde darboğaz olan noktaları tespit etmeye yardımcı olan Profiler ve bu modellerin nasıl optimize edileceğini gösteren rehberler gibi yenilikler içermektedir. Ayrıca, Colab da artık [varsayılan](https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/tutorials/quickstart/advanced.ipynb?linkId=85251566) olarak TensorFlow 2 kullanmaktadır.

\\
Gabriel Peyré, ML optimizasyonu dersi için bir dizi kullanışlı [not](https://mathematical-tours.github.io/book-sources/optim-ml/OptimML.pdf) sağlamaktadır. Notlar, dışbükey analizi(convex analysis), SGD(rastgele gradyan inişi), autodiff(otomatik diferansiyel), MLP(çok katmanlı algılayıcı) gibi konu başlıklarını içermektedir.


----------

## dair.ai sitesinden güncellemeler

- ***Açık Bilim için İşbirlikçilere Çağrı:*** Açık bilime katkı yapmak isteyenlere çağrıda bulunmaktayız. Pipeline'da birçok ilgi çekici işbirliği konusu var. Davetiyelerimizi açık bilime katkıda bulunmak isteyen herkese ulaştırmak istiyoruz. Gönüllüler, yazarlar, eleştirmenler, editörler, geliştiriciler, konuşmacılar, araştırmacılar, proje sahipleri vb. aramaktayız. [Bize katılın](https://github.com/dair-ai/dair-ai.github.io/issues/54)!

- ***NLP Araştırmasında İlginç Olaylar Sayı #1:*** ICYMI, şu [makalede](https://dair.ai/NLP_Research_Highlights_-_Issue_-1/), bazı NLP akımlarını ve konu başlıklarını, geçtiğimiz birkaç ayda yayımlanan ilginç ve önemli NLP bildirilerinin hangisini,nasıl ve neden seçtiğimizi özetlemeye odaklanarak vurgulamaktayız.

----------
Eğer NLP Haber Bülteni'nin sonraki sayılarında paylaşmak istediğiniz veri seti, proje, blog, rehber veya bildiri varsa lütfen şu [formu](https://forms.gle/3b7Q2w2bzsXE6uYo9) kullanarak direkt gönderiniz.

\\
*🔖Gelen kutunuzda NLP Haber Bülteni'nin gelecek sayılarını görmek istiyorsanız [buradan](https://dair.ai/newsletter/) abone olabilirsiniz.
