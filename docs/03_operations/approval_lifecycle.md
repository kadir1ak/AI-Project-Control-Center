# Approval Lifecycle

## Amaç

Approval lifecycle, riskli işlemlerin insan kararı olmadan çalışmamasını sağlar.

## Durumlar

```text
Requested
PendingReview
Approved
Rejected
Expired
Cancelled
Executed
FailedAfterApproval
```

## Approval Oluşturma

Approval şu durumlarda oluşturulur:

- Command policy `approval_required` döner.
- Ajan dosya silmek ister.
- Migration veya deploy gibi geri dönüşü zor işlem istenir.
- Secret/env değişikliği önerilir.
- GitHub üzerinde PR merge veya main branch push istenir.

## Approval İçeriği

Her approval'da şunlar olmalıdır:

- Title.
- Action type.
- Reason.
- Risk level.
- Command preview.
- Affected files/services.
- Rollback plan.
- Requesting run.
- Approve/reject notes.

## Onay Sonrası

Onay verilirse:

1. Approval `Approved` olur.
2. Worker işlemi çalıştırır.
3. Command log approval ID ile bağlanır.
4. Sonuç `Executed` veya `FailedAfterApproval` olur.

Reddedilirse:

1. Approval `Rejected` olur.
2. Run durur veya alternatif aksiyon ister.
3. Task `Blocked` veya `Review` durumuna alınır.

## MVP Kabul Kriteri

- Riskli işlem otomatik çalışmaz.
- Kullanıcı approval kartında neyin neden istendiğini görür.
- Approval kararı audit log'a yazılır.
- Approval run ve task ile ilişkilidir.
