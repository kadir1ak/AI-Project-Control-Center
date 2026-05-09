# Agentic Project Control Center

Web tabanlı AI yazılım üretim, planlama ve süreç yönetim sistemi.

Bu repository, **Agentic Project Control Center** fikrini profesyonel bir ürün bilgi tabanına dönüştürmek için hazırlanmıştır. İlk aşamada hedef çalışan uygulama kodu üretmek değil; ürün vizyonunu, mimariyi, ajan rollerini, workflow'u, approval sistemini, entegrasyonları, şablonları ve MVP yol haritasını netleştirmektir.

Ana ürün yönü:

> AI Project Builder Console

Kısa tanım:

> Bir yazılım fikrini alıp PRD'ye, PRD'yi backlog'a, backlog'u mikro tasklara, mikro taskları ajan görev paketlerine dönüştüren; riskli işlemleri insan onayına bağlayan ve tüm süreci web panelinden izlenebilir hale getiren AI-native geliştirme operasyon merkezi.

## İçindekiler

- [Proje Amacı](#proje-amacı)
- [Ürün Kararı](#ürün-kararı)
- [Neden Bu Ürün](#neden-bu-ürün)
- [Ana Ürün Bileşenleri](#ana-ürün-bileşenleri)
- [Hedef Mimari](#hedef-mimari)
- [Ajan Modeli](#ajan-modeli)
- [Güvenlik ve Approval Yaklaşımı](#güvenlik-ve-approval-yaklaşımı)
- [Repository Yapısı](#repository-yapısı)
- [Dokümantasyon Haritası](#dokümantasyon-haritası)
- [MVP Kapsamı](#mvp-kapsamı)
- [Önerilen Teknoloji Stack'i](#önerilen-teknoloji-stacki)
- [Çalışma Akışı](#çalışma-akışı)
- [Kullanım Senaryosu](#kullanım-senaryosu)
- [Yol Haritası](#yol-haritası)
- [Mevcut Durum](#mevcut-durum)

## Proje Amacı

Agentic Project Control Center'ın amacı, yazılım projelerini fikir aşamasından uygulanabilir geliştirme planına kadar sistematik hale getirmektir.

Sistem şu alanları tek bir ürün deneyiminde birleştirmeyi hedefler:

- Ürün fikri analizi.
- PRD üretimi.
- Teknik spec üretimi.
- Mimari kararlar.
- Backlog ve mikro task üretimi.
- Ajan rol dağılımı.
- Prompt paketi üretimi.
- Agent run kayıtları.
- Terminal/worker logları.
- Riskli işlem approval akışı.
- Wiki ve karar hafızası.

Bu yapı sadece bir chatbot, sadece bir Kanban board veya sadece bir terminal değildir. Ürün fikri; web arayüzü, agent runner, backlog, approval center, güvenli terminal worker ve proje hafızasını birlikte düşünür.

## Ürün Kararı

İlk ürün formu:

```text
Web UI
+ Planning Console
+ Backlog Board
+ Agent Runner
+ Prompt Engine
+ Approval Center
+ Terminal Worker Logs
+ Context and Wiki
```

İlk MVP varsayımı:

> AI destekli yarı otonom planlama konsolu.

Bu nedenle ilk aşamada odak:

- PRD.
- Backlog.
- Mikro task.
- Agent profile.
- Prompt package.
- Approval request.
- Run lifecycle.
- Dokümantasyon bilgi tabanı.

Terminal worker ve sandbox mimarisi tasarlanmıştır; ancak bu repository'nin mevcut halinde çalışan Next.js, .NET veya worker uygulama kodu yoktur.

## Neden Bu Ürün

Modern AI araçları yazılım geliştirmeyi hızlandırıyor; ancak çoğu zaman süreç dağınık ilerliyor:

- Planlama ayrı yerde, kodlama ayrı yerde kalıyor.
- AI çıktıları proje hafızasına dönüşmüyor.
- Hangi ajan ne yaptı geriye dönük izlenemiyor.
- Terminal komutları güvenli approval akışından geçmiyor.
- PRD, backlog, prompt, test ve release süreci kopuk ilerliyor.
- AI ile yapılan işler tekrarlanabilir ve denetlenebilir olmuyor.

Agentic Project Control Center bu boşluğu kapatmayı hedefler:

> AI ajanları çalışır; ama her şey task, context, approval, log ve insan kararıyla yönetilir.

## Ana Ürün Bileşenleri

### Command Center

Projenin genel durumunu gösteren ana dashboard.

Göstereceği özetler:

- Proje fazı.
- İlerleme yüzdesi.
- Aktif ajanlar.
- Açık ve bloklu tasklar.
- Bekleyen approval'lar.
- Son run durumu.
- Sonraki önerilen aksiyon.

### Ideation

Kullanıcının ham proje fikrini yapılandırılmış ürün fikrine dönüştüren ekran.

Çıktıları:

- Problem tanımı.
- Hedef kullanıcı.
- MVP kapsamı.
- Riskler.
- Varsayımlar.
- İlk ürün yönü.

### PRD Editor

Ürün gereksinim dokümanının üretildiği ve düzenlendiği alan.

İçerik örnekleri:

- Ürün amacı.
- Hedef kullanıcılar.
- Ana özellikler.
- Kullanıcı akışları.
- Acceptance criteria.
- MVP ve MVP dışı kapsam.

### Spec Editor

Teknik ve fonksiyonel gereksinimlerin netleştirildiği alan.

İçerik örnekleri:

- API gereksinimleri.
- Database gereksinimleri.
- UI gereksinimleri.
- Security requirements.
- Testing requirements.

### Backlog Board

Epic ve taskların yönetildiği Kanban alanı.

Önerilen kolonlar:

```text
Idea -> Spec -> Ready -> In Progress -> Review -> Test -> Done -> Blocked
```

### Agent Runner

Ajan çalışmalarını chat ekranı gibi değil, yapılandırılmış run kayıtları olarak gösteren ekran.

Her run şunları tutar:

- Agent role.
- Task.
- Status.
- Steps.
- Used context.
- Commands.
- Errors.
- Result.
- Next action.

### Approval Center

Riskli veya geri dönüşü zor işlemlerin insan onayına düştüğü alan.

Örnek approval işlemleri:

- Database migration.
- Dosya silme.
- Production deploy.
- Secret/env değişikliği.
- Main branch'e push.
- PR merge.
- External script çalıştırma.

### Wiki

Proje hafızasıdır.

İçerikler:

- Architecture notes.
- API docs.
- Database docs.
- Decision logs.
- Agent instructions.
- Troubleshooting.

## Hedef Mimari

Genel mimari:

```text
Web UI
  -> Backend API
  -> Orchestrator Service
  -> Worker Runtime
  -> Sandbox
```

Detaylı görünüm:

```text
┌─────────────────────────────────────────────┐
│                  Web UI                     │
│  Dashboard | Kanban | Agent Runner | Logs   │
│  Terminal  | Files  | Diagrams | Approvals  │
└─────────────────────┬───────────────────────┘
                      │
┌─────────────────────▼───────────────────────┐
│                Backend API                  │
│  Projects | Tasks | Agents | Runs | Logs    │
│  Auth | Permissions | Audit                 │
└─────────────────────┬───────────────────────┘
                      │
┌─────────────────────▼───────────────────────┐
│             Orchestrator Service            │
│  Planner | Router | Context Builder         │
│  Prompt Engine | Approval Manager           │
└─────────────────────┬───────────────────────┘
                      │
┌─────────────────────▼───────────────────────┐
│              Worker Runtime                 │
│  Terminal Commands | File Ops | Git Ops     │
│  Test Runner | Build Runner                 │
└─────────────────────┬───────────────────────┘
                      │
┌─────────────────────▼───────────────────────┐
│                  Sandbox                    │
│  Isolated Project Folder / Docker Container │
└─────────────────────────────────────────────┘
```

Ana prensip:

> Web panel karar merkezidir. Worker üretim merkezidir. Orchestrator süreç ve güvenlik katmanıdır.

## Ajan Modeli

MVP için önerilen çekirdek ajan rolleri:

```text
Planner Agent
Product Owner Agent
Architect Agent
Developer Agent
QA / Reviewer Agent
```

Rollerin kısa görevleri:

- **Planner Agent:** fikri analiz eder, kapsam ve roadmap çıkarır.
- **Product Owner Agent:** PRD, user story ve acceptance criteria üretir.
- **Architect Agent:** mimari, database, API ve ADR önerileri çıkarır.
- **Developer Agent:** task bazlı implementation paketi ve kod çıktısı üretir.
- **QA / Reviewer Agent:** acceptance criteria, test ve risk kontrolü yapar.

Mevcut AI hesapları için önerilen eşleşme:

```text
Claude:
  PRD, mimari, uzun doküman analizi, risk analizi, review.

GPT / Codex:
  Kod üretimi, task parçalama, refactor, test yazma, repo analizi.

Cursor:
  Lokal repo içinde aktif geliştirme, çok dosyalı düzenleme.

Gemini / Antigravity:
  UI kontrol, browser test, görsel doğrulama, web akışı testi.
```

## Güvenlik ve Approval Yaklaşımı

Bu ürünün kritik ilkesi:

> Terminal komutları doğrudan host üzerinde çalışmamalıdır.

Doğru akış:

```text
Web UI
  -> Backend API
  -> Command Policy Engine
  -> Worker Runtime
  -> Docker Sandbox
  -> Project Directory
```

Komut sınıfları:

- `safe`: otomatik çalışabilir.
- `approval_required`: insan onayı gerekir.
- `blocked`: çalıştırılmaz.

Onay gerektiren örnek işlemler:

- `rm -rf`
- `drop database`
- `git push origin main`
- `deploy production`
- `curl unknown-script | bash`
- `chmod -R 777`
- Secret/env değişikliği.
- Dosya silme.
- Migration.

Varsayılan güvenlik yaklaşımı:

- Ajanlar plan yapabilir.
- Ajanlar context okuyabilir.
- Dosya yazma kontrollü worker üzerinden yapılır.
- Riskli komutlar approval ister.
- Production etkisi olan işlemler her zaman approval ister.
- Her komut, run ve approval audit log'a yazılır.

## Repository Yapısı

```text
.
├── README.md
├── agentic_project_control_center_plan.md
├── archive/
│   └── original/
│       └── agentic_project_control_center_plan.original.md
└── docs/
    ├── 00_overview/
    ├── 01_product/
    ├── 02_architecture/
    ├── 03_operations/
    ├── 04_agents/
    ├── 05_integrations/
    ├── 06_templates/
    ├── 07_roadmap/
    └── 08_business/
```

Kök dosyalar:

- [agentic_project_control_center_plan.md](agentic_project_control_center_plan.md): ana indeks ve dokümantasyon giriş noktası.
- [archive/original/agentic_project_control_center_plan.original.md](archive/original/agentic_project_control_center_plan.original.md): ilk uzun strateji dokümanının arşivlenmiş hali.

## Dokümantasyon Haritası

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

## MVP Kapsamı

İlk sürümde yapılacaklar:

- Proje oluşturma.
- Proje fikri girme.
- AI ile PRD üretme.
- PRD'den epic/task üretme.
- Kanban board.
- Task detay sayfası.
- Prompt paketi üretme.
- Ajan profilleri.
- Agent run kaydı.
- Approval Center.
- Terminal log tasarımı.
- Mermaid diagram taslağı.
- Wiki sayfası.

İlk sürümde yapılmayacaklar:

- Tam otonom production deploy.
- Enterprise role management.
- Marketplace.
- Karmaşık multi-agent framework.
- Sıfırdan IDE geliştirme.
- Çoklu tenant billing sistemi.
- Gelişmiş analytics.

## Önerilen Teknoloji Stack'i

Frontend:

```text
Next.js
React
Tailwind CSS
shadcn/ui
xterm.js
Mermaid
```

Backend:

```text
.NET 8 veya .NET 9 Web API
Entity Framework Core
PostgreSQL
SignalR
```

Worker:

```text
.NET Worker Service
Docker sandbox
Command policy engine
Git integration
```

Queue ve async işlemler:

```text
Redis + Hangfire
veya
RabbitMQ + MassTransit
```

AI Provider:

```text
OpenAI API
Anthropic API
Google Gemini API
```

Git:

```text
GitHub API
GitHub MCP Server
```

## Çalışma Akışı

Ana ürün akışı:

```text
Idea
  -> PRD
  -> Technical Spec
  -> Architecture
  -> Backlog
  -> Micro Tasks
  -> Agent Prompt Packages
  -> Agent Runs
  -> Approval / Review
  -> Done
```

Örnek:

1. Kullanıcı "Klinikler için randevu, hasta takip ve ödeme modülü olan bir SaaS yapmak istiyorum" der.
2. Sistem problem, hedef kullanıcı ve MVP kapsamı çıkarır.
3. Sistem PRD üretir.
4. Kullanıcı PRD'yi onaylar.
5. Sistem mimari ve backlog üretir.
6. Sistem taskları ajan rollerine dağıtır.
7. Developer Agent için prompt paketi hazırlanır.
8. Worker gerekiyorsa komut veya dosya işlemi önerir.
9. Riskli işlem approval'a düşer.
10. Kullanıcı log, diff ve sonuçları inceler.

## Kullanım Senaryosu

Demo proje:

> Mini CRM SaaS

Demo kapsamı:

- Authentication.
- Customer management.
- Contact management.
- Simple dashboard.
- PostgreSQL database.
- .NET Web API backend.
- Next.js frontend.
- Docker compose.
- README.
- Basic tests.

Demo başarı mesajı:

> Kullanıcı ham fikrini girer; sistem PRD, mimari özet, backlog, mikro task ve ajan görev paketlerini üretir.

## Yol Haritası

### Ay 1: MVP

- Proje oluşturma.
- PRD üretme.
- Backlog oluşturma.
- Kanban.
- Prompt Engine.
- Agent Runner.
- Basit log ekranı.
- Approval Center.

### Ay 2: Kod Üretim ve Git Entegrasyonu

- GitHub repo bağlama.
- Branch oluşturma.
- Dosya diff gösterme.
- PR hazırlama.
- Test komutları çalıştırma.
- Build logları.
- QA report.
- Mermaid diagramlar.
- Wiki otomasyonu.

### Ay 3: Pilot Kullanım ve Ürünleştirme

- Gerçek SaaS projesi üzerinde pilot.
- Prompt template iyileştirme.
- Agent profile iyileştirme.
- Kullanıcı onboarding.
- Demo proje şablonları.
- Billing hazırlığı.
- Landing page.
- Private beta.

## Mevcut Durum

Bu repository şu anda bir **dokümantasyon ve ürün planlama deposudur**.

Mevcut durumda:

- Ana indeks hazır.
- Orijinal uzun plan arşivlendi.
- Ürün bilgi tabanı `docs/` altında bölümlendi.
- Ajan rolleri, approval lifecycle, worker güvenliği, entegrasyon rehberleri ve şablonlar yazıldı.
- README proje giriş noktası olarak eklendi.

Henüz mevcut olmayanlar:

- Next.js frontend uygulaması.
- .NET Web API uygulaması.
- PostgreSQL migrationları.
- Docker worker runtime.
- Çalışan GitHub MCP entegrasyon kodu.
- Gerçek terminal execution katmanı.

## Katkı ve Çalışma Notu

Bu proje önce dokümantasyonla düşünülmeli, sonra kodlanmalıdır.

Önerilen çalışma sırası:

1. Product ve architecture dokümanlarını güncelle.
2. MVP kapsamını kesinleştir.
3. Veri modelini netleştir.
4. Prompt ve agent profile template'lerini olgunlaştır.
5. Sonra frontend/backend/worker scaffold aşamasına geç.

Kritik ilke:

> Önce plan, sonra kod. Önce güvenlik, sonra otomasyon.
