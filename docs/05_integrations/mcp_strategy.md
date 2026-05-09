# MCP Strategy

## Amaç

MCP stratejisi, AI araçlarının GitHub ve benzeri dış sistemlerle kontrollü şekilde konuşmasını tanımlar.

## MVP Kullanımı

- GitHub read operations.
- Repo ve issue metadata okuma.
- PR hazırlık context'i toplama.
- AI araçları için kontrollü bilgi erişimi.

## Güvenlik Notları

- MCP tool izinleri role ve task scope ile sınırlandırılmalıdır.
- Write actionlar approval gerektirmelidir.
- Tool output audit edilebilir run kaydına bağlanmalıdır.
- MCP üzerinden secret okunmamalı veya prompt'a taşınmamalıdır.

## İlgili Dokümanlar

- [GitHub MCP](github_mcp.md)
- [Agent Permissions](../04_agents/agent_permissions.md)
- [Audit Logging](../02_architecture/audit_logging.md)
- [Command Policy](../03_operations/command_policy.md)
