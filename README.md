# 📦 Kargo Kutusu Boyut Optimizasyonu - Genetik Algoritma

Bu proje, bir e-ticaret firmasının ürünleri için kullanacağı **en uygun (optimum) kargo kutusu boyutlarını** belirlemek amacıyla geliştirilmiş bir yapay zeka uygulamasıdır. Çözüm yöntemi olarak **Genetik Algoritma (GA)** kullanılmıştır.

Amaç; belirli malzeme maliyeti ve hacim kısıtlarını dikkate alarak **kârı maksimize eden** genişlik ($x_1$) ve yükseklik ($x_2$) değerlerini bulmaktır.

## 🧮 Matematiksel Model

Proje, aşağıdaki amaç fonksiyonunu maksimize etmeye çalışır:

### 1. Amaç Fonksiyonu (Objective Function)
$$y = (x_1 \cdot x_2) - 0.1 \cdot x_1^2 - 0.1 \cdot x_2^2$$

Burada:
* $y$: Başarı puanı (Kâr/Verimlilik)
* $x_1$: Kutunun Genişliği (cm)
* $x_2$: Kutunun Yüksekliği (cm)

### 2. Değişken Sınırları (Bounds)
* **Genişlik ($x_1$):** $10 \le x_1 \le 40$
* **Yükseklik ($x_2$):** $5 \le x_2 \le 20$

### 3. Kısıtlar (Constraints)
Genetik algoritma aşağıdaki kısıtları ihlal eden bireylere **ceza puanı (Penalty)** uygular:
* **Alan Kısıtı:** $x_1 \cdot x_2 \le 600$ (Raf sığdırma sınırı)
* **Alt Sınır Kısıtı:** $x_1 \ge 15$

---

## 🧬 Algoritma Detayları

Bu projede kullanılan Genetik Algoritma parametreleri ve yöntemleri şunlardır:

* **Popülasyon Büyüklüğü:** 50 Birey
* **Nesil Sayısı (Iterations):** 100
* **Seçilim Yöntemi (Selection):** Turnuva Seçimi (Tournament Selection)
* **Çaprazlama (Crossover):** Aritmetik Çaprazlama (Ebeveynlerin ağırlıklı ortalaması)
* **Mutasyon (Mutation):** Rastgele değer ekleme (Sınır kontrolü ile birlikte, Oran: %10)
* **Elitizm:** Her neslin en iyi 2 bireyi bozulmadan sonraki nesle aktarılır.

---

## 🚀 Kurulum ve Çalıştırma

Bu projeyi kendi bilgisayarınızda çalıştırmak için aşağıdaki adımları izleyebilirsiniz.

### Gereksinimler
Proje **Python 3** ile geliştirilmiştir ve aşağıdaki kütüphanelere ihtiyaç duyar:
* `numpy`
* `matplotlib`

### Kurulum
Gerekli kütüphaneleri yüklemek için terminalde şu kodu çalıştırın:

```bash
pip install numpy matplotlib
