# Commands API

## Purpose

Commands API, komut preview, execution ve command log görüntüleme davranışını tanımlar.

## Endpoints

```text
POST /api/v1/projects/{projectId}/commands/preview
POST /api/v1/projects/{projectId}/commands
GET  /api/v1/commands/{commandId}
GET  /api/v1/projects/{projectId}/commands
```

## Request Examples

Preview:

```json
{
  "command": "dotnet test",
  "workingDirectory": "backend"
}
```

Execute:

```json
{
  "command": "dotnet test",
  "workingDirectory": "backend",
  "runId": "run_123"
}
```

## Response Examples

Safe preview:

```json
{
  "success": true,
  "data": {
    "riskLevel": "Low",
    "classification": "safe",
    "requiresApproval": false
  },
  "error": null,
  "meta": {}
}
```

Approval required:

```json
{
  "success": true,
  "data": {
    "riskLevel": "High",
    "classification": "approval_required",
    "requiresApproval": true,
    "approvalRequestId": "approval_123"
  },
  "error": null,
  "meta": {}
}
```

## Validation

- Command boş olamaz.
- Working directory proje workspace sınırı içinde olmalıdır.
- Blocked command execute edilemez.
- Approval required command approved olmadan execute edilemez.

## Security/Audit Notes

- Preview ve execute audit log yazmalıdır.
- Execution sadece sandbox içinde yapılmalıdır.
- stdout/stderr secret masking'den geçmelidir.

## Related Documents

- [Command Policy](../03_operations/command_policy.md)
- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Terminal Screen](../10_ui/screen_terminal.md)
