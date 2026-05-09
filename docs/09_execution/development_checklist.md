# Development Checklist

## Kodlamaya Başlamadan Önce

- İlgili ürün dokümanı okundu mu?
- İlgili architecture veya API dokümanı okundu mu?
- Scope tek task seviyesinde net mi?
- Acceptance criteria var mı?
- Risk seviyesi belirlendi mi?
- Test veya validation yöntemi var mı?
- Approval gerektiren işlem var mı?
- Task'ın bağlı olduğu epic veya milestone biliniyor mu?

## Her Task Öncesi

- Task input ve output alanları net mi?
- İlgili dosya sınırları belli mi?
- Command çalışacaksa command policy kontrol edildi mi?
- Secret/env bilgisi gerektiriyor mu?
- Existing behavior korunuyor mu?

## Her Task Sonrası

- Dosyalar küçük kapsamda mı değişti?
- Test/validation yapıldı mı?
- Hata veya risk notu yazıldı mı?
- README veya DOC_INDEX güncellemesi gerekiyor mu?
- Agent run veya command log kaydı gerekiyor mu?
- Commit mesajı task kapsamını açıklıyor mu?
- Push için ayrıca kullanıcı onayı var mı?

## Related Documents

- [Definition of Done](definition_of_done.md)
- [Command Policy](../03_operations/command_policy.md)
- [Agent Permissions](../04_agents/agent_permissions.md)
- [Audit Logging](../02_architecture/audit_logging.md)
