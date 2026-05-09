# Backend Services

## Amaç

Backend servisleri ürün davranışını modüler ve test edilebilir parçalara ayırır.

## Çekirdek Servisler

- `ProjectService`: proje oluşturma, güncelleme, durum takibi.
- `IdeationService`: ham fikri yapılandırılmış proje özetine dönüştürme.
- `PrdService`: PRD üretme, versiyonlama, onaylama.
- `SpecService`: teknik ve fonksiyonel gereksinimleri yönetme.
- `BacklogService`: epic ve task üretme.
- `TaskService`: task yaşam döngüsü.
- `AgentProfileService`: ajan rol ve yetki tanımları.
- `AgentRunService`: run başlatma, takip, sonuç kaydı.
- `PromptEngineService`: task bazlı context ve prompt paketi oluşturma.
- `ContextService`: PRD, spec, kararlar, wiki ve dosya özetlerinden context hazırlama.
- `CommandService`: worker komut isteklerini yönetme.
- `ApprovalService`: riskli aksiyonlar için approval üretme.
- `FileService`: dosya ağacı, içerik ve diff bilgisi.
- `GitService`: GitHub ve lokal git operasyonları.
- `DiagramService`: Mermaid diagram üretimi.
- `WikiService`: proje wiki sayfaları.
- `AuditLogService`: kritik olayların kayıt altına alınması.

## MVP Önceliği

İlk sürümde şu servisler önce gelmelidir:

1. `ProjectService`
2. `PrdService`
3. `BacklogService`
4. `TaskService`
5. `AgentProfileService`
6. `PromptEngineService`
7. `AgentRunService`
8. `ApprovalService`

Terminal worker servisleri ikinci dalgada derinleştirilebilir.

## Servis Sınırları

- AI provider çağrıları doğrudan controller içinde yapılmamalıdır.
- Prompt üretimi ve agent run ayrı tutulmalıdır.
- Approval kararı command execution'dan önce verilmelidir.
- Audit log kritik state değişimlerinden sonra yazılmalıdır.
