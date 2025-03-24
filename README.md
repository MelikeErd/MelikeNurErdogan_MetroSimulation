# Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)
## Proje Hakkında

Bu proje, bir metro ağı içerisinde iki istasyon arasındaki en az aktarmalı ve en hızlı rotayı bulmak için geliştirilmiş bir simülasyondur. 
Breadth-First Search (BFS) algoritması en az aktarmalı rota için, A* algoritması ise en hızlı rota için kullanılmaktadır. 
Proje, farklı metro hatları ve aktarma noktalarını içeren bir ağ yapısı oluşturarak gerçek hayattaki metro sistemlerinin simüle edilmesini amaçlamaktadır.


## Kullanılan Teknolojiler ve Kütüphaneler

Bu projede aşağıdaki Python kütüphaneleri kullanılmıştır:

* collections.defaultdict: Metro hatları ve istasyonların birbirleriyle ilişkili bir şekilde saklanması için kullanılmıştır.

* collections.deque: BFS algoritmasında kuyruk veri yapısını kullanarak en az aktarmalı rotayı bulmak için kullanılmıştır.

* heapq: A* algoritmasında öncelikli kuyruk kullanarak en hızlı rotayı bulmak için kullanılmıştır.

* typing: Kodun okunabilirliğini arttırmak için veri tipleri tanımlanırken kullanılmıştır.

## Kullanılan Algoritmalar

### BFS Algoritma Çalışma Mantığı

[Breadth-First Search (BFS) algoritması](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/), metro sisteminde en az aktarmalı rotayı bulmak için kullanılmıştır. 
Algoritma, bir kuyruk yapısı kullanarak başlangıç noktasından itibaren istasyonları keşfederek hedef istasyona en az durak sayısıyla ulaşmayı amaçlar. 
Her tekrar çalıştırmada kuyruğun başındaki istasyonun komşu istasyonları incelenir ve daha önce rotaya dahil edilmemiş olanlar kuyruğa eklenir.

### A* Algoritma Çalışma Mantığı

[A* algoritması](https://www.redblobgames.com/pathfinding/a-star/introduction.html), metro sisteminde en hızlı rotayı bulmak için kullanılmıştır. Bu algoritma, bir öncelikli kuyruk (heapq) kullanarak en kısa süreli rotayı bulur. 
Her tekrar çalıştırmada en düşük maliyetli (toplam süre bazlı) rota genişletilerek hedef istasyona ulaşılır. 
Algoritma, en hızlı rotayı bulabilmek için daha önce rotaya dahil edilmemiş olan istasyonların toplam sürelerini takip eder ve daha kısa sürede ulaşılabilecek bir yol bulduğunda eski yollardan vazgeçer.

### BFS ve A* Algoritmalarını Kullanma Nedenleri

* BFS, metro ağında en az aktarmayla varılacak rotaları belirlemek için en uygun algoritmalardan biridir, çünkü seviyelere göre tarama yaparak en kısa aktarmayı bulur.

* A*, zamana dayalı en iyi rotayı bulmak için tercih edilmiştir. A* algoritması, maliyet bazlı hesaplama yaptığından en kısa süreli yolu bulmada daha etkilidir.

## Örnek Kullanım ve Test Sonuçları

Kod, aşağıdaki test senaryolarını içermektedir:

### Senaryo 1: AŞTİ'den OSB'ye

* En az aktarmalı rota: AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB
* En hızlı rota (19 dakika): AŞTİ -> Kızılay -> Demetevler -> OSB

### Senaryo 2: Batıkent'ten Keçiören'e

* En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
* En hızlı rota (21 dakika): Batıkent -> Demetevler -> Gar -> Keçiören

### Senaryo 3: Keçiören'den AŞTİ'ye

* En az aktarmalı rota: Keçiören -> Gar -> Sıhhiye -> Kızılay -> AŞTİ
* En hızlı rota (16 dakika): Keçiören -> Gar -> Kızılay -> AŞTİ

## Projeyi Geliştirme Fikirleri

Projeye belirli eklentiler yapılarak gerçek hayat ile daha fazla benzeşen bir simülasyon yaratılabilir. Bunlara örnek olarak:

* Harita Uygulamaları ile Entegrasyon: Metro hatları ile şehiriçi farklı ulaşım araçlarının verileri birleştirilerek genelgeçer bir navigasyon uygulaması geliştirilebilir.

* Yolcu Tercihlerinin Gösterilmesi: Yolcunun tercihine göre en az aktarmalı ve en kısa süreli yol algoritmalarını birleştirip optimize eden yeni bir algoritma geliştirilebilir.

* İstasyon Yoğunluğu: Turnike sistemine entegre edilecek bir sayaç veya kamera verileri ile oluşturulacak metro istasyonlarının yoğunluk verisi kullanılarak rotalar optimize edilebilir.

* Dinamik Trafik Durumu: Akşam ve sabah gibi yoğun saatlerde metro hatlarının gecikmelerini hesaba katan bir sistem entegre edilebilir.
