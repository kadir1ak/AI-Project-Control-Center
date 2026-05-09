# Run Lifecycle

## Amaç

Run lifecycle, bir ajan çalışmasının nasıl başlatıldığını, izlendiğini ve sonuçlandırıldığını tanımlar.

## Durumlar

```text
Queued
PreparingContext
GeneratingPrompt
RunningAgent
RunningCommand
WaitingApproval
ReviewingOutput
Completed
Failed
Cancelled
```

## Standart Run Adımları

1. Task okunur.
2. İlgili PRD, spec, kararlar ve wiki context'i toplanır.
3. Ajan profili seçilir.
4. Prompt paketi üretilir.
5. Ajan çıktısı alınır.
6. Gerekirse worker operasyonu hazırlanır.
7. Riskli işlem varsa approval istenir.
8. Sonuç, log ve next action kaydedilir.

## Run Output

Her run şu çıktıları üretmelidir:

- Summary.
- Changed files veya generated artifacts.
- Commands requested veya executed.
- Test result.
- Risks.
- Approval requirement.
- Next action.

## Hata Davranışı

Run hata aldığında:

- Hata mesajı saklanır.
- Hangi adımda hata olduğu görünür.
- Kullanıcıya önerilen aksiyon sunulur.
- Task otomatik olarak `Blocked` veya `Review` durumuna alınabilir.

## MVP Kabul Kriteri

- Her run için durum takip edilir.
- Run adımları kalıcı kaydedilir.
- Hata ve sonuç görünürdür.
- Run task ile ilişkilidir.
