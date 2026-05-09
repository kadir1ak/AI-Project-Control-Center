# Navigation Structure

## Sol Menü

| Menü | Amaç | MVP | Permission Notu |
| --- | --- | --- | --- |
| Overview | Proje sağlığı ve sonraki aksiyonlar | Evet | Tüm proje üyeleri okuyabilir |
| Ideation | Ham fikri yapılandırmak | Evet | Product/Owner rolü yazabilir |
| PRD Editor | PRD üretmek ve düzenlemek | Evet | Product/Owner onayı gerekir |
| Spec Editor | Teknik/fonksiyonel gereksinimler | Evet | Architect/Lead yazabilir |
| Architecture | Mimari kararlar ve diagramlar | Evet | Architect owner olmalı |
| Backlog | Epic/task Kanban yönetimi | Evet | Task edit için project permission gerekir |
| Agent Runner | Agent run ve prompt takibi | Evet | Run başlatma ayrı permission ister |
| Terminal | Controlled terminal ve loglar | Sonra/MVP-lite | Command input yüksek yetki ister |
| Files | Dosya ağacı ve diff | Sonra | Yazma ve silme approval ister |
| Approvals | Riskli işlem onayları | Evet | Sadece authorized approver karar verir |
| Logs | Audit, command ve run logları | Evet | Read-only çoğu role açık olabilir |
| Wiki | Proje hafızası | Evet | Kritik sayfa değişimi approval ister |
| Settings | Project, integrations, permissions | Sonra | Admin/Owner |

## MVP Navigasyon

İlk ürün shell'inde görünür olması önerilen menüler:

- Overview
- Ideation
- PRD Editor
- Spec Editor
- Backlog
- Agent Runner
- Approvals
- Logs
- Wiki

Terminal ve Files MVP'de read-only veya placeholder olabilir.

## Sonraki Faz

- Terminal command input.
- File write/delete.
- GitHub PR actions.
- Billing/team settings.

## Related Documents

- [Command Center Screen](screen_command_center.md)
- [Backlog Board Screen](screen_backlog_board.md)
- [Agent Runner Screen](screen_agent_runner.md)
- [Approval Center Screen](screen_approval_center.md)
- [Agent Permissions](../04_agents/agent_permissions.md)
