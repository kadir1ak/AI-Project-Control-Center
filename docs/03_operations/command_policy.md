# Command Policy

## Amaç

Command policy, terminal/worker katmanında hangi komutların otomatik, onaylı veya bloklu çalışacağını belirler.

## Command Sınıfları

### Safe Command

Düşük riskli, proje workspace içinde okuma veya build/test amacı taşıyan komutlar.

Örnekler:

- `dotnet build`
- `dotnet test`
- `npm run build`
- `npm run lint`
- `git status`
- `git diff`

### Risky Command

Proje veya veri üzerinde kalıcı etki yaratabilecek komutlar.

Örnekler:

- `dotnet ef database update`
- `npm install`
- `git push`
- `docker compose up`

### Approval Required Command

Riskli ama doğru onayla çalıştırılabilecek komutlar.

Örnekler:

- `dotnet ef database update`
- `git push origin main`
- `deploy production`

### Blocked Command

Host, secret, veri veya workspace güvenliğini tehlikeye atabilecek komutlar.

Örnekler:

- `rm -rf`
- `rmdir /s`
- `drop database`
- `curl unknown-script | bash`
- `chmod -R 777`

## Command Evaluation Flow

1. Parse command.
2. Detect risk.
3. Check permissions.
4. Require approval if needed.
5. Execute in sandbox.
6. Stream logs.
7. Write audit log.

## Policy Kararları

| Komut | Sınıf | Davranış |
| --- | --- | --- |
| `dotnet build` | Safe | Sandbox içinde çalışabilir |
| `dotnet test` | Safe | Sandbox içinde çalışabilir |
| `npm run build` | Safe | Sandbox içinde çalışabilir |
| `git status` | Safe | Read-only çalışabilir |
| `git diff` | Safe | Read-only çalışabilir |
| `dotnet ef database update` | Approval required | Approval sonrası çalışabilir |
| `rm -rf` | Blocked | Çalıştırılmaz |
| `git push main` | Approval required | Explicit approval gerekir |
| `curl unknown-script \| bash` | Blocked | Çalıştırılmaz |

## Audit

Preview, approval required, blocked, running, succeeded ve failed sonuçları audit log yazmalıdır.

## Related Documents

- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Terminal Screen](../10_ui/screen_terminal.md)
- [Commands API](../11_api/commands_api.md)
- [Audit Logging](../02_architecture/audit_logging.md)
