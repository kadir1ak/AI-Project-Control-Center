# Screen: Agent Runner

## Amaç

Agent Runner ekranı, task bazlı ajan çalışmalarını izlenebilir run kayıtları olarak gösterir.

## Ana Bileşenler

- Run list.
- Run detail paneli.
- Step timeline.
- Used context.
- Prompt preview.
- Output summary.
- Generated files.
- Command logs.
- Requires approval state.

## Run Detail Paneli

Panelde şunlar görünmelidir:

- Agent role.
- Task ID.
- Run status.
- Started/finished time.
- Prompt package.
- Output contract validation result.
- Related approval.
- Next action.

## Step Timeline

Örnek adımlar:

```text
Context Building -> Prompt Generated -> Agent Running -> Tool Execution -> Completed
```

## Requires Approval State

Run approval bekliyorsa:

- Run durumu `Waiting Approval` olur.
- Approval Center'a link gösterilir.
- Risk sebebi ve command preview görünür.

## Acceptance Criteria

- Kullanıcı run adımlarını sıralı görür.
- Kullanıcı prompt preview ve output summary görebilir.
- Command logs run ile ilişkilidir.
- Approval gereken run kullanıcıyı açıkça bilgilendirir.

## Related Documents

- [Agent Runner](../01_product/agent_runner.md)
- [Run Lifecycle](../03_operations/run_lifecycle.md)
- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
- [Runs API](../11_api/runs_api.md)
