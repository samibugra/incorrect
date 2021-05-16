# incorrect




#grafiğin tahsilat sütunun tüm değerlerine göre değil yalnızca ilk 20
#değerine göre oluşmasını istiyorum [1:20] notasyonu kullanarak oluşturmaya
#çalıştım ama grafiği çizmedi. notasyonu kaldırınca ise çiziyor.
#o notasyon farklı bir şekilde mi kullanmam gerekiyor?

verri %>%
  ggplot(aes(x = Tahsilat_2019[1:20], y = Tahsilat_2020[1:20])) +
  geom_point() +
  geom_smooth() +
  scale_x_continuous("abc") +
  scale_y_continuous("def")




#bu grafikte de notasyon kullanınca grafiği çizmiyor.
#notasyon kullanmayınca ise gelirin_çeşidi sütunu karakter değişken olduğundan
#okunmayacak şekilde ortaya çıkıyor. o yüzden ilk on değişkene göre 
#oluşturmak istiyorum. karakter değişken bu grafik için pek uygun olmasa da 
#sorunu anlamak için iyi bir örnek olduğunu düşünüyorum. sayısal değişken için de
#aynı sorun oluşuyor malesef.


library(ggplot2)
library(hrbrthemes)
ggplot(verri, aes(verri$Tahsilat_2020[1:10],verri$Gelirin_cesidi[1:10])) +
  geom_area( fill="#69b3a2", alpha=0.4) +
  geom_line(color="#69b3a2", size=2) +
  geom_point(size=3, color="#69b3a2") +
  theme_ipsum() +
  ggtitle("VERGİ GELİRLERİ TAHSİLATI")
  
  
  
  