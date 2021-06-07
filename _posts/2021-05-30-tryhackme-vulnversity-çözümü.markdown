---
layout: post
title: TryHackMe – Vulnversity Çözümü
date: 2021-05-30 00:00:00 +0300
---


----------------------------------------------

Start Machine ile makinemizi başlattık.

![image](/blog/images/vulnversity/1.JPG)
#### Şekil 1.1 Makineyi Başlatma

Task 2 de nmap ile bilgi toplamamızı istemektedir.

![image](/blog/images/vulnversity/2.JPG)
#### Şekil 1.2 Task 2 

Öncelikle aşağıdaki komutu kullanarak versiyon taraması gerçekleştireceğiz.

![image](/blog/images/vulnversity/3.JPG)
#### Şekil 1.3

Tarama sonucunda elde ettiğimiz veriler aşağıdaki gibidir. (Makine IP = 10.10.168.30 (Makinanın her başlatılışında ip adresi değişecektir))

![image](/blog/images/vulnversity/4.JPG)
#### Şekil 1.4 Tarama Çıktısı

Şekil 1.4 ten de görüleceği üzere açık portlarımızın sayıdır 6 adettir.

![image](/blog/images/vulnversity/5.JPG)
#### Şekil 1.5

Squid proxy in versiyon bilgisine de şekil 1.4 te ki taramada gözlemleyebilmekteyiz. (3.*.**)

![image](/blog/images/vulnversity/6.JPG)
#### Şekil 1.6

Bir sonraki soru da ise –p-400 parametresi ile nmap in kaç adet bağlantı noktasını tarayacağını sormaktadır. Bu da –p parametresinden sonra verilen değer kadar noktayı tarayacağından dolayı cevabımız 400 olacaktır.

![image](/blog/images/vulnversity/7.JPG)
#### Şekil 1.7

Bir sonraki soruda ise –n parametresinin neyi çözümlemeyeceği sorulmaktadır. Bu sorunun cevabına ise nmap –help ile ulaşabilmemiz mümkündür.

![image](/blog/images/vulnversity/8.JPG)
#### Şekil 1.8

Şekil 1.8 den de anlaşılacağı üzere bu soruya cevabımız ‘DNS’ dir.

![image](/blog/images/vulnversity/9.JPG)
#### Şekil 1.9

Bir sonraki soruda ise işletim sistemi bilgisini sormaktadır. Bu soru için ise - O parametresini kullanabiliriz.

![image](/blog/images/vulnversity/10.JPG)
#### Şekil 1.10

Çıktımız bize tam olarak işletim sistemi bilgisini verememiş olsada ssh servisinden işletim sistemi bilgimizin ‘Ubuntu’ olduğunu söyleyebilmemiz mümkündür.

![image](/blog/images/vulnversity/11.JPG)
#### Şekil 1.11

Task 2 deki son sorumuz ise web server ın hangi portta çalıştığı ile ilgili. Yine bu sorunun cevabına da Şekil 1.4 te yaptığımız taramadan ulaşabilmekteyiz.

![image](/blog/images/vulnversity/12.JPG)
#### Şekil 1.12

![image](/blog/images/vulnversity/13.JPG)
#### Şekil 1.13

Bir sonraki task ise GoBuster i kullanmaya yönelik.

![image](/blog/images/vulnversity/14.JPG)
#### Şekil 1.14

Bu araç kalide kurulu olarak gelmektedir. Kurulu olmaması durumunda https://github.com/OJ/gobuster adresinden ya da Kali Linux 2020.1 ve üzeri bir sürüm kullanılması durumunda sudo apt-get install gobuster komutu ile kurulumu gerçekletirebilmek mümkündür. 

<a href="https://github.com/OJ/gobuster">Buradan</a>