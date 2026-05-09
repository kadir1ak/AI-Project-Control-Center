# Terminal Worker

## Amaç

Terminal Worker, dosya işlemleri ve komut çalıştırma gibi üretim işlemlerini web uygulamasından ayrılmış kontrollü bir ortamda yürütür.

## Temel Kural

Komutlar doğrudan host üzerinde çalıştırılmamalıdır.

Doğru akış:

```text
Web UI
  -> Backend API
  -> Command Policy Engine
  -> Worker Runtime
  -> Docker Sandbox
  -> Project Directory
```

## Worker Yetkinlikleri

- Dosya oluşturma.
- Dosya okuma.
- Dosya güncelleme.
- Build çalıştırma.
- Test çalıştırma.
- Git status ve diff alma.
- Branch oluşturma.
- PR hazırlık verisi üretme.
- Komut çıktısını stream etme.

## Otomatik Çalışmaması Gerekenler

- Production deploy.
- Database drop.
- Secret değiştirme.
- Main branch push.
- Toplu dosya silme.
- Bilinmeyen external script çalıştırma.
- `curl ... | bash` tarzı komutlar.

## MVP Sandbox

MVP için öneri:

```text
Docker container per project
Mounted project directory
Restricted command execution
Command policy middleware
SignalR live log stream
```

## Command Policy

Komutlar üç sınıfa ayrılmalıdır:

- `safe`: otomatik çalışabilir.
- `approval_required`: insan onayı gerekir.
- `blocked`: çalıştırılmaz.

## Örnek Riskli Komutlar

```text
rm -rf
rmdir /s
del /s
drop database
truncate
delete without where
git push origin main
deploy production
chmod -R 777
curl unknown-script | bash
```

## Loglama

Her komut için:

- Command.
- Working directory.
- Started at.
- Finished at.
- Exit code.
- stdout.
- stderr.
- Risk level.
- Approval ID.
- Agent run ID.

saklanmalıdır.
