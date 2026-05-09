# Task Lifecycle

## Amaç

Task lifecycle, her işin fikirden tamamlanmaya kadar aynı disiplinle ilerlemesini sağlar.

## Durumlar

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

## Durum Açıklamaları

### Idea

Task henüz ham fikirdir. Scope ve kabul kriterleri net değildir.

### Spec

Task açıklaması, input, output, bağımlılık ve acceptance criteria netleştirilir.

### Ready

Task ajan veya kullanıcı tarafından çalışılmaya hazırdır.

### In Progress

Task için agent run veya manuel çalışma başlamıştır.

### Review

Çıktı incelenir. Diff, prompt sonucu, log veya doküman değişikliği kontrol edilir.

### Test

Acceptance criteria ve test sonuçları doğrulanır.

### Done

Task tamamlanmıştır ve ilişkili run sonucu kayıtlıdır.

### Blocked

Task bağımlılık, hata, eksik bilgi veya approval beklediği için durmuştur.

## Task Hazır Olma Kriteri

Bir task `Ready` olabilmek için şunlara sahip olmalıdır:

- Net başlık.
- Kısa açıklama.
- Epic bağlantısı.
- Acceptance criteria.
- Girdi ve çıktı.
- Bağımlılıklar.
- Önerilen ajan rolü.
- Risk seviyesi.

## Task Tamamlanma Kriteri

Bir task `Done` olabilmek için:

- Acceptance criteria karşılanmalıdır.
- Run veya manuel çalışma sonucu kaydedilmelidir.
- Varsa test sonucu eklenmelidir.
- Varsa approval kapanmış olmalıdır.
- Sonraki aksiyon net olmalıdır.
