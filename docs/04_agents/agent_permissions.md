# Agent Permissions

## Amaç

Agent permissions, her rolün ne yapabileceğini ve ne zaman approval gerektiğini tanımlar.

## Yetki Matrisi

| Rol | Plan | Context Oku | Dosya Oku | Dosya Yaz | Komut Çalıştır | Approval İsteyebilir |
| --- | --- | --- | --- | --- | --- | --- |
| Planner | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Product Owner | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Architect | Evet | Evet | Evet | Doküman | Hayır | Evet |
| Developer | Evet | Evet | Evet | Evet | Güvenli | Evet |
| QA / Reviewer | Evet | Evet | Evet | Rapor | Test | Evet |

## Approval Gerektiren Durumlar

- Dosya silme.
- Migration.
- Paket yükleme.
- Production etkisi.
- Secret/env değişikliği.
- Git push main.
- PR merge.
- Worker sandbox dışına çıkma isteği.

## Bloklanacak Durumlar

- Host sistem dosyalarına erişim.
- Proje klasörü dışına yazma.
- Gizli bilgileri prompt veya log içine koyma.
- Onaysız production deploy.
- Onaysız destructive database işlemi.

## MVP Varsayılanı

MVP'de tüm ajanlar `Plan`, `Context Oku` ve `Prompt Üret` seviyesinde çalışabilir. Dosya yazma ve komut çalıştırma sadece controlled worker üzerinden yapılır.
