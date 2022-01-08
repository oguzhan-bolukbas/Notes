A highly available system has the ability to instantly redirect requests to a backup system if a component fails.

High Availability : Türkçe karşılığı olarak “Yüksek Erişebilirlik” olarak çevirebiliriz. Çalışmış olduğumuz uygulamalarımızı, servislerimizi birden fazla server üzerine yayarak, herhangi bir server üzerinde oluşabilecek hatadan dolayı , çalışan sistemin etkilenmemesi için kullanılmaktadır.

HA seviyesine sahip sistemler aşağıdaki üç karakteristik özelliği barındırmalıdır.

1 - Redundancy
2 - Monitoring
3 - Failover

HA sistemler genellikle ihtiyaç duyulandan fazla bileşene sahiptirler. Bu bileşenlerin durumları sürekli izlenerek ( monitoring ) bir problem olması durumunda, problemli bileşenin görevi reduntant ( ihtiyaç fazlası ) olan bileşene devredilir.

Redundancy : Bir sistem içerisinde aynı işleve sahip bileşenlerin gereğinden fazla bulunması. Örneğin birden fazla veritabanı server'ı olduğunda serverlardan birinde bir problem çıktığında diğer veritabanı server'ı gelen istekleri yanıtlayabilir. Bu tarz sistemlerde replication (tüm sistemlerin aynı veriye sahip olmasının sağlanması) kritiktir. Tüm veritabanları aynı veriye sahip olmalıdır. 

Monitoring & Failover 

HA sistemler sürekli olarak bileşenlerin durumunu izlemelidir. Bir problem durumunda yedekte bulunan bileşenin birincil (aktif) bileşen durumuna geçmesi failover olarak adlandırılır.
