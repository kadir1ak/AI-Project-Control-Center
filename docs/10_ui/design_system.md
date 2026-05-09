# Design System

## UI Prensipleri

- Operasyon paneli hissi vermeli; gereksiz marketing hero yaklaşımından kaçınılmalı.
- Bilgi yoğun ama taranabilir olmalı.
- Task, run, approval ve log durumları net ayrışmalı.
- Riskli aksiyonlar görsel olarak sakin ama belirgin uyarılmalı.
- Her ekran empty/loading/error state içermeli.

## Renk ve Durum Mantığı

- `success`: tamamlandı, test geçti, approval onaylandı.
- `warning`: bekliyor, attention gerekiyor, approval pending.
- `danger`: failed, blocked, high risk, rejected.
- `neutral`: draft, queued, read-only, archived.

## Status Badge Kuralları

- Badge metni kısa olmalı.
- Renk tek başına anlam taşımasın; metin de durumu anlatmalı.
- Status değerleri state machine ile uyumlu olmalı.

## Risk Badge Kuralları

- Low: neutral veya success ton.
- Medium: warning.
- High: danger.
- Critical: danger + explicit confirmation.

## Empty/Loading/Error Standardı

- Empty state kullanıcıya sonraki aksiyonu söyler.
- Loading state layout shift yaratmamalı.
- Error state retry ve kısa teknik özet içermeli.

## Copywriting Tonu

- Kısa.
- Operasyonel.
- Karar odaklı.
- Belirsizliği saklamayan.
- Kullanıcıyı gereksiz korkutmayan.

## Log ve Terminal Görünüm Prensipleri

- Monospace font.
- Timestamp görünür.
- stdout/stderr ayrımı yapılabilir.
- Riskli komutlar log içinde badge ile işaretlenir.
- Secret değerleri maskelenir.

## Related Documents

- [Navigation Structure](navigation_structure.md)
- [State Machine](../03_operations/state_machine.md)
- [Command Policy](../03_operations/command_policy.md)
- [Security Model](../02_architecture/security_model.md)
