# Sprint 01: Foundation

## Amaç

Temel ürün zeminini kurmak: frontend shell, backend shell, veri modeli ve ilk Kanban akışı.

## Kapsam

- Next.js shell.
- .NET Web API shell.
- PostgreSQL bağlantısı.
- Entity Framework Core.
- Projects, Epics, Tasks tabloları.
- Basit Kanban.

## Micro Task Listesi

| ID | Task | Çıktı | Kabul Kriteri |
| --- | --- | --- | --- |
| FND-001 | Frontend shell oluştur | Layout ve route yapısı | Sol menü ve boş ekranlar açılır |
| FND-002 | Backend API shell oluştur | `/api/v1/health` | Health endpoint başarılı döner |
| FND-003 | PostgreSQL bağlantısını planla | Connection strategy | Local dev bağlantı standardı yazılıdır |
| FND-004 | EF Core temel modelini kur | Projects, Epics, Tasks entity planı | Entity alanları data model ile uyumludur |
| FND-005 | Project CRUD ekle | API + basit UI | Proje oluşturulur ve listelenir |
| FND-006 | Task CRUD ekle | API + task detail | Task proje ile ilişkilendirilir |
| FND-007 | Kanban kolonlarını oluştur | Idea, Spec, Ready, In Progress, Review, Test, Done, Blocked | Task statüsü kolonla uyumludur |
| FND-008 | Validation ve error standardını bağla | API response standardı | Hata response formatı `api_overview.md` ile uyumludur |

## Sprint Sonu Demo

Kullanıcı yeni proje oluşturur, birkaç task ekler ve taskları Kanban kolonları arasında taşır.

## Related Documents

- [Build Order](build_order.md)
- [Data Model](../02_architecture/data_model.md)
- [Projects API](../11_api/projects_api.md)
- [Tasks API](../11_api/tasks_api.md)
- [Backlog Board Screen](../10_ui/screen_backlog_board.md)
