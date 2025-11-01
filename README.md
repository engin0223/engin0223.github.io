---

# 📊 KTÜ Not Hesaplayıcı (İstatistiksel Değerlendirme)

[![GitHub Pages'da Görüntüle](https://img.shields.io/badge/GitHub%20Pages-Live-blue?logo=github)](https://engin0223.github.io/ktuharfnotu/)

## Projeye Genel Bakış

Bu proje, **Next.js + TypeScript** ile geliştirilmiş bir **istatistiksel not hesaplayıcıdır**.
Karadeniz Teknik Üniversitesi (KTÜ) notlandırma yönetmeliklerini uygular ve sınıf sınav dağılımlarına dayanarak öğrenci harf notlarını tahmin etmek için istatistiksel yöntemler kullanır.

Uygulama:

* Vize ve final sınav özet istatistiklerini (ortalama, standart sapma) girdi olarak alır
* Vize ve final arasındaki korelasyon katsayısını $p$’yi hesaplar ve kullanır
* Ağırlıklı ders notunu (HBN) ve dağılımını hesaplar
* KTÜ değerlendirme kurallarını uygular (T-puanı yöntemi, mutlak yöntem, fakülteye özgü final eşikleri)

> **Not:** Uygulama **GitHub Pages** üzerinde ücretsiz olarak barındırılmaktadır.

---

## Matematiksel Türetme (HBN Ortalaması ve Varyansı)

Bu bölüm, uygulamada kullanılan matematiksel formülleri adım adım açıklar ve HBN (Harfli Başarı Notu) hesaplamasının temelini gösterir.

### Notasyon

* $X$ : Vize notu rastgele değişkeni (sınıf dağılımı)
  Ortalama: $\mu_X$, Standart sapma: $\sigma_X$, Varyans: $\mathrm{Var}(X) = \sigma_X^2$
* $Y$ : Final notu rastgele değişkeni (sınıf dağılımı)
  Ortalama: $\mu_Y$, Standart sapma: $\sigma_Y$, Varyans: $\mathrm{Var}(Y) = \sigma_Y^2$
* $p$ : $X$ ve $Y$ arasındaki Pearson korelasyon katsayısı, $p \in [-1,1]$
  Kovaryans: $\mathrm{Cov}(X,Y)$
* Ders ağırlıkları: $w_1$ (vize), $w_2$ (final). Varsayılan: $w_1 = w_2 = 0.5$

---

### 1️⃣ Ağırlıklı Ders Puanı (HBN)

$$
H = w_1 X + w_2 Y
$$

---

### 2️⃣ HBN Ortalaması

$$
\mu_H = w_1 \mu_X + w_2 \mu_Y
$$

> HBN’nin beklenen değeri, vize ve finalin ağırlıklı ortalamasıdır.

---

### 3️⃣ HBN Varyansı

$$
\mathrm{Var}(H) = w_1^2 \sigma_X^2 + w_2^2 \sigma_Y^2 + 2 w_1 w_2 p , \sigma_X \sigma_Y
$$

$$
\sigma_H = \sqrt{\mathrm{Var}(H)}
$$

> Bu formül, hem öğrencinin hem de sınıfın HBN dağılımını doğru şekilde tahmin eder.

---

## Özellikler

* 📐 **İstatistiksel Hesaplama:** Korelasyon kullanarak tam HBN ortalaması ve varyans hesaplaması
* 🎓 **Harf Notu Tahmini:** T-puan sistemi veya mutlak notlandırma yöntemi
* 🖥️ **Etkileşimli Kullanıcı Arayüzü:** React + Tailwind CSS ile modern tasarım
* 🌐 **GitHub Pages Yayını:** Ek sunucu gerekmeden ücretsiz ve hızlı erişim
* 🔒 **Fakülte Kuralları:** Bölüm bazlı final eşiği yapılandırması

---

## Teknoloji Yığını

* Next.js (React + TypeScript)
* Tailwind CSS
* GitHub Pages (statik barındırma)
* npm / yarn / pnpm / bun uyumlu

---
