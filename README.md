# Spam Filter

## Giriş

Bu proje aşağıdaki kişiler tarafından yapılmıştır.

Yusuf YILDIRIM
Tamer Sertaç GÜNEŞ
Rafet AKKAYA

## Giriş

Bu projede, ling-spam veri seti üzerinde Naïve Bayes ve SVM tabanlı bir sınıflandırma kullanarak bir e-posta spam filtresi tasarlayacağız.

## Veriset

Ling-spam corpus, Linguist eposta listesi yasal veya istenmeyen e-postalar olarak sınıflandırılan e-postaları içerir. Korpus, lemmatizasyonlu/olmayan ve stop-word kaldırmalı/kaldırmasız önceden işlenmiş aynı e-postaları içeren dört alt klasöre bölünmüştür. Her alt klasördeki e-postalar 10 "kısma" bölünmüştür.

Bu projede, ling-spam corpus (lemm_stop klasörü, hem lemmatizasyon hem de stop-word etkinleştirilmiş) ilk 9 katını eğitim verisi olarak ve 10. katını test verisi olarak kullanacağız.

Tüm ling-spam veri kümesini buradan indirin [link](http://www.aueb.gr/users/ion/data/lingspam_public.tar.gz ).

10 alt klasörden her biri, her dosyada bir eposta olmak üzere hem spam hem de yasal epostalar içerir. Adları spmsg*.txt biçiminde olan dosyalar spam iletilerdir. Diğer tüm dosyalar yasal mesajlardır.

## Öznitelik Seçimi

Özellik seçimi, bilgi kazancı (IG) metriği kullanılarak gerçekleştirilir. Eğitim verilerinden, N = {10, 100, 1000} için en iyi N özelliği seçin. IG metriğine dayalı özellik seçiminin, veri kümesinde yalnızca terimlerin ortaya çıkışını (ve terimlerin görünme sıklığını değil) hesaba kattığını unutmayın.

## Sınıflandırıcılar

Jupyter not defterinde `spam_filter.ipynb`, 5 farklı sınıflandırıcı uygulanmıştır.

E-posta spam filtrelerinin bir listesi:

*  Naive Bayes Classifier
  * Bernoulli NB classiﬁer with binary features
  * Multinomial NB with binary features
  * Multinomial NB with term frequency (TF) features
* SVM based Classifier
* Adversarial Classification

Son sınıflandırıcı olan "Adversarial Classifier", temel bir NB filtresinden kaçmaya çalışan saldırılara yanıt olarak NB tabanlı e-posta spam filtrelerini güncelleme yaklaşımıdır. Çalışma kaynağı: [paper](https://dl.acm.org/doi/10.1145/1014052.1014066).