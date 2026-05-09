# GitHub Integration

## Amaç

GitHub entegrasyonu repository, branch, diff, issue ve pull request akışlarını AI Project Control Center'a bağlar.

## MVP Kullanımı

- Repo bağlantısı.
- Read-only file/diff görüntüleme.
- Issue/task eşleştirme.
- PR taslağı hazırlama.

## Güvenlik Notları

- `main` branch'e otomatik push yapılmamalıdır.
- PR merge her zaman approval gerektirir.
- Secret ve workflow permission değişiklikleri otomatik yapılmamalıdır.
- GitHub token izinleri minimum tutulmalıdır.

## İlgili Dokümanlar

- [GitHub MCP](github_mcp.md)
- [MCP Strategy](mcp_strategy.md)
- [Files API](../11_api/files_api.md)
- [Approval Lifecycle](../03_operations/approval_lifecycle.md)
