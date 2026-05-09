# Build Order

Bu doküman, AI Project Control Center MVP'sinin hangi sırayla geliştirileceğini tanımlar.

## Öncelik Sırası

| Sıra | Adım | Amaç | Çıktı | Bağımlılık | Kabul Kriteri |
| --- | --- | --- | --- | --- | --- |
| 1 | Repo ve dokümantasyon standardı | Çalışma zemini ve karar hafızasını netleştirmek | README, DOC_INDEX, roadmap, templates | Yok | Doküman linkleri çalışır ve MVP kapsamı görünürdür |
| 2 | Frontend shell | Web UI için uygulama kabuğunu kurmak | Layout, navigation, empty screens | 1 | Sol menü ve temel sayfalar açılır |
| 3 | Backend API shell | API kabuğunu hazırlamak | `/api/v1` base, health endpoint | 1 | API health response döner |
| 4 | PostgreSQL data model | Kalıcı veri modelini hazırlamak | EF Core entities ve migrations planı | 3 | Projects, Epics, Tasks modeli doğrulanır |
| 5 | Project CRUD | Proje yönetimini başlatmak | Project endpoints ve UI list/detail | 2, 3, 4 | Proje oluşturulur, listelenir, güncellenir |
| 6 | Task CRUD | Task yönetimini başlatmak | Task endpoints ve detay ekranı | 5 | Task oluşturulur ve proje ile ilişkilidir |
| 7 | Kanban Board | Süreci görsel yönetmek | Kanban kolonları ve transition | 6 | Task kolonlar arasında kurala uygun taşınır |
| 8 | PRD generation | Fikirden PRD üretmek | Ideation input ve PRD draft | 5 | Kullanıcı fikrinden PRD taslağı oluşur |
| 9 | Backlog generation | PRD'den epic/task üretmek | Epic ve task kayıtları | 8, 6 | PRD'den backlog oluşturulur |
| 10 | Agent Profiles | Rolleri ve yetkileri tanımlamak | Agent profile CRUD | 6 | Rol, provider, permissions kayıt edilir |
| 11 | Prompt Engine | Task bazlı prompt paketi üretmek | Prompt package output | 8, 9, 10 | Task için structured prompt üretilir |
| 12 | Agent Runner | Run kayıtlarını izlemek | AgentRuns ve AgentRunSteps | 11 | Run başlar, adımlar ve sonuç görünür |
| 13 | Command Logs | Worker komutlarını kayıt altına almak | CommandLogs modeli ve UI | 12 | Komut, çıktı, exit code kayıt edilir |
| 14 | Approval Center | Riskli işlemleri insan onayına almak | Approval list/detail | 13 | Riskli işlem onaysız çalışmaz |
| 15 | Docker Sandbox | Komutları izole ortamda yürütmek | Project container runtime | 13, 14 | Komut sandbox içinde çalışır |
| 16 | File diff view | Değişiklikleri review etmek | File tree ve diff ekranı | 15 | Kullanıcı dosya diff görebilir |
| 17 | GitHub integration | Repo/issue/PR akışını bağlamak | GitHub read/PR preparation | 16 | Repo diff ve PR taslağı ilişkilidir |

## Uygulama Prensibi

- Her adım tek başına review edilebilir olmalıdır.
- Runtime veya güvenlik etkisi olan adımlar approval gerektirir.
- Dokümantasyon, kod değişikliğinden önce güncellenmelidir.
- `main` branch'e otomatik push yapılmaz.

## Related Documents

- [MVP Scope](../07_roadmap/mvp_scope.md)
- [30 Day Plan](../07_roadmap/thirty_day_plan.md)
- [API Overview](../11_api/api_overview.md)
- [Navigation Structure](../10_ui/navigation_structure.md)
- [Command Policy](../03_operations/command_policy.md)
