#Arduino ve Python ile Etkileşimli Tartı Sistemi

Bu proje, bir Arduino mikrodenetleyici ve bir tartı sensörü (HX711) kullanılarak oluşturulmuş bir sistemdir. Temel amacı, kullanıcıya bir kullanıcı arayüzü üzerinden tartı ölçümleri yapma, kalibrasyon ve dara işlemlerini gerçekleştirme imkanı sunmaktır. Projede Python ve Arduino kodları birlikte çalışarak etkileşimli bir deneyim sağlar.

Proje İşlevselliği:
Tartı Sensörü ve Arduino İletişimi:

Arduino, HX711 kütüphanesi aracılığıyla tartı sensörü ile iletişim kurar.
Sensör, Arduino üzerinden gelen komutlara yanıt verir ve ölçüm sonuçlarını Arduino'ya iletir.
Kalibrasyon:

Kullanıcı, Python arayüzü üzerinden belirli bir kalibrasyon değeri girebilir.
Ardından bu değer, Arduino'ya iletilir ve sensör kalibrasyonu gerçekleştirilir.
Dara Alma:

Python arayüzündeki "Dara" düğmesi, Arduino'ya bir tare komutu gönderir.
Bu işlem, sensör üzerindeki ölçümü sıfırlar.
Sürekli Veri Okuma ve Gösterme:

Python arayüzü, Arduino'dan sürekli olarak gelen ölçüm verilerini okur ve ekranda gösterir.
Kullanıcı, bilgi etiketleri aracılığıyla sürekli olarak sensör durumu hakkında bilgi alabilir.
Bilgi Mesajları:

Kullanıcı, arayüz üzerinden bilgi mesajları alır.
Kalibrasyon tamamlandığında, ağırlıkları kaldırın veya ekleyin gibi yönergeler görüntülenir.
Kullanıcı Arayüzü:
Tkinter kütüphanesi kullanılarak basit bir GUI oluşturulur.
Kullanıcı, kalibrasyon değeri girebilir, kalibrasyon yapabilir ve dara alabilir.
Bilgi etiketleri aracılığıyla kullanıcıya yönergeler ve sonuçlar gösterilir.
Projeyi İlerletme İmkanları:
Proje, kullanıcı arayüzünü geliştirmek veya farklı sensörler eklemek gibi çeşitli yönlere genişletilebilir.
Verilerin kaydedilmesi veya uzaktan erişim gibi özellikler eklenerek projenin işlevselliği artırılabilir.
Bu proje, temel elektronik ve programlama bilgilerini bir araya getirerek kullanıcıya interaktif bir deneyim sunar. Ayrıca, Arduino ve Python'un birlikte çalışarak karmaşık projelerin nasıl oluşturulabileceğine dair bir örnek sunmaktadır.


Bu Python kodu, bir Arduino mikrodenetleyicisi ile seri iletişim kurarak tartı verilerini okuyan ve kullanıcı arayüzü üzerinden kalibrasyon ve dara işlemlerini yöneten bir programı içerir.

#Python Kodu Açıklaması:
Gerekli Kütüphaneler ve Seri Bağlantı:

serial ve tkinter kütüphaneleri kullanıldı.
serial.Serial ile Arduino ile seri bağlantı kuruldu.
Kullanıcı Arayüzü Oluşturma:

tkinter kullanılarak basit bir GUI (Graphical User Interface - Grafiksel Kullanıcı Arayüzü) oluşturuldu.
Kullanıcıya kalibrasyon değeri girmesi için bir giriş kutusu (Entry) sağlandı.
Kalibrasyon ve dara işlemlerini başlatmak için düğmeler (Button) eklendi.
Kalibrasyon Fonksiyonları:

calibration_button_click: Kalibrasyon başlatma işlemini gerçekleştirir.

Girilen kalibrasyon değerini alır ve Arduino'ya gönderir.
Ardından kalibrasyon işlemi devam ederken kullanıcı arayüzünü günceller.
check_calibration_result fonksiyonunu çağırarak kalibrasyon sonuçlarını kontrol eder.
send_tare_command: Arduino'ya tare (sıfırlama) komutu gönderir.

check_calibration_result: Kalibrasyon sonuçlarını kontrol eder.

Arduino'dan gelen verileri okur.
Eğer kalibrasyon tamamlandıysa, bilgi etiketini günceller.
Aksi takdirde, tartı üzerine ağırlık koyun veya kaldırın gibi mesajları görüntüler.
Dara işlemi tamamlandığında ek bir düğme görüntüler.
Veri Okuma ve Güncelleme:

read_and_print_data: Arduino'dan gelen veriyi sürekli olarak okur ve kullanıcı arayüzünü günceller.
Kalibrasyon tamamlandığında veya başka bir özel durumda gerekli mesajları görüntüler.
Belirli aralıklarla bu fonksiyonu tekrar çağırarak sürekli veri güncellemesini sağlar.
Ana Program Döngüsü:

root.mainloop(): Tkinter uygulamasını başlatır ve kullanıcı arayüzünü görüntüler.
Bu kod, Arduino ile etkileşimli bir kullanıcı arayüzü sağlar ve mikrodenetleyiciden gelen verileri izler. Kullanıcılar, kalibrasyon yapabilir, dara alabilir ve bu sırada bilgi mesajlarını görebilirler.
