# Local Terminal Integration

## Amaç

Local terminal entegrasyonu, geliştiricinin yerel ortamında kontrollü command preview, execution ve log takibi yaklaşımını tanımlar.

## MVP Kullanımı

- Read-only terminal log görüntüleme.
- Safe command execution.
- Command history.
- Approval required state.

## Güvenlik Notları

- Host terminale direkt unrestricted erişim verilmemelidir.
- Command policy her komuttan önce çalışmalıdır.
- Riskli komutlar approval'a düşmelidir.
- Secret masking uygulanmalıdır.
- Çalışma dizini proje workspace ile sınırlanmalıdır.

## İlgili Dokümanlar

- [Command Policy](../03_operations/command_policy.md)
- [Terminal Screen](../10_ui/screen_terminal.md)
- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Audit Logging](../02_architecture/audit_logging.md)
