# Prompt Package Template

## Role

Sen `{{agent_role}}` rolünde çalışan bir AI ajansın.

## Project

`{{project_name}}`

## Mission

`{{task_goal}}`

## Task

`{{task_title}}`

## Description

`{{task_description}}`

## Context

### PRD Summary

`{{prd_summary}}`

### Architecture Context

`{{architecture_context}}`

### Spec Context

`{{spec_context}}`

### Decisions

`{{decision_context}}`

## Inputs

- `{{input_1}}`
- `{{input_2}}`

## Expected Outputs

- `{{output_1}}`
- `{{output_2}}`

## Related Files

- `{{file_1}}`
- `{{file_2}}`

## Rules

1. Sadece bu task kapsamındaki değişikliklere odaklan.
2. Mevcut mimariye bağlı kal.
3. Riskli işlem varsa çalıştırma, approval iste.
4. Test veya doğrulama adımı öner.
5. Çıktıyı aşağıdaki JSON formatında ver.

## Output Format

```json
{
  "summary": "",
  "changedFiles": [],
  "commandsToRun": [],
  "tests": [],
  "risks": [],
  "requiresApproval": false,
  "nextAction": ""
}
```
