# Sandbox Design

## Amaç

Sandbox, terminal/worker işlemlerinin ana host üzerinde doğrudan çalışmasını engeller ve proje bazlı izole execution ortamı sağlar.

## Neden Host Üzerinde Direkt Komut Çalıştırılmamalı?

- Host dosya sistemine zarar verme riski.
- Secret ve env bilgilerine erişim riski.
- Yanlış working directory ile destructive command riski.
- Audit ve rollback zorluğu.
- Multi-project izolasyon eksikliği.

## Docker Container per Project

MVP yaklaşımı:

```text
One project -> One isolated Docker container/workspace
```

Her proje için:

- Ayrı workspace mount.
- Sınırlı environment variables.
- Kontrollü network policy.
- Resource limits.
- Command log stream.

## Workspace Sınırı

- Worker sadece proje workspace içinde okuma/yazma yapabilir.
- Path traversal (`../`) blocked olmalıdır.
- File delete approval gerektirir.

## Network Sınırı

MVP'de network varsayılan olarak kontrollü olmalıdır.

- Package install approval gerektirebilir.
- Unknown script download blocked olmalıdır.
- External service access audit log yazmalıdır.

## Environment Variable / Secret Yönetimi

- Secret değerleri prompt veya log içine yazılmamalıdır.
- Worker secret'ları masked şekilde görmelidir.
- Production secret değişikliği approval gerektirir.

## Dosya Sistemi İzolasyonu

- Workspace dışına write blocked.
- System directory access blocked.
- Generated artifactlar project scope içinde tutulur.

## Resource Limits

MVP için öneri:

- CPU limit.
- Memory limit.
- Timeout.
- Max output size.
- Max process duration.

## Lifecycle

```text
create -> start -> execute -> stream logs -> stop -> cleanup
```

### create

Project workspace ve container metadata hazırlanır.

### start

Container başlatılır, health kontrol edilir.

### execute

Command policy onayından geçen komut çalıştırılır.

### stream logs

stdout/stderr UI'a ve CommandLogs'a aktarılır.

### stop

Run tamamlanınca container durdurulabilir veya warm tutulabilir.

### cleanup

Geçici dosyalar ve expired workspace kaynakları temizlenir.

## Yasaklı İşlemler

- Host path mount genişletme.
- Workspace dışına yazma.
- Unknown script pipe execution.
- Onaysız destructive database command.
- Onaysız production deploy.

## MVP Yaklaşımı

MVP'de Docker yeterlidir. Firecracker/microVM veya Kubernetes job sonraki güvenlik seviyesi olarak ele alınmalıdır.

## Gelecek Seçenekler

- Firecracker microVM.
- Kubernetes job/pod per run.
- Network egress policy.
- Ephemeral workspace snapshot.

## Related Documents

- [Terminal Worker](terminal_worker.md)
- [Command Policy](../03_operations/command_policy.md)
- [Commands API](../11_api/commands_api.md)
- [Terminal Screen](../10_ui/screen_terminal.md)
