# GitHub MCP

## Amaç

GitHub MCP Server, AI araçlarının GitHub repository, issue, pull request ve workflow verilerine kontrollü erişmesini sağlar.

## Kullanım Senaryoları

- Repository dosyalarını okuma.
- Issue ve PR inceleme.
- Kod değişikliklerini analiz etme.
- PR açıklaması hazırlama.
- Review yorumlarını özetleme.
- CI sonuçlarını yorumlama.
- Backlog tasklarını GitHub issue'larına bağlama.

## Ürün İçindeki Rolü

GitHub MCP, Agentic Project Control Center için entegrasyon katmanıdır. Ana ürün verisi yine kendi backend'inde tutulur; GitHub kaynak kontrol ve iş birliği sistemi olarak bağlanır.

## Güvenlik Politikası

- Read işlemleri düşük risklidir.
- Branch oluşturma orta risklidir.
- PR açma approval gerektirebilir.
- Main branch'e push veya merge her zaman approval gerektirir.
- Secret, token ve workflow permission ayarları otomatik değiştirilmemelidir.

## MVP Kullanımı

İlk sürümde GitHub MCP için hedef:

- Repo bağlama.
- Dosya ve diff okuma.
- PR hazırlık özeti üretme.
- GitHub issue/task eşleştirme planı.

PR merge ve production workflow tetikleme sonraki faza bırakılmalıdır.

## Veri Eşleştirme

```text
Project -> Repository
Task -> GitHub Issue
AgentRun -> PR Comment / Check Summary
Approval -> Protected Action
CommandLog -> CI/Local Run Evidence
```
