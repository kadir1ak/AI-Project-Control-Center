# Docker Integration

## Amaç

Docker entegrasyonu, worker komutlarını proje bazlı izole sandbox içinde çalıştırmak için kullanılır.

## MVP Kullanımı

- Project workspace container.
- Build/test command execution.
- Command log stream.
- File diff üretimi.

## Güvenlik Notları

- Host path mount minimum tutulmalıdır.
- Workspace dışına erişim blocked olmalıdır.
- Network egress kontrollü olmalıdır.
- Container resource limit uygulanmalıdır.
- Unknown external script blocked olmalıdır.

## İlgili Dokümanlar

- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Terminal Worker](../02_architecture/terminal_worker.md)
- [Command Policy](../03_operations/command_policy.md)
- [Commands API](../11_api/commands_api.md)
