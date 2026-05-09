# Runs API

## Purpose

Runs API, task bazlı agent run oluşturma, izleme ve iptal etme davranışını tanımlar.

## Endpoints

```text
POST /api/v1/tasks/{taskId}/runs
GET  /api/v1/runs/{runId}
GET  /api/v1/tasks/{taskId}/runs
POST /api/v1/runs/{runId}/cancel
```

## Request Examples

```json
{
  "agentProfileId": "agent_backend",
  "mode": "prompt_only",
  "contextDocumentIds": ["prd_1", "spec_1"]
}
```

## Response Examples

```json
{
  "success": true,
  "data": {
    "id": "run_123",
    "taskId": "task_auth_003",
    "status": "Prompt Generated",
    "steps": [
      {
        "name": "Context Building",
        "status": "Completed"
      }
    ]
  },
  "error": null,
  "meta": {}
}
```

## AgentRunStep Response

```json
{
  "name": "Agent Running",
  "status": "Completed",
  "startedAt": "2026-05-09T10:00:00Z",
  "finishedAt": "2026-05-09T10:01:00Z",
  "errorMessage": null
}
```

## Validation

- `taskId` geçerli olmalıdır.
- `agentProfileId` geçerli olmalıdır.
- Run status [State Machine](../03_operations/state_machine.md) ile uyumlu olmalıdır.
- Cancel, tamamlanmış run için uygulanmamalıdır.

## Security/Audit Notes

- Run start/cancel audit log yazmalıdır.
- Run output agent output contract ile validate edilmelidir.
- Tool/command çalıştırma ayrı approval ve command policy akışına bağlıdır.

## Related Documents

- [Run Lifecycle](../03_operations/run_lifecycle.md)
- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
- [Agent Runner Screen](../10_ui/screen_agent_runner.md)
