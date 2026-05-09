# Sprint 02: AI Planning

## Amaç

Kullanıcı fikrinden PRD ve backlog üretmek.

## Kapsam

- AI provider abstraction.
- Ideation ekranı.
- PRD generation.
- PRD editor.
- Backlog generation.
- Epic/task kayıtları.

## Micro Task Listesi

| ID | Task | Çıktı | Kabul Kriteri |
| --- | --- | --- | --- |
| PLN-001 | AI provider abstraction tasarla | Provider interface | Provider bağımlılığı controller içine sızmaz |
| PLN-002 | Ideation input ekranını ekle | Fikir giriş formu | Kullanıcı proje fikrini kaydedebilir |
| PLN-003 | PRD prompt template bağla | PRD generation prompt | Çıktı PRD template ile uyumludur |
| PLN-004 | PRD Editor ekle | Markdown editor | PRD düzenlenir ve kaydedilir |
| PLN-005 | Backlog generation prompt ekle | Epic/task JSON draft | PRD'den task taslağı üretilir |
| PLN-006 | Epic/task kayıt akışını ekle | Database kayıtları | Üretilen backlog Kanban'da görünür |
| PLN-007 | Varsayım ve risk alanlarını göster | PRD risk/assumption paneli | Kullanıcı belirsizlikleri görebilir |

## Sprint Sonu Demo

Kullanıcı proje fikri girer; sistem PRD taslağı ve ilk backlog'u üretir.

## Related Documents

- [Ideation](../01_product/ideation.md)
- [PRD Editor](../01_product/prd_editor.md)
- [PRD Template](../06_templates/prd_template.md)
- [Epic Template](../06_templates/epic_template.md)
- [AI Providers](../05_integrations/ai_providers.md)
