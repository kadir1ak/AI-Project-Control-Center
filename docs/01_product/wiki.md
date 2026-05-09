# Wiki

## Amaç

Wiki, proje dokümantasyonunun yaşayan hafızasıdır.

## İçerik Türleri

- Project overview.
- Setup guide.
- Architecture notes.
- API docs.
- Database docs.
- Decision logs.
- Release notes.
- Developer guide.
- Agent instructions.
- Troubleshooting.

## Kullanım

Wiki hem kullanıcı hem de ajanlar için context kaynağıdır. Ancak ajanlar wiki'yi sınırsız değiştirmemelidir.

## Güncelleme Kuralları

- Küçük açıklama güncellemeleri düşük risklidir.
- Mimari karar, güvenlik kuralı veya çalışma standardı değişiklikleri approval gerektirmelidir.
- Her önemli wiki değişikliği ilgili task veya run ile ilişkilendirilmelidir.

## MVP Davranışı

İlk sürümde wiki markdown dosyaları veya database içinde markdown content olarak tutulabilir.

## Kabul Kriterleri

- Proje bazlı wiki sayfaları listelenir.
- Sayfa içeriği ajan context'ine dahil edilebilir.
- Önemli değişiklikler karar kaydı veya approval ile ilişkilendirilebilir.
