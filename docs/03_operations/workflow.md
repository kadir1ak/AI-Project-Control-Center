# Workflow

## Ana Akış

```text
1. Kullanıcı yeni proje oluşturur.
2. Proje fikrini Ideation ekranına yazar.
3. Sistem PRD üretir.
4. Kullanıcı PRD'yi düzenler veya onaylar.
5. Sistem teknik spec ve mimari özet üretir.
6. Sistem epic ve taskları üretir.
7. Kullanıcı backlog'u onaylar.
8. Sistem tasklar için ajan ve prompt paketi önerir.
9. Ajan run başlatılır.
10. Worker gerekiyorsa dosya veya komut operasyonu yürütür.
11. Riskli işlem approval'a düşer.
12. Kullanıcı diff, log ve run sonucunu inceler.
13. Task review/test/done aşamalarından geçer.
14. Wiki, karar kayıtları ve release notları güncellenir.
```

## MVP Akışı

İlk sürümde workflow daha kontrollü olmalıdır:

```text
Idea -> PRD -> Backlog -> Task Package -> Agent Run Record -> Approval/Review -> Done
```

Kod üretimi otomatik yapılmak zorunda değildir. Prompt paketleri Cursor, Codex, Claude veya Gemini gibi araçlara verilebilir.

## Durum Geçişleri

- `Draft`: kullanıcı veya AI çıktısı henüz onaylanmamış.
- `Ready`: çalışmaya hazır.
- `Running`: ajan veya worker çalışıyor.
- `WaitingApproval`: riskli işlem onay bekliyor.
- `Review`: kullanıcı veya QA kontrolünde.
- `Done`: tamamlandı.
- `Blocked`: bağımlılık veya hata nedeniyle durmuş.

## Karar Noktaları

- PRD onayı.
- Backlog onayı.
- Riskli command onayı.
- Dosya silme onayı.
- Migration onayı.
- PR veya merge onayı.

## Kayıt Altına Alınacaklar

- Kullanıcı aksiyonları.
- AI çıktıları.
- Prompt paketleri.
- Agent run adımları.
- Terminal komutları.
- Approval kararları.
- Dosya değişiklikleri.
- Teknik kararlar.
