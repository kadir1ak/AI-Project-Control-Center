# Agent Output Contracts

## Neden Gerekli?

Ajan çıktıları chat cevabı gibi serbest metin olmamalıdır. Sistem; run sonucu, risk, dosya değişikliği, komut ve approval bilgisini makine tarafından işleyebilmelidir.

## Genel Kural

Her ajan çıktısı structured JSON contract'a uymalıdır.

## Genel Agent Output Contract

```json
{
  "agentRole": "",
  "taskId": "",
  "status": "completed|failed|blocked|requires_approval",
  "summary": "",
  "changedFiles": [],
  "createdArtifacts": [],
  "commandsToRun": [],
  "commandsExecuted": [],
  "tests": [],
  "risks": [],
  "assumptions": [],
  "requiresApproval": false,
  "approvalRequest": null,
  "nextAction": ""
}
```

## Planner Agent Output

Zorunlu alanlar:

- `summary`
- `assumptions`
- `risks`
- `createdArtifacts`
- `nextAction`

Beklenen artifact türleri:

- Project brief.
- MVP scope.
- Roadmap draft.
- Epic candidates.

## Product Owner Agent Output

Zorunlu alanlar:

- `summary`
- `createdArtifacts`
- `assumptions`
- `risks`

Beklenen artifact türleri:

- PRD.
- User stories.
- Acceptance criteria.
- Out-of-scope list.

## Architect Agent Output

Zorunlu alanlar:

- `summary`
- `decisions`
- `alternatives`
- `consequences`
- `affectedModules`
- `risks`

Örnek:

```json
{
  "decisions": [],
  "alternatives": [],
  "consequences": [],
  "affectedModules": []
}
```

## Developer Agent Output

Zorunlu alanlar:

- `summary`
- `changedFiles`
- `tests`
- `risks`
- `requiresApproval`

Kural:

Riskli komut veya dosya silme varsa `requiresApproval: true` olmalıdır.

## QA / Reviewer Agent Output

Zorunlu alanlar:

- `summary`
- `passedCriteria`
- `failedCriteria`
- `testNotes`
- `risks`
- `releaseRecommendation`

Örnek:

```json
{
  "passedCriteria": [],
  "failedCriteria": [],
  "testNotes": [],
  "releaseRecommendation": "approve|reject|needs_changes"
}
```

## DevOps / Worker Agent Output

Zorunlu alanlar:

- `summary`
- `commandsToRun`
- `commandsExecuted`
- `risks`
- `requiresApproval`
- `approvalRequest`

## Error Output Contract

```json
{
  "agentRole": "",
  "taskId": "",
  "status": "failed",
  "summary": "Failure summary",
  "error": {
    "code": "",
    "message": "",
    "details": {}
  },
  "nextAction": ""
}
```

## Approval Request Output Contract

```json
{
  "title": "",
  "actionType": "",
  "reason": "",
  "riskLevel": "Low|Medium|High|Critical",
  "commandPreview": "",
  "affectedFiles": [],
  "rollbackPlan": "",
  "expectedResult": ""
}
```

## Output Validation Kuralları

- Boş `summary` kabul edilmez.
- Riskli işlem varsa `requiresApproval` true olmalıdır.
- `commandsToRun` içinde riskli komut varsa `approvalRequest` olmalıdır.
- `changedFiles` varsa task scope ile uyumlu olmalıdır.
- `status` izin verilen değerlerden biri olmalıdır.
- Developer output içinde `changedFiles`, `tests` ve `risks` bulunmalıdır.

## Related Documents

- [Agent Roles](agent_roles.md)
- [Agent Permissions](agent_permissions.md)
- [Prompt Package Template](../06_templates/prompt_package_template.md)
- [Runs API](../11_api/runs_api.md)
