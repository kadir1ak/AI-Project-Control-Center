# Sprint 04: Terminal Worker

## Amaç

Kontrollü terminal/worker ve onay akışını kurmak.

## Kapsam

- Worker service.
- Docker sandbox.
- CommandLogs.
- SignalR log stream.
- Approval Center.
- Command policy.
- File diff.

## Micro Task Listesi

| ID | Task | Çıktı | Kabul Kriteri |
| --- | --- | --- | --- |
| WRK-001 | Worker service shell tasarla | Worker runtime planı | Worker API'den ayrıdır |
| WRK-002 | Docker sandbox lifecycle ekle | create/start/execute/stop planı | Komut host yerine sandbox içinde çalışır |
| WRK-003 | Command preview endpoint ekle | Risk preview | Riskli komut approval gerektirir |
| WRK-004 | CommandLogs modelini ekle | Komut kayıtları | stdout, stderr, exit code saklanır |
| WRK-005 | SignalR log stream ekle | Canlı log akışı | UI command output'u canlı görür |
| WRK-006 | Approval Center akışını bağla | Pending approval listesi | Onaysız riskli komut çalışmaz |
| WRK-007 | File diff view ekle | Diff ekranı | Kullanıcı değişen dosyaları görür |
| WRK-008 | Audit log bağla | İzlenebilir olay kaydı | Command ve approval correlation ID taşır |

## Sprint Sonu Demo

Kullanıcı güvenli bir build/test komutunu sandbox içinde çalıştırır, logları canlı görür ve riskli komutta approval ekranına yönlendirilir.

## Related Documents

- [Terminal Worker](../02_architecture/terminal_worker.md)
- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Command Policy](../03_operations/command_policy.md)
- [Approvals API](../11_api/approvals_api.md)
- [Commands API](../11_api/commands_api.md)
