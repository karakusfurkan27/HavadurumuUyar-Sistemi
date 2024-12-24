# Hava Durumu Uyarı Sistemi

Bu Python uygulaması, belirli bir şehirdeki hava durumu verilerini OpenWeatherMap API'si üzerinden alır ve belirli hava durumu koşulları (örneğin, düşük sıcaklık veya şiddetli rüzgar) için uyarılar gönderir. Uyarılar, e-posta ile gönderilmektedir.

## Özellikler

- **Hava Durumu Verisi Alımı:** OpenWeatherMap API'si üzerinden şehirdeki hava durumu verilerini alır.
- **E-posta Uyarısı:** Belirli hava durumu koşulları için (düşük sıcaklık, şiddetli rüzgar) e-posta uyarıları gönderir.
- **Otomatik Kontrol:** Hava durumu her belirli bir süre (örneğin, her saat) otomatik olarak kontrol edilir.

## Gereksinimler

- Python 3.x
- `requests` ve `smtplib` modülleri
- OpenWeatherMap API anahtarı (API_KEY)
- Gmail hesabı (e-posta uyarıları için)

## Kurulum

1. **Gerekli Modülleri Yükleyin:**

   Bu uygulama için `requests` modülüne ihtiyacınız var. Bunu yüklemek için terminal veya komut satırında şu komutu çalıştırın:

   ```bash
   pip install requests
   ```

2. **API Anahtarını Alın:**

   OpenWeatherMap API'sinden bir API anahtarı alın. [OpenWeatherMap](https://openweathermap.org/) web sitesine gidip ücretsiz bir hesap oluşturabilirsiniz.

3. **E-posta Hesabınızı Ayarlayın:**

   E-posta uyarıları göndermek için bir Gmail hesabına ihtiyacınız var. `SENDER_EMAIL` ve `SENDER_PASSWORD` değişkenlerini, e-posta adresiniz ve şifrenizle doldurun. Gmail'de, güvenli olmayan uygulama erişimi için izin vermeniz gerekebilir.

4. **Konfigürasyon:**

   - `API_KEY` ile OpenWeatherMap API anahtarınızı girin.
   - `CITY` değişkenini istediğiniz şehirle değiştirin (örneğin: `'Gaziantep'`).
   - `SENDER_EMAIL`, `SENDER_PASSWORD` ve `RECEIVER_EMAIL` değişkenlerini kendi e-posta adreslerinizle ayarlayın.

## Kullanım

1. **Uygulamayı Çalıştırma:**

   Aşağıdaki kodu çalıştırarak hava durumu kontrolünü başlatabilirsiniz:

   ```python
   run_weather_check()
   ```

   Bu kod, hava durumu her belirli bir süre (örneğin, her 1 saatte bir) kontrol eder ve belirli koşullar sağlanırsa e-posta uyarıları gönderir.

2. **Uyarılar:**

   Uygulama, aşağıdaki hava durumu koşullarında uyarı gönderecektir:
   - Sıcaklık 0°C'nin altına düştüğünde "Düşük Sıcaklık Uyarısı".
   - Rüzgar hızı 10 m/s'in üzerine çıktığında "Şiddetli Rüzgar Uyarısı".

## Örnek E-posta Uyarısı

- **Düşük Sıcaklık Uyarısı:**
  - **Konu:** Düşük Sıcaklık Uyarısı
  - **İçerik:** Sıcaklık -2°C'ye düştü. Dışarı çıkarken dikkatli olun!

- **Şiddetli Rüzgar Uyarısı:**
  - **Konu:** Şiddetli Rüzgar Uyarısı
  - **İçerik:** Rüzgar hızı 12 m/s'e ulaştı. Dikkatli olun!

## Uyarılar

- E-posta şifrenizin güvenliği için, şifrenizi doğrudan kodda yazmak yerine çevresel değişkenler veya güvenli bir yapı kullanmanızı öneririz.
- Gmail hesabınızda "Daha Az Güvenli Uygulama Erişimi"ni açmanız gerekebilir. Bunun yerine OAuth 2.0 ile daha güvenli bir yöntem tercih edebilirsiniz.
