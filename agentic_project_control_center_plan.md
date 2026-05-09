# Agentic Project Control Center

Web tabanlı, insan onaylı ve izlenebilir bir AI yazılım üretim operasyon merkezi.

Bu dosya artık ana indeks görevi görür. İlk uzun strateji dokümanı korunmuştur:

- [Orijinal plan arşivi](archive/original/agentic_project_control_center_plan.original.md)

## Ürün Kararı

Ana yön: **AI Project Builder Console**.

Ürün; fikirden PRD'ye, PRD'den backlog'a, backlog'dan ajan görevlerine, ajan görevlerinden kontrollü terminal/worker operasyonuna giden süreci tek bir web panelinde yönetir.

İlk MVP varsayımı: **AI destekli yarı otonom planlama konsolu**.

Bu aşamada hedef kod scaffold üretmek değil; planlama, backlog, ajan profilleri, prompt paketleri, approval akışı, loglama ve süreç yönetimini profesyonel şekilde netleştirmektir.

## Dokümantasyon Haritası

### Root Documents

- [README](README.md)
- [DOC_INDEX](DOC_INDEX.md)
- [PROJECT_STATUS](PROJECT_STATUS.md)
- [CHANGELOG](CHANGELOG.md)

### Overview

- [Product Vision](docs/00_overview/product_vision.md)
- [Product Positioning](docs/00_overview/product_positioning.md)
- [Target Users](docs/00_overview/target_users.md)

### Product

- [Command Center](docs/01_product/command_center.md)
- [Ideation](docs/01_product/ideation.md)
- [PRD Editor](docs/01_product/prd_editor.md)
- [Spec Editor](docs/01_product/spec_editor.md)
- [Backlog Board](docs/01_product/backlog_board.md)
- [Agent Runner](docs/01_product/agent_runner.md)
- [Approvals](docs/01_product/approvals.md)
- [Wiki](docs/01_product/wiki.md)

### Architecture

- [System Architecture](docs/02_architecture/system_architecture.md)
- [Backend Services](docs/02_architecture/backend_services.md)
- [Data Model](docs/02_architecture/data_model.md)
- [Terminal Worker](docs/02_architecture/terminal_worker.md)
- [Security Model](docs/02_architecture/security_model.md)

### Operations

- [Workflow](docs/03_operations/workflow.md)
- [Task Lifecycle](docs/03_operations/task_lifecycle.md)
- [Run Lifecycle](docs/03_operations/run_lifecycle.md)
- [Approval Lifecycle](docs/03_operations/approval_lifecycle.md)

### Agents

- [Agent Team Model](docs/04_agents/agent_team_model.md)
- [Agent Roles](docs/04_agents/agent_roles.md)
- [AI Account Mapping](docs/04_agents/ai_account_mapping.md)
- [Agent Permissions](docs/04_agents/agent_permissions.md)

### Integrations

- [GitHub MCP](docs/05_integrations/github_mcp.md)
- [Claude Skills and Plugins](docs/05_integrations/claude_skills_plugins.md)
- [Cursor, Codex and Gemini Usage](docs/05_integrations/cursor_codex_gemini_usage.md)

### Templates

- [PRD Template](docs/06_templates/prd_template.md)
- [Task Template](docs/06_templates/task_template.md)
- [Agent Profile Template](docs/06_templates/agent_profile_template.md)
- [Prompt Package Template](docs/06_templates/prompt_package_template.md)
- [Approval Request Template](docs/06_templates/approval_request_template.md)
- [ADR Template](docs/06_templates/adr_template.md)

### Roadmap

- [MVP Scope](docs/07_roadmap/mvp_scope.md)
- [30 Day Plan](docs/07_roadmap/thirty_day_plan.md)
- [90 Day Roadmap](docs/07_roadmap/ninety_day_roadmap.md)
- [Demo Scenario](docs/07_roadmap/demo_scenario.md)

### Business

- [Commercial Positioning](docs/08_business/commercial_positioning.md)
- [Pricing Ideas](docs/08_business/pricing_ideas.md)
- [Risks](docs/08_business/risks.md)

### Execution

- [Build Order](docs/09_execution/build_order.md)
- [Sprint 01 Foundation](docs/09_execution/sprint_01_foundation.md)
- [Sprint 02 AI Planning](docs/09_execution/sprint_02_ai_planning.md)
- [Sprint 03 Agent Runner](docs/09_execution/sprint_03_agent_runner.md)
- [Sprint 04 Terminal Worker](docs/09_execution/sprint_04_terminal_worker.md)
- [Development Checklist](docs/09_execution/development_checklist.md)
- [Definition of Done](docs/09_execution/definition_of_done.md)
- [Release Checklist](docs/09_execution/release_checklist.md)

### UI

- [Navigation Structure](docs/10_ui/navigation_structure.md)
- [Command Center Screen](docs/10_ui/screen_command_center.md)
- [Backlog Board Screen](docs/10_ui/screen_backlog_board.md)
- [Agent Runner Screen](docs/10_ui/screen_agent_runner.md)
- [Terminal Screen](docs/10_ui/screen_terminal.md)
- [Approval Center Screen](docs/10_ui/screen_approval_center.md)
- [Design System](docs/10_ui/design_system.md)

### API

- [API Overview](docs/11_api/api_overview.md)
- [Projects API](docs/11_api/projects_api.md)
- [Tasks API](docs/11_api/tasks_api.md)
- [Agents API](docs/11_api/agents_api.md)
- [Runs API](docs/11_api/runs_api.md)
- [Approvals API](docs/11_api/approvals_api.md)
- [Commands API](docs/11_api/commands_api.md)
- [Files API](docs/11_api/files_api.md)

## Kritik İlkeler

1. Önce plan, sonra kod.
2. Her task küçük, ölçülebilir ve test edilebilir olmalı.
3. Her ajan çıktısı kayıt altına alınmalı.
4. Terminal komutları doğrudan host üzerinde değil, kontrollü worker/sandbox içinde çalışmalı.
5. Riskli işlemler insan onayına düşmeli.
6. Sistem chat değil, operasyon paneli gibi davranmalı.
7. Ajanlar rol, yetki, context ve approval kurallarıyla sınırlandırılmalı.
8. Kullanıcı her an ne olduğunu, ne olacağını ve neden onay istendiğini görebilmeli.

## MVP Tanımı

İlk sürüm şunu başarmalı:

> Kullanıcı yazılım fikrini girer. Sistem PRD, mimari özet, backlog, mikro tasklar, ajan görev paketleri ve approval akışı üretir. Kullanıcı bunları web panelinden izler, düzenler ve kontrollü şekilde çalıştırır.

Bu turda bilinçli olarak dışarıda bırakılanlar:

- Tam otonom production deploy.
- Enterprise seviye çoklu tenant yetki sistemi.
- Marketplace.
- Karmaşık multi-agent framework bağımlılığı.
- Sıfırdan IDE inşa etmek.
- Kod scaffold oluşturmak.
