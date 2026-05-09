# API Overview

## Purpose

API katmanı, Web UI, Orchestrator ve Worker Runtime arasındaki kontrollü veri akışını sağlar.

## API Versioning

Önerilen base path:

```text
/api/v1
```

Breaking change gerektiğinde yeni major path açılır.

## REST Endpoint Standardı

- Collection: `GET /api/v1/projects`
- Create: `POST /api/v1/projects`
- Detail: `GET /api/v1/projects/{projectId}`
- Partial update: `PATCH /api/v1/projects/{projectId}`
- Action endpoint: `POST /api/v1/tasks/{taskId}/transition`

## Response Format Standardı

```json
{
  "success": true,
  "data": {},
  "error": null,
  "meta": {}
}
```

## Error Format Standardı

```json
{
  "success": false,
  "data": null,
  "error": {
    "code": "TASK_NOT_FOUND",
    "message": "Task not found",
    "details": {}
  },
  "meta": {}
}
```

## Pagination Standardı

```json
{
  "success": true,
  "data": [],
  "error": null,
  "meta": {
    "page": 1,
    "pageSize": 20,
    "totalCount": 100
  }
}
```

## Auth Notları

- MVP'de auth tasarımı ayrı netleştirilebilir.
- Tüm write/action endpointleri actor bilgisi üretmelidir.
- Approval, command execution ve file write endpointleri yüksek yetki ister.

## Audit/Logging Beklentileri

Audit log yazılacak durumlar:

- Create/update/delete.
- State transition.
- Agent run start/cancel.
- Command preview/execution.
- Approval decision.
- File write/delete.

## Related Documents

- [Audit Logging](../02_architecture/audit_logging.md)
- [Security Model](../02_architecture/security_model.md)
- [State Machine](../03_operations/state_machine.md)
