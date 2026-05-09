# Documentation Index

Bu dosya, AI Project Control Center dokümantasyonunun ana navigasyon haritasıdır.

## Nereden Başlamalı?

1. [Product Vision](docs/00_overview/product_vision.md)
2. [System Architecture](docs/02_architecture/system_architecture.md)
3. [Workflow](docs/03_operations/workflow.md)
4. [Build Order](docs/09_execution/build_order.md)
5. [API Overview](docs/11_api/api_overview.md)
6. [Navigation Structure](docs/10_ui/navigation_structure.md)

## Kök Dokümanlar

- [README](README.md): proje tanımı, vizyon, yapı ve ana giriş.
- [Project Status](PROJECT_STATUS.md): mevcut faz, hedef, risk ve sıradaki milestone.
- [Changelog](CHANGELOG.md): dokümantasyon değişiklik geçmişi.
- [Plan Index](agentic_project_control_center_plan.md): önceki planın indekslenmiş hali.
- [Original Plan Archive](archive/original/agentic_project_control_center_plan.original.md): ilk uzun strateji dokümanı.

## docs/00_overview

Amaç: ürün vizyonunu, konumlandırmayı ve hedef kullanıcıları tanımlar.

- [product_vision.md](docs/00_overview/product_vision.md): ana ürün vizyonu ve başarı tanımı.
- [product_positioning.md](docs/00_overview/product_positioning.md): ürün adı, mesaj ve pazar konumu.
- [target_users.md](docs/00_overview/target_users.md): solo founder, ajans ve kurumsal ekip ihtiyaçları.

## docs/01_product

Amaç: ürün modüllerinin davranışını tanımlar.

- [command_center.md](docs/01_product/command_center.md): dashboard metrikleri ve ana kontrol ekranı.
- [ideation.md](docs/01_product/ideation.md): fikirden yapılandırılmış ürün kapsamına geçiş.
- [prd_editor.md](docs/01_product/prd_editor.md): PRD üretim ve düzenleme alanı.
- [spec_editor.md](docs/01_product/spec_editor.md): teknik ve fonksiyonel gereksinimler.
- [backlog_board.md](docs/01_product/backlog_board.md): Kanban ve task alanları.
- [agent_runner.md](docs/01_product/agent_runner.md): ajan run kayıtları.
- [approvals.md](docs/01_product/approvals.md): insan onaylı riskli işlem merkezi.
- [wiki.md](docs/01_product/wiki.md): proje hafızası.

## docs/02_architecture

Amaç: sistem katmanları, veri modeli, worker ve güvenliği tanımlar.

- [system_architecture.md](docs/02_architecture/system_architecture.md): Web UI, API, Orchestrator, Worker ve Sandbox akışı.
- [backend_services.md](docs/02_architecture/backend_services.md): backend servis sınırları.
- [data_model.md](docs/02_architecture/data_model.md): başlangıç veri modeli.
- [terminal_worker.md](docs/02_architecture/terminal_worker.md): terminal worker sorumlulukları.
- [security_model.md](docs/02_architecture/security_model.md): yetki ve risk yaklaşımı.
- [sandbox_design.md](docs/02_architecture/sandbox_design.md): sandbox izolasyonu ve lifecycle.
- [audit_logging.md](docs/02_architecture/audit_logging.md): audit log gereksinimleri.

## docs/03_operations

Amaç: görev, run, approval, command ve release akışlarını tanımlar.

- [workflow.md](docs/03_operations/workflow.md): ana ürün workflow'u.
- [task_lifecycle.md](docs/03_operations/task_lifecycle.md): task durumları.
- [run_lifecycle.md](docs/03_operations/run_lifecycle.md): agent run durumları.
- [approval_lifecycle.md](docs/03_operations/approval_lifecycle.md): approval akışı.
- [state_machine.md](docs/03_operations/state_machine.md): task, run, approval, command ve release state machine.
- [command_policy.md](docs/03_operations/command_policy.md): command risk değerlendirme politikası.

## docs/04_agents

Amaç: ajan takım modeli, roller, yetkiler ve çıktı sözleşmelerini tanımlar.

- [agent_team_model.md](docs/04_agents/agent_team_model.md): takım hiyerarşisi.
- [agent_roles.md](docs/04_agents/agent_roles.md): çekirdek roller.
- [ai_account_mapping.md](docs/04_agents/ai_account_mapping.md): Claude, GPT/Codex, Cursor, Gemini kullanımı.
- [agent_permissions.md](docs/04_agents/agent_permissions.md): rol bazlı yetkiler.
- [agent_output_contracts.md](docs/04_agents/agent_output_contracts.md): makine tarafından işlenebilir ajan çıktı formatları.

## docs/05_integrations

Amaç: AI provider, GitHub, MCP, Docker ve local terminal entegrasyon stratejilerini tanımlar.

