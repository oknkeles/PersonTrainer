# Antrenman Studio (PT Studio)

Spor salonu için PT randevu uygulaması — mobil-öncelikli, kurulabilir PWA.
Öğrenci, hoca ve salon sahibi rolleri; talep → onay → kota akışı; esnek paket
tanımı (serbest ders adedi + süre) ve yönetici raporları.

**Canlı:** https://oknkeles.github.io/PersonTrainer/

## Roller
- **Öğrenci** — hocalarının boş saatlerini görüp ders talebi açar, kotasını ve
  kullanım geçmişini görür. Talep açılınca dilim kilitlenir.
- **Hoca** — haftalık müsaitliğini yönetir, gelen talepleri onaylar/reddeder,
  yalnızca kendine tanımlı öğrencileri görür (günlük/haftalık takvim).
- **Salon Sahibi** — üye ve paket yönetimi (esnek adet + süre), çoklu hoca
  ataması, raporlar (hoca başına ders, en yoğun saatler, iptal).

## Kurallar
- Talep *oluşturulunca* dilim kilitlenir; hoca reddederse tekrar açılır.
- Onayda öğrencinin kotasından 1 ders düşer.
- Kota = adet + süre; ikisinden biri bitince paket kapanır.
- İptal aynı gün değilse hak iade, aynı günse hak yanar (hoca onayıyla).

## Teknik
- Tek dosya `index.html` (vanilla JS), veriler `localStorage`.
- `sw.js` ile offline/PWA; `main`'e push'ta GitHub Actions ile otomatik yayın.

> Not: Bu bir prototiptir — veriler cihazda yereldir, gerçek çok-kullanıcılı
> senkron ve SMS OTP giriş sonraki aşamada eklenecektir.
