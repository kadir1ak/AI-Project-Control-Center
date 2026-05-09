# Security Model

## Amaç

Güvenlik modeli, ajanların ne yapabileceğini, hangi işlemlerin onay gerektirdiğini ve terminal worker'ın sınırlarını tanımlar.

## Yetki Seviyeleri

```text
Level 0: Plan only
Level 1: Read project context
Level 2: Read files
Level 3: Write project files
Level 4: Run safe commands
Level 5: Run tests and builds
Level 6: Git branch and PR preparation
Level 7: Database migration with approval
Level 8: Deploy with approval
```

## Varsayılan Politika

- Ajanlar plan yapabilir.
- Ajanlar proje context'ini okuyabilir.
- Ajanlar task kapsamındaki dosyaları yazabilir.
- Güvenli komutlar çalıştırılabilir.
- Riskli işlemler approval ister.
- Production etkisi olan işlemler her zaman approval ister.

## Yasaklı veya Bloklanacak İşlemler

- Host dosya sistemine kaçış.
- Proje klasörü dışına yazma.
- Secret değerlerini loglama.
- Onaysız production deploy.
- Onaysız database drop veya destructive migration.
- Bilinmeyen external script pipe çalıştırma.

## Audit Trail

Şu olaylar audit log'a yazılmalıdır:

- Project creation.
- PRD approval.
- Backlog generation.
- Agent run start/finish.
- Command execution.
- Approval approve/reject.
- File delete.
- Git push/PR/merge.
- Deployment action.

## MVP Güvenlik Minimumu

İlk sürümde en az şunlar olmalıdır:

- Risk sınıflandırması.
- Approval gerektiren komut listesi.
- Command log.
- Agent run log.
- Proje klasörü sınırı.
- Secret masking.
