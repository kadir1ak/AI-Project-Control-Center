# Release Checklist

## Build/Test

- Frontend build geçti mi?
- Backend build geçti mi?
- Unit/integration testler geçti mi?
- Worker command smoke test yapıldı mı?
- Kritik browser akışları doğrulandı mı?

## Dokümantasyon

- README güncel mi?
- DOC_INDEX güncel mi?
- CHANGELOG Unreleased bölümü güncel mi?
- API docs endpoint davranışıyla uyumlu mu?
- Release notes hazır mı?

## Migration

- Migration listesi review edildi mi?
- Rollback planı var mı?
- Migration approval alındı mı?
- Development/staging sonuçları kaydedildi mi?

## Env/Secrets

- Yeni env değişkenleri dokümante edildi mi?
- Secret değerleri loglara yazılmıyor mu?
- Production secret değişikliği approval aldı mı?

## Approval

- Riskli komutlar approval aldı mı?
- PR/merge approval tamam mı?
- Production deploy approval tamam mı?

## Rollback

- Release rollback adımları yazıldı mı?
- Database rollback planı var mı?
- Git tag veya release referansı hazır mı?

## Tag/Release Notes

- Semantic version veya release tag belirlendi mi?
- Release notes kullanıcı etkisini açıklıyor mu?
- Known issues yazıldı mı?

## Hotfix Sonrası

- Hotfix main branch'e uygulanırsa develop/aktif çalışma branch'ine geri merge planlandı mı?
- Dokümantasyon ve changelog güncellendi mi?

## Related Documents

- [Definition of Done](definition_of_done.md)
- [Audit Logging](../02_architecture/audit_logging.md)
- [Approval Lifecycle](../03_operations/approval_lifecycle.md)
- [Commercial Risks](../08_business/risks.md)
