# Screen: Approval Center

## Amaç

Approval Center, riskli operasyonların insan tarafından incelendiği ve karara bağlandığı ekrandır.

## Pending Approvals Listesi

Liste alanları:

- Approval title.
- Action type.
- Risk level.
- Requested by.
- Related task/run.
- Created at.
- Status.

## Approval Detail

Detail ekranında:

- Risk level.
- Impact analysis.
- Affected files.
- Affected services.
- Command preview.
- Rollback plan.
- Agent recommendation.
- Audit record.

görünmelidir.

## Aksiyonlar

- Approve.
- Reject.
- Request changes.

## Audit Record

Her karar audit log'a şunlarla yazılır:

- Actor.
- Action.
- Approval ID.
- Before/after status.
- Risk level.
- Timestamp.
- Correlation ID.

## Acceptance Criteria

- Kullanıcı approval sebebini ve etkisini görmeden onay vermez.
- Approve/reject/request changes kararı kaydedilir.
- Approval run ve command ile ilişkilidir.
- Yüksek riskli işlemler belirgin uyarı ile görünür.

## Related Documents

- [Approvals](../01_product/approvals.md)
- [Approval Lifecycle](../03_operations/approval_lifecycle.md)
- [Audit Logging](../02_architecture/audit_logging.md)
- [Approvals API](../11_api/approvals_api.md)
