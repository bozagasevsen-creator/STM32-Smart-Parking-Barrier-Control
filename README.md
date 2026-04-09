# STM32 Akıllı Park Bariyeri Kontrolü

## Proje Tanımı
Bu proje, STM32F072 mikrodenetleyici kullanılarak geliştirilmiş akıllı park bariyeri kontrol sistemidir.

Sistem aşağıdaki işlevleri yerine getirir:
- Otoparka giriş yapan araçları sayar
- Otoparktan çıkan araçları sayar
- Maksimum araç kapasitesini kontrol eder
- Servo motor ile bariyeri açıp kapatır
- Acil durum butonu ile bariyeri güvenli konuma getirir
- UART üzerinden durum mesajları gönderir

## Kullanılan Donanımlar
- STM32F072RB
- Servo motor
- Giriş sensörü / butonu
- Çıkış sensörü / butonu
- Acil durum butonu
- UART haberleşmesi için bilgisayar/terminal

## Kullanılan Çevre Birimleri
- GPIO
- EXTI
- TIM1 PWM
- TIM2 Timer Interrupt
- USART1 UART

## Çalışma Mantığı
- Araç giriş pini tetiklendiğinde araç sayısı 1 artar ve bariyer açılır.
- Araç çıkış pini tetiklendiğinde araç sayısı 1 azalır ve bariyer açılır.
- Otopark doluysa yeni girişe izin verilmez.
- Acil durum butonuna basıldığında sistem bariyeri kapatır.
- Sistem belirli aralıklarla UART üzerinden araç sayısını bildirir.

## Pin Yapısı
- PA0 -> ACIL_BUTTON
- PA1 -> GIRIS
- PA2 -> CIKIS
- PA8 -> TIM1_CH1 (Servo PWM)
- PA9 -> USART1_TX
- PA10 -> USART1_RX

## Proje Dosyaları
- `Çekirdek/` : Ana uygulama dosyaları
- `Sürücüler/` : HAL ve CMSIS sürücü dosyaları
- `akilli_otoparkArac.ioc` : CubeMX yapılandırma dosyası

## Amaç
Bu proje, gömülü sistemlerde GPIO, interrupt, PWM, timer ve UART kullanımını gerçek bir uygulama üzerinden göstermek amacıyla geliştirilmiştir.
##  Future Improvements
- LCD display for vehicle count
- Mobile app integration
- RFID card access system
- IoT monitoring via WiFi

##  Skills Demonstrated
- Embedded C (STM32 HAL)
- GPIO & EXTI Interrupts
- PWM (Servo Control)
- Timer-based scheduling
- UART Communication
