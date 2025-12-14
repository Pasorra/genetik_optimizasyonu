# Kimya Tesisi Reaksiyon Optimizasyonu (Senaryo 5)

Bu proje, Genetik Algoritma kullanarak bir kimya tesisindeki reaksiyon süresi ve sıcaklık değerlerini optimize etmekte ve maksimum verimi elde etmektedir.

## Proje Hakkında

Kimyasal üretim süreçlerinde reaksiyon verimi, sıcaklık ve süre parametrelerine bağlı olarak değişmektedir. Bu projede, belirlenen matematiksel model ve kısıtlar çerçevesinde en yüksek verimi sağlayan parametreler evrimsel hesaplama yöntemleriyle bulunmuştur.

  * **Yöntem:** Genetik Algoritma (Turnuva Seçimi, Tek Noktalı Çaprazlama, Gaussian Mutasyon)
  * **Dil:** Python (NumPy, Matplotlib)

## Matematiksel Model (Senaryo 5)

**Amaç Fonksiyonu (Verim):**
$$f(x_1, x_2) = 8x_1 + 3x_2 - x_1x_2 + x_1^2$$

**Değişkenler:**

  * $x_1$: Reaksiyon Süresi (dk) $[10, 60]$
  * $x_2$: Sıcaklık (°C) $[40, 120]$

**Kısıtlar:**

1.  $x_1 + x_2 \le 140$
2.  $x_2 \ge 60$

## Algoritma Parametreleri

Projede kullanılan hiper-parametreler, deneysel çalışmalar sonucunda yakınsama (convergence) ve çeşitlilik (diversity) dengesi gözetilerek seçilmiştir:

| Parametre | Değer | Açıklama |
| :--- | :--- | :--- |
| **Popülasyon Boyutu** | 50 | Genetik çeşitlilik için optimize edildi. |
| **Nesil Sayısı** | 100 | Kararlı sonuçlar (stability) için seçildi. |
| **Çaprazlama Oranı** | 0.8 | **Popülasyonun %80'i genetik bilgi takası yapar.** |
| **Mutasyon Oranı** | 0.1 | Yerel tuzaklardan kaçış için %10 şans. |
| **Mutasyon Büyüklüğü** | 0.5 | Gaussian dağılım ile hassas ayar (fine-tuning). |
| **Elitizm** | 2 | En iyi 2 birey bozulmadan sonraki nesle aktarılır. |
| **Tolerans (Epsilon)** | 1e-9 | Kayan nokta hatalarını önlemek için. |

## Sonuçlar

Algoritma 100 nesil sonunda global maksimum noktasına başarıyla ulaşmıştır.

  * **Optimal Süre ($x_1$):** `60.00 dk`
  * **Optimal Sıcaklık ($x_2$):** `60.00 °C`
  * **Maksimum Verim:** `660.00`

### Yakınsama Grafiği

Algoritmanın adım adım optimum noktaya ulaşması not defteri içerisindeki grafiklerde detaylandırılmıştır. Ortalama uygunluk değeri, ceza fonksiyonu sayesinde ilk nesillerde negatif başlasa da, 10. nesil civarında optimum seviyeye oturmaktadır.
