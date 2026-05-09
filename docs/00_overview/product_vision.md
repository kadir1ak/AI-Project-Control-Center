# Product Vision

## Amaç

Agentic Project Control Center, yazılım projelerini fikir aşamasından uygulanabilir geliştirme planına kadar sistematik hale getiren web tabanlı bir AI operasyon merkezidir.

Ürün; PRD, mimari kararlar, backlog, mikro tasklar, ajan görevleri, prompt paketleri, terminal logları ve approval kayıtlarını tek bir yönetim alanında toplar.

## Vizyon Cümlesi

Bir yazılım fikrini alıp, insan onaylı ve izlenebilir bir süreçle planlayan, tasklara bölen, ajanlara yönlendiren ve kontrollü terminal worker ile uygulanabilir hale getiren AI-native geliştirme konsolu.

## Çözülen Problem

Mevcut AI araçları güçlüdür ama proje yönetimi açısından dağınıktır:

- Planlama, kodlama, terminal ve dokümantasyon farklı yerlerde kalır.
- Ajan çıktıları kalıcı proje hafızasına dönüşmez.
- Hangi kararın neden alındığı izlenemez.
- Terminal komutları ve dosya işlemleri güvenli bir approval zincirinden geçmez.
- AI ile yapılan iş tekrar üretilebilir ve denetlenebilir değildir.

## Ürün Formülü

```text
Web UI
+ Planning Console
+ Backlog Board
+ Agent Runner
+ Prompt Engine
+ Approval Center
+ Terminal Worker Logs
+ Context and Wiki
```

## İlk Ürün İlkesi

MVP, tam otonom kod fabrikası değil; **AI destekli yarı otonom planlama ve operasyon konsolu** olmalıdır.

Sistem önce plan üretir, sonra task üretir, sonra ajanlara iş paketi verir, sonra worker çıktısını kaydeder.

## Başarı Tanımı

İlk başarılı sürümde kullanıcı:

- Bir proje fikri girer.
- Sistem PRD ve teknik kapsam üretir.
- Sistem epic ve taskları çıkarır.
- Her task için uygulanabilir prompt paketi üretir.
- Ajan çalışmasını ve onay ihtiyacını izler.
- Terminal/worker loglarını kayıtlı görür.

## Kapsam Dışı

İlk sürümde şu hedeflenmez:

- Tam otonom production deploy.
- Geniş enterprise rol yönetimi.
- Marketplace.
- Kendi IDE editörünü sıfırdan yapmak.
- Çok karmaşık multi-agent framework bağımlılığı.
