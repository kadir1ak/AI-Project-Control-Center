# Agent Team Model

## Amaç

Agent team model, çoklu AI araçlarını kontrolsüz bir sohbet zinciri yerine görev bazlı bir ekip yapısına dönüştürür.

## Temel Yaklaşım

MVP'de 12 ajan yerine 5 çekirdek rol kullanılmalıdır:

```text
Planner Agent
Product Owner Agent
Architect Agent
Developer Agent
QA / Reviewer Agent
```

Bu roller daha sonra alt uzmanlıklara bölünebilir.

## Hiyerarşi

```text
Human Owner
  -> Orchestrator
    -> Planner Agent
    -> Product Owner Agent
    -> Architect Agent
    -> Developer Agent
    -> QA / Reviewer Agent
```

## Orchestrator Sorumluluğu

Orchestrator şunları belirler:

- Hangi task hangi ajana gider.
- Hangi context kullanılacak.
- Hangi prompt template seçilecek.
- Hangi işlem approval ister.
- Run hangi durumda tamamlanır veya durur.

## Ajan Takım Prensipleri

- Ajanlar serbest çalışmaz; task paketiyle çalışır.
- Her ajan rol bazlı yetkiye sahiptir.
- Her ajan çıktısı kalıcı run kaydı üretir.
- Terminal işlemleri worker ve policy katmanından geçer.
- İnsan son karar vericidir.

## Subagent ve Team Model Ayrımı

Subagent modeli küçük işler için uygundur: ana ajan işi böler, alt ajanlar çıktı döner.

Team model daha profesyoneldir: ortak task listesi, rol bazlı sorumluluk ve kontrollü görev dağıtımı vardır.

Bu ürün için uzun vadede doğru model: **Agent Teams + Shared Task List + Approval Layer**.
