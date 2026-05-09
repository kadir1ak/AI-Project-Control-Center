# Screen: Command Center

## Amaç

Command Center, projenin genel sağlık ve operasyon durumunu gösteren ana dashboard'dur.

## Gösterilecek Metrikler

- Project phase.
- Progress.
- Active agents.
- Open tasks.
- Blocked tasks.
- Pending approvals.
- Last run.
- Test status.
- Risk level.

## Ana Bileşenler

- Project summary header.
- Health metrics row.
- Active agents panel.
- Pending approvals panel.
- Recent runs list.
- Next recommended action.
- Risk notes panel.

## Empty State

Proje yeni oluşturulduysa kullanıcıya Ideation ekranına geçmesi önerilir.

## Loading State

Metric kartları skeleton olarak görünür; action buttonları disabled kalır.

## Error State

Dashboard verisi alınamazsa retry button ve kısa hata mesajı gösterilir.

## Acceptance Criteria

- Kullanıcı proje fazını ve sıradaki aksiyonu görebilir.
- Bekleyen approval varsa görünür ve Approval Center'a link verir.
- Son run durumu Agent Runner detayına link verir.
- Risk seviyesi renk ve metinle anlaşılırdır.

## Related Documents

- [Command Center](../01_product/command_center.md)
- [Workflow](../03_operations/workflow.md)
- [Run Lifecycle](../03_operations/run_lifecycle.md)
- [Approval Lifecycle](../03_operations/approval_lifecycle.md)
