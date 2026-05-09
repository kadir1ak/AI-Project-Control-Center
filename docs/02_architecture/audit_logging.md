# Audit Logging

## Neden Gerekli?

AI ajanları ve terminal worker proje üzerinde işlem yapacağı için her kritik olay geriye dönük izlenebilir olmalıdır.

Audit log şunları sağlar:

- Kim veya hangi ajan ne yaptı?
- Ne zaman yaptı?
- Hangi entity etkilendi?
- Öncesi ve sonrası neydi?
- Risk seviyesi neydi?
- Hangi approval veya command ile ilişkiliydi?

## Loglanacak Olaylar

- Project created.
- Task created/updated.
- Agent run started/completed/failed.
- Command previewed/executed/blocked.
- Approval requested/approved/rejected.
- File changed/deleted.
- PR created.
- Release tagged.
- State transition.
- Permission changed.

## Audit Log Alanları

```text
id
actorType
actorId
action
entityType
entityId
before
after
riskLevel
timestamp
correlationId
```

## Actor Type

Örnek değerler:

- `user`
- `agent`
- `worker`
- `system`
- `integration`

## AI Ajanları İçin Zorunluluk

AI ajanları tarafından üretilen her run ve önerilen her command kayıt altına alınmalıdır.

Minimum:

- Agent role.
- Task ID.
- Prompt package reference.
- Output contract.
- Risk list.
- Next action.

## Komut ve Dosya İşlemleri

Command execution ve file operation için:

- Command preview.
- Policy classification.
- Approval ID.
- Sandbox ID.
- Exit code.
- Changed files.

saklanmalıdır.

## Correlation ID

Bir kullanıcı aksiyonu, agent run, approval ve command log aynı correlation ID ile bağlanmalıdır.

## Related Documents

- [Command Policy](../03_operations/command_policy.md)
- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
- [Approvals API](../11_api/approvals_api.md)
- [Commands API](../11_api/commands_api.md)
