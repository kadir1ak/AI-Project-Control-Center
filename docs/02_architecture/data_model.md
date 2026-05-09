# Data Model

## Amaç

Veri modeli; proje, doküman, task, ajan, run, command log, approval ve karar kayıtlarını izlenebilir şekilde saklamalıdır.

## Başlangıç Tabloları

```text
Users
Organizations
Projects
ProjectDocuments
Epics
Tasks
TaskDependencies
AgentProfiles
AgentRuns
AgentRunSteps
PromptTemplates
ContextDocuments
Artifacts
CommandLogs
Approvals
Files
FileChanges
Decisions
Diagrams
Repositories
AuditLogs
```

## Projects

```text
Id
OrganizationId
Name
Description
Status
TechStack
CreatedAt
UpdatedAt
```

## ProjectDocuments

PRD, spec, architecture, wiki ve benzeri dokümanları tutar.

```text
Id
ProjectId
Type
Title
ContentMarkdown
Version
Status
CreatedAt
UpdatedAt
ApprovedAt
```

## Epics

```text
Id
ProjectId
Title
Description
Priority
Status
Order
CreatedAt
UpdatedAt
```

## Tasks

```text
Id
ProjectId
EpicId
Title
Description
Status
Priority
AssignedAgentProfileId
AcceptanceCriteria
Dependencies
RiskLevel
EstimatedEffort
CreatedAt
UpdatedAt
```

## AgentRuns

```text
Id
ProjectId
TaskId
AgentProfileId
Status
InputPrompt
OutputSummary
StartedAt
FinishedAt
RequiresApproval
ErrorMessage
```

## AgentRunSteps

```text
Id
AgentRunId
StepName
Status
Input
Output
StartedAt
FinishedAt
ErrorMessage
```

## CommandLogs

```text
Id
ProjectId
AgentRunId
Command
WorkingDirectory
Output
ExitCode
RiskLevel
ApprovalId
StartedAt
FinishedAt
```

## Approvals

```text
Id
ProjectId
RequestedByAgentRunId
ActionType
Title
Description
RiskLevel
CommandPreview
AffectedFiles
RollbackPlan
Status
ApprovedByUserId
CreatedAt
ResolvedAt
```

## Decisions

```text
Id
ProjectId
Title
Decision
Reason
Alternatives
Consequences
CreatedBy
CreatedAt
```
