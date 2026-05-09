# Claude Skills and Plugins

## Amaç

Claude Skills ve benzeri agent skill/plugin yapıları, belirli görevler için tekrar kullanılabilir uzmanlık paketleri sağlar.

## Ürün İçindeki Rolü

Bu sistemde skills yapısı, ajan profillerinin genişletilebilir bilgi ve işlem paketleri olarak konumlandırılmalıdır.

Örnek skill türleri:

- PRD writing.
- API design.
- Security review.
- DevOps checklist.
- Compliance review.
- Marketing copy.
- QA planning.

## Skill Yapısı

Bir skill paketi şunları içerebilir:

- Talimat dosyası.
- Örnek promptlar.
- Kontrol listeleri.
- Scriptler.
- Referans dokümanlar.
- Output formatları.

## Kullanım Kuralları

- Skill, ajan rolünün yerine geçmez; rolü güçlendirir.
- Skill seçimi task türüne göre yapılır.
- Güvenlik veya terminal yetkisi skill üzerinden otomatik verilmez.
- Skill çıktı formatı Agent Runner tarafından kayıt altına alınmalıdır.

## MVP Yaklaşımı

İlk aşamada skills sistemi marketplace gibi yapılmamalıdır.

MVP için yeterli olan:

- Skill registry dokümanı.
- Ajan profiline bağlı skill listesi.
- Prompt template içinde skill talimatı.
- Output format standardı.

## Örnek

```text
Agent: Architect Agent
Skill: SaaS Architecture Review
Purpose: PRD'den modül, database, API ve deployment kararları çıkarmak.
Output: Architecture summary + ADR candidates + risks.
```
