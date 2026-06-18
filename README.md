# Deney Tasarımı Analizleri

Çeşitli deneysel tasarım türlerinin R ile ANOVA analizleri. Altı farklı tasarım problemi, hem elle (adım adım kareler toplamı hesaplarıyla) hem de R'ın `aov()` fonksiyonu ile çözülerek karşılaştırmalı olarak incelenmiştir.

## İçerik

Her bölümde ilgili tasarımın problem tanımı, istatistiksel modeli ve hipotezleri verilmiş; ardından ANOVA tablosu önce manuel olarak (satır/sütun/muamele toplamları ve kareler toplamları üzerinden) hesaplanmış, sonra R fonksiyonlarıyla doğrulanmıştır. Uygun yerlerde TukeyHSD ile çoklu karşılaştırma ve Shapiro-Wilk ile normallik kontrolü yapılmıştır.

| Bölüm | Tasarım |
|-------|---------|
| 1 | İki faktörlü tekrarlı faktöriyel deney (etkileşimli iki yönlü ANOVA) |
| 2 | Greko-Latin kare tasarımı |
| 3 | Latin kare tasarımı (5×5) |
| 4 | İki faktörlü faktöriyel deney |
| 5 | Greko-Latin kare tasarımı |
| 6 | Latin kare tasarımı (5×5) |

## Yöntem

- ANOVA tablolarının elle hesaplanması (KT, KO, SD ve F değerleri)
- Sonuçların R `aov()` ve `summary()` fonksiyonlarıyla doğrulanması
- Çoklu karşılaştırma için `TukeyHSD`
- Normallik varsayımının `shapiro.test` ile kontrolü
- Latin/Greko-Latin kare tasarımlarında ortogonallik ve denge kontrolleri

## Dosyalar

- `experimental-design-anova.rmd.Rmd` — R Markdown kaynak dosyası
- `experimental-design-anova.pdf` — Derlenmiş (render edilmiş) çıktı

## Çalıştırma

R ve RStudio gerektirir. Kaynak dosyayı açıp derlemek için:

```r
# Gerekli paket (PDF derlemesi icin)
install.packages("rmarkdown")

# Derleme (XeLaTeX gerektirir)
rmarkdown::render("experimental-design-anova.rmd.Rmd")
```

PDF çıktısı `xelatex` ile derlenmektedir; sisteminizde bir LaTeX dağıtımı (örn. TinyTeX veya MiKTeX) kurulu olmalıdır.

## Kullanılan Kütüphaneler

`stats` (aov, TukeyHSD, shapiro.test) · `knitr` · `rmarkdown`
