# Tasks API

## Purpose

Task endpointleri task CRUD, state transition ve micro task breakdown davranışını tanımlar.

## Endpoints

```text
GET  /api/v1/projects/{projectId}/tasks
POST /api/v1/projects/{projectId}/tasks
GET  /api/v1/tasks/{taskId}
PATCH /api/v1/tasks/{taskId}
POST /api/v1/tasks/{taskId}/transition
POST /api/v1/tasks/{taskId}/breakdown
```

## Request Examples

```json
{
  "title": "Login endpoint oluştur",
  "description": "Email/password ile login ve JWT response",
  "epicId": "epic_auth",
  "priority": "high",
  "status": "Ready",
  "acceptanceCriteria": [
    "Doğru bilgilerle 200 döner",
    "Hatalı şifrede 401 döner"
  ]
}
```

Transition:

```json
{
  "toStatus": "In Progress",
  "reason": "Developer Agent run started"
}
```

## Response Examples

```json
{
  "success": true,
  "data": {
    "id": "task_auth_003",
    "title": "Login endpoint oluştur",
    "status": "Ready",
    "riskLevel": "Medium"
  },
  "error": null,
  "meta": {}
}
```

## Task Status Transition Kuralları

- `Spec -> Ready` için acceptance criteria zorunludur.
- `Ready -> In Progress` için assigned agent veya owner olmalıdır.
- `Waiting Approval -> In Progress` sadece approval approved ise olabilir.
- `Done` için validation sonucu gerekir.
- Yasak geçişler [State Machine](../03_operations/state_machine.md) dokümanına uymalıdır.

## Micro Task Breakdown Notları

`POST /breakdown`, büyük taskı küçük tasklara böler. Çıktı task template ile uyumlu olmalıdır.

## Validation

- `title` zorunludur.
- `projectId` geçerli olmalıdır.
- `acceptanceCriteria` `Ready` state öncesi dolu olmalıdır.
- `riskLevel` izin verilen değerlerden biri olmalıdır.

## Security/Audit Notes

- Task create/update/transition audit log yazmalıdır.
- Breakdown AI çıktısıysa agent run veya artifact ile ilişkilendirilmelidir.

## Related Documents

- [Backlog Board](../01_product/backlog_board.md)
- [Task Lifecycle](../03_operations/task_lifecycle.md)
- [Task Template](../06_templates/task_template.md)
