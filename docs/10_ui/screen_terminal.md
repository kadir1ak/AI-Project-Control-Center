# Screen: Terminal

## Amaç

Terminal ekranı, sandbox içindeki kontrollü komut çalıştırma ve log izleme alanıdır.

## Modlar

- Read-only terminal.
- Controlled command input.
- Command risk preview.
- Live logs.
- Command history.

## Command Input

Kullanıcı komut yazdığında önce preview çalışır:

1. Komut parse edilir.
2. Risk tespit edilir.
3. Permission kontrol edilir.
4. Safe ise sandbox içinde çalıştırılır.
5. Riskli ise approval istenir.
6. Blocked ise çalıştırılmaz.

## Approval Required State

Riskli komut için:

- Komut çalıştırılmaz.
- Risk nedeni gösterilir.
- Approval request oluşturulur.
- Kullanıcı Approval Center'a yönlendirilir.

## Yasaklı/Riskli Komut Uyarısı

Blocked komutlarda mesaj kısa ve net olmalıdır:

```text
This command is blocked by command policy because it can modify files outside the allowed workspace.
```

## Acceptance Criteria

- Terminal host üzerinde direkt komut çalıştırmaz.
- Safe command log üretir.
- Riskli command approval'a düşer.
- Blocked command çalışmaz ve audit log yazar.
- Live logs okunabilir ve timestamp içerir.

## Related Documents

- [Terminal Worker](../02_architecture/terminal_worker.md)
- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Command Policy](../03_operations/command_policy.md)
- [Commands API](../11_api/commands_api.md)
