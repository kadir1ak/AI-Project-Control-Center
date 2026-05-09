# Project Status

## Current Phase

Documentation Architecture / MVP Planning

## Current Goal

Dokümantasyonu geliştirilebilir MVP şartnamesine dönüştürmek.

## Completed

- Ana ürün vizyonu dokümante edildi.
- Orijinal uzun plan arşivlendi.
- `docs/00_overview` ile `docs/08_business` arası bilgi tabanı oluşturuldu.
- README proje giriş noktası olarak hazırlandı.
- Execution, UI ve API dokümantasyon klasörleri eklendi.
- State machine, agent output contracts, sandbox design, audit logging ve command policy ayrıştırıldı.

## In Progress

- MVP execution order ve sprint dokümantasyonu olgunlaştırılıyor.
- UI ekran spesifikasyonları netleştiriliyor.
- API endpoint sözleşmeleri ilk taslak haline getiriliyor.
- Agent output contract doğrulama kuralları tanımlanıyor.

## Next Milestone

MVP implementation planının geliştiriciye doğrudan verilebilir seviyeye getirilmesi:

1. Veri modeli ve API sözleşmelerini netleştirmek.
2. UI ekranlarını MVP/sonra ayrımıyla kesinleştirmek.
3. Command policy ve sandbox yaklaşımını implementation öncesi kontrol etmek.
4. İlk scaffold için ayrı uygulama planı hazırlamak.

## Open Questions

- İlk implementation stack'i kesin olarak .NET 8 mi .NET 9 mu olacak?
- Worker runtime .NET Worker Service ile mi başlayacak, yoksa Node/Python bridge mi kullanılacak?
- AI provider entegrasyonunda ilk MVP provider sırası ne olacak?
- GitHub MCP ilk sürümde read-only mi, PR hazırlama seviyesinde mi kullanılacak?
- Terminal ekranı MVP'de command input alacak mı, yoksa sadece read-only log stream mi olacak?

## Risk Notes

- Scope creep riski: ürün aynı anda Kanban, IDE, terminal, multi-agent OS ve SaaS platformu olmaya çalışmamalı.
- Güvenlik riski: terminal komutları host üzerinde direkt çalıştırılmamalı.
- Audit riski: AI ve worker işlemleri loglanmazsa ürün güvenilir operasyon paneli olamaz.
- Ürün riski: ilk kullanıcı deneyimi çok karmaşık olursa değer netleşmez.
- Teknik risk: prompt ve agent output contract standardı olmazsa run sonuçları makine tarafından işlenemez.
