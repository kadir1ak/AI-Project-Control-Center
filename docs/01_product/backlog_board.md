# Backlog Board

## Amaç

Backlog Board, planlanmış işlerin görüldüğü ve süreç içinde taşındığı ana proje yönetim ekranıdır.

## Kolonlar

```text
Idea
Spec
Ready
In Progress
Review
Test
Done
Blocked
```

## Task Alanları

- Task ID.
- Title.
- Description.
- Epic.
- Priority.
- Status.
- Assigned agent.
- Dependencies.
- Risk level.
- Acceptance criteria.
- Estimated effort.
- Related files.
- Related runs.
- Approvals.
- Test status.

## Örnek Task

```text
Task ID: AUTH-003
Title: Login endpoint oluştur
Epic: Authentication
Priority: High
Assigned Agent: Backend Developer
Status: Ready
Acceptance Criteria:
- Kullanıcı email/password ile giriş yapabilmeli.
- JWT access token dönmeli.
- Hatalı şifrede 401 dönmeli.
- Unit test yazılmalı.
```

## Mikro Task Kuralları

- Task tek sorumluluk taşımalıdır.
- Task'ın input ve output'u açık olmalıdır.
- Test veya doğrulama kriteri bulunmalıdır.
- Bağımlılıkları görünür olmalıdır.
- Ajan rolü ve approval seviyesi belirtilmelidir.

## MVP Davranışı

İlk sürümde drag-and-drop Kanban yeterlidir. Gelişmiş sprint kapasite planı sonraya bırakılır.
