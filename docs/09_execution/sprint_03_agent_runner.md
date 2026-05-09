# Sprint 03: Agent Runner

## Amaç

Task bazlı ajan çalıştırma kayıt sistemini kurmak.

## Kapsam

- AgentProfiles.
- PromptTemplates.
- ContextDocuments.
- PromptEngineService.
- AgentRuns.
- AgentRunSteps.
- Agent Runner UI.

## Micro Task Listesi

| ID | Task | Çıktı | Kabul Kriteri |
| --- | --- | --- | --- |
| RUN-001 | AgentProfiles modelini ekle | Agent profile kayıtları | Rol, provider, permissions saklanır |
| RUN-002 | PromptTemplates modelini ekle | Template kayıtları | Template task tipine bağlanabilir |
| RUN-003 | ContextDocuments modelini ekle | Context kaynakları | PRD/spec/wiki context'e dahil olur |
| RUN-004 | PromptEngineService tasarla | Prompt package üretimi | Task için structured prompt üretilir |
| RUN-005 | AgentRuns modelini ekle | Run kayıtları | Run task ve agent profile ile ilişkilidir |
| RUN-006 | AgentRunSteps modelini ekle | Timeline adımları | Her adım status ve error tutar |
| RUN-007 | Agent Runner UI ekle | Run list/detail | Run timeline, prompt preview ve output görünür |
| RUN-008 | Output contract validation ekle | Contract kontrolü | Boş summary veya eksik required alan kabul edilmez |

## Sprint Sonu Demo

Kullanıcı bir task seçer, uygun ajan için prompt paketi üretir ve run timeline'ını görür.

## Related Documents

- [Agent Runner](../01_product/agent_runner.md)
- [Agent Roles](../04_agents/agent_roles.md)
- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
- [Prompt Package Template](../06_templates/prompt_package_template.md)
- [Runs API](../11_api/runs_api.md)
