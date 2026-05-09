# Approvals API

## Purpose

Approvals API, riskli aksiyonların insan onayına alınmasını ve kararın audit edilebilir şekilde kaydedilmesini sağlar.

## Endpoints

```text
GET  /api/v1/approvals
GET  /api/v1/approvals/{approvalId}
POST /api/v1/approvals/{approvalId}/approve
POST /api/v1/approvals/{approvalId}/reject
POST /api/v1/approvals/{approvalId}/request-changes
```

## Request Examples

Approve:

```json
{
  "note": "Development database migration approved"
}
```

Reject:

```json
{
  "reason": "Rollback plan is missing"
}
```

## Response Examples

```json
{
  "success": true,
  "data": {
    "id": "approval_123",
    "status": "Approved",
    "riskLevel": "Medium",
    "resolvedAt": "2026-05-09T10:05:00Z"
  },
  "error": null,
  "meta": {}
}
```

## Validation

- Sadece `Pending` approval karar alabilir.
- `approve` için authorized approver gerekir.
- `request-changes` notu boş olamaz.

## Security/Audit Notes

- Tüm approval kararları audit log yazmalıdır.
- High/Critical risk approval kararları explicit confirmation gerektirebilir.
- Approval related run, command veya file operation ile ilişkilendirilmelidir.

## Related Documents

- [Approval Lifecycle](../03_operations/approval_lifecycle.md)
- [Approval Center Screen](../10_ui/screen_approval_center.md)
- [Audit Logging](../02_architecture/audit_logging.md)
