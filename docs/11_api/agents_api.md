# Agents API

## Purpose

Agent profile endpointleri rol, provider, izinler, allowed tools ve output contract referanslarını yönetir.

## Endpoints

```text
GET   /api/v1/agent-profiles
POST  /api/v1/agent-profiles
GET   /api/v1/agent-profiles/{agentProfileId}
PATCH /api/v1/agent-profiles/{agentProfileId}
```

## Request Examples

```json
{
  "roleName": "Backend Developer",
  "provider": "OpenAI",
  "modelName": "codex",
  "permissions": ["read_context", "read_files", "write_project_files"],
  "allowedTools": ["prompt_engine", "file_diff"],
  "outputContract": "developer_agent_output"
}
```

## Response Examples

```json
{
  "success": true,
  "data": {
    "id": "agent_backend",
    "roleName": "Backend Developer",
    "permissions": ["read_context", "read_files", "write_project_files"]
  },
  "error": null,
  "meta": {}
}
```

## Validation

- `roleName` zorunludur.
- `provider` desteklenen providerlardan biri olmalıdır.
- `permissions` [Agent Permissions](../04_agents/agent_permissions.md) ile uyumlu olmalıdır.
- `outputContract` [Agent Output Contracts](../04_agents/agent_output_contracts.md) ile uyumlu olmalıdır.

## Security/Audit Notes

- Agent permission değişikliği audit log yazmalıdır.
- Tool veya command yetkisi genişletme yüksek riskli sayılmalıdır.

## Related Documents

- [Agent Roles](../04_agents/agent_roles.md)
- [Agent Permissions](../04_agents/agent_permissions.md)
- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