- [github_mcp.md](docs/05_integrations/github_mcp.md): GitHub MCP kullanımı.
- [claude_skills_plugins.md](docs/05_integrations/claude_skills_plugins.md): skill/plugin yaklaşımı.
- [cursor_codex_gemini_usage.md](docs/05_integrations/cursor_codex_gemini_usage.md): araç bazlı kullanım.
- [ai_providers.md](docs/05_integrations/ai_providers.md): AI provider soyutlama yaklaşımı.
- [github_integration.md](docs/05_integrations/github_integration.md): GitHub repo, issue ve PR entegrasyonu.
- [mcp_strategy.md](docs/05_integrations/mcp_strategy.md): MCP stratejisi ve güvenlik sınırları.
- [docker_integration.md](docs/05_integrations/docker_integration.md): Docker sandbox entegrasyonu.
- [local_terminal_integration.md](docs/05_integrations/local_terminal_integration.md): kontrollü local terminal yaklaşımı.

## docs/06_templates

Amaç: PRD, task, prompt, approval, ADR ve rapor şablonlarını sağlar.

- [prd_template.md](docs/06_templates/prd_template.md): PRD şablonu.
- [task_template.md](docs/06_templates/task_template.md): task şablonu.
- [agent_profile_template.md](docs/06_templates/agent_profile_template.md): ajan profili şablonu.
- [prompt_package_template.md](docs/06_templates/prompt_package_template.md): prompt paketi şablonu.
- [approval_request_template.md](docs/06_templates/approval_request_template.md): approval request şablonu.
- [adr_template.md](docs/06_templates/adr_template.md): mimari karar şablonu.
- [epic_template.md](docs/06_templates/epic_template.md): epic şablonu.
- [run_report_template.md](docs/06_templates/run_report_template.md): agent run raporu.
- [qa_report_template.md](docs/06_templates/qa_report_template.md): QA raporu.

## docs/07_roadmap

Amaç: MVP, 30 günlük plan, 90 günlük roadmap ve demo kapsamını tanımlar.

- [mvp_scope.md](docs/07_roadmap/mvp_scope.md): ilk sürüm kapsamı.
- [thirty_day_plan.md](docs/07_roadmap/thirty_day_plan.md): 30 günlük plan.
- [ninety_day_roadmap.md](docs/07_roadmap/ninety_day_roadmap.md): 90 günlük roadmap.
- [demo_scenario.md](docs/07_roadmap/demo_scenario.md): Mini CRM demo senaryosu.

## docs/08_business

Amaç: ticari konumlandırma, fiyatlandırma fikirleri ve riskleri tanımlar.

- [commercial_positioning.md](docs/08_business/commercial_positioning.md): ticari mesaj.
- [pricing_ideas.md](docs/08_business/pricing_ideas.md): paket fikirleri.
- [risks.md](docs/08_business/risks.md): teknik ve ürün riskleri.

## docs/09_execution

Amaç: MVP geliştirme sırası, sprintler, DoD ve release hazırlığını tanımlar.

- [build_order.md](docs/09_execution/build_order.md): uygulama geliştirme sırası.
- [sprint_01_foundation.md](docs/09_execution/sprint_01_foundation.md): temel ürün zemini.
- [sprint_02_ai_planning.md](docs/09_execution/sprint_02_ai_planning.md): fikirden PRD/backlog üretimi.
- [sprint_03_agent_runner.md](docs/09_execution/sprint_03_agent_runner.md): agent runner kayıt sistemi.
- [sprint_04_terminal_worker.md](docs/09_execution/sprint_04_terminal_worker.md): terminal worker ve approval.
- [development_checklist.md](docs/09_execution/development_checklist.md): task öncesi/sonrası kontrol listesi.
- [definition_of_done.md](docs/09_execution/definition_of_done.md): Done koşulları.
- [release_checklist.md](docs/09_execution/release_checklist.md): release öncesi kontrol listesi.

## docs/10_ui

Amaç: ekran spesifikasyonları, navigasyon ve UI standartlarını tanımlar.

- [navigation_structure.md](docs/10_ui/navigation_structure.md): sol menü, MVP/sonra ayrımı ve permission notları.
- [screen_command_center.md](docs/10_ui/screen_command_center.md): command center ekran spesifikasyonu.
- [screen_backlog_board.md](docs/10_ui/screen_backlog_board.md): backlog board ekran spesifikasyonu.
- [screen_agent_runner.md](docs/10_ui/screen_agent_runner.md): agent runner ekran spesifikasyonu.
- [screen_terminal.md](docs/10_ui/screen_terminal.md): controlled terminal ekran spesifikasyonu.
- [screen_approval_center.md](docs/10_ui/screen_approval_center.md): approval center ekran spesifikasyonu.
- [design_system.md](docs/10_ui/design_system.md): durum, risk, state ve copywriting standartları.

## docs/11_api

Amaç: `/api/v1` REST API sözleşmelerini ve güvenlik/audit notlarını tanımlar.

- [api_overview.md](docs/11_api/api_overview.md): response, error, pagination ve versiyonlama standardı.
- [projects_api.md](docs/11_api/projects_api.md): project endpointleri.
- [tasks_api.md](docs/11_api/tasks_api.md): task endpointleri ve transition kuralları.
- [agents_api.md](docs/11_api/agents_api.md): agent profile endpointleri.
- [runs_api.md](docs/11_api/runs_api.md): agent run endpointleri.
- [approvals_api.md](docs/11_api/approvals_api.md): approval endpointleri.
- [commands_api.md](docs/11_api/commands_api.md): command preview/execution endpointleri.
- [files_api.md](docs/11_api/files_api.md): file tree, content ve diff endpointleri.
