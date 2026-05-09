# AI Providers

## Amaç

AI provider entegrasyonu, Claude, OpenAI/Codex, Gemini ve benzeri sağlayıcıların tek bir provider abstraction arkasında kullanılmasını sağlar.

## MVP Kullanımı

- Ideation ve PRD generation.
- Backlog generation.
- Prompt package generation.
- Agent output contract validation.

## Güvenlik Notları

- Secret/API key değerleri loglanmamalıdır.
- Prompt içine gereksiz secret veya user data koyulmamalıdır.
- Provider response agent output contract ile normalize edilmelidir.
- Provider hatası run error olarak kaydedilmelidir.

## İlgili Dokümanlar

- [Agent Output Contracts](../04_agents/agent_output_contracts.md)
- [Prompt Package Template](../06_templates/prompt_package_template.md)
- [Runs API](../11_api/runs_api.md)
- [Audit Logging](../02_architecture/audit_logging.md)
