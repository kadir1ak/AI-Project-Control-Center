# Screen: Backlog Board

## Amaç

Backlog Board, epic ve taskların Kanban üzerinde yönetildiği ana ürün ekranıdır.

## Kanban Kolonları

```text
Idea
Spec
Ready
In Progress
Review
Test
Done
Blocked
```

## Task Kart Alanları

- Task ID.
- Title.
- Epic.
- Priority.
- Assigned agent.
- Risk level.
- Dependencies.
- Test status.
- Last run status.
- Approval indicator.

## Drag/Drop Kuralları

- `Idea -> Spec`: scope netleştirme başlar.
- `Spec -> Ready`: acceptance criteria ve agent role atanmış olmalı.
- `Ready -> In Progress`: run veya manuel çalışma başlar.
- `In Progress -> Review`: çıktı oluşmuş olmalı.
- `Review -> Test`: review notları kapanmış olmalı.
- `Test -> Done`: validation tamamlanmış olmalı.
- Herhangi bir durumdan `Blocked`: bağımlılık, hata veya approval bekleniyorsa.

## State Transition Kuralları

Geçişler [State Machine](../03_operations/state_machine.md) ile uyumlu olmalıdır.

## Micro Task Görünümü

Task detail panelinde:

- Goal.
- Inputs.
- Outputs.
- Acceptance criteria.
- Related documents.
- Related runs.
- Commands/logs.

görünmelidir.

## Acceptance Criteria

- Kullanıcı taskı kolonlar arasında kurallara uygun taşıyabilir.
- Task kartında risk ve approval durumu görünür.
- Blocked tasklar nedeni ile birlikte gösterilir.
- Task detail paneli micro task bilgilerini içerir.

## Related Documents

- [Backlog Board](../01_product/backlog_board.md)
- [Task Lifecycle](../03_operations/task_lifecycle.md)
- [State Machine](../03_operations/state_machine.md)
- [Tasks API](../11_api/tasks_api.md)
