# Agent Runner

## Amaç

Agent Runner, ajan çalışmalarını chat ekranı gibi değil, yapılandırılmış run kayıtları olarak yönetir.

## Run Alanları

- Agent name.
- Role.
- Current task.
- Status.
- Started at.
- Finished at.
- Steps.
- Used context.
- Generated files.
- Executed commands.
- Errors.
- Result.
- Next action.
- Approval required.

## Örnek Run

```text
Agent: Backend Developer
Task: AUTH-004 Login endpoint oluştur
Status: Running

Step 1: Reading project context - Done
Step 2: Reading authentication spec - Done
Step 3: Generating AuthController.cs - Done
Step 4: Running dotnet test - Failed
Step 5: Analyzing error - Running
```

## Run Tipleri

- Planning run.
- Backlog generation run.
- Prompt generation run.
- Code generation run.
- QA/review run.
- Terminal command run.

## MVP Davranışı

İlk sürümde Agent Runner en azından şunları göstermelidir:

- Hangi task çalışıyor.
- Hangi ajan çalışıyor.
- Hangi adım tamamlandı.
- Hata varsa ne oldu.
- Sonraki önerilen aksiyon nedir.
- Approval gerekiyor mu.

## Kabul Kriterleri

- Her agent run kalıcı kaydedilir.
- Run adımları sıralı görünür.
- Run çıktısı task ile ilişkilidir.
- Hata, log ve approval bağlantıları görülebilir.
