# Definition of Done

## Genel DoD

Bir task `Done` sayılmadan önce:

- Acceptance criteria karşılanmış olmalı.
- Değişiklik task scope içinde kalmalı.
- Test veya validation sonucu yazılmalı.
- Risk ve açık soru varsa kaydedilmeli.
- İlgili doküman güncellemesi gerekiyorsa yapılmalı.
- Approval gerektiren işlem varsa approval kapanmış olmalı.

## Dokümantasyon Taskları

- Markdown linkleri çalışmalı.
- Başlık seviyesi tutarlı olmalı.
- İçerik mevcut ürün vizyonuyla uyumlu olmalı.
- Gereksiz tekrar oluşturulmamalı.
- Related Documents bölümü eklenmeli.

## UI Taskları

- Empty/loading/error state tanımlı olmalı.
- Permission notları net olmalı.
- Status ve risk badge kuralları uygulanmalı.
- Acceptance criteria ekran davranışını doğrulamalı.

## API Taskları

- Endpoint `/api/v1` standardına uymalı.
- Request/response örneği olmalı.
- Validation kuralları belirtilmeli.
- Security/Audit Notes bölümü olmalı.

## Agent/Worker Taskları

- Agent output contract ile uyumlu olmalı.
- Command policy uygulanmalı.
- Riskli komut approval'a düşmeli.
- Command ve run log ilişkisi kurulmalı.

## Güvenlik/Onay Gerektiren Tasklar

- Impact analysis yazılmalı.
- Rollback planı olmalı.
- Audit log alanları belirtilmeli.
- İnsan onayı olmadan execution yapılmamalı.

## Related Documents

- [Development Checklist](development_checklist.md)
- [Approval Lifecycle](../03_operations/approval_lifecycle.md)
- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
- [Release Checklist](release_checklist.md)
