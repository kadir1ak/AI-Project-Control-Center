# Spec Editor

## Amaç

Spec Editor, PRD'nin teknik ve fonksiyonel detaylara ayrıldığı çalışma alanıdır.

## İçerik Alanları

- Functional requirements.
- Technical requirements.
- API specification.
- Database requirements.
- UI requirements.
- Security requirements.
- Integration requirements.
- Performance requirements.
- Testing requirements.
- Deployment requirements.

## Kullanım

Spec Editor, geliştirici ajanların en önemli context kaynaklarından biridir. Kod üretim promptları PRD yerine çoğunlukla Spec Editor içeriğine dayanmalıdır.

## Örnek Teknik Kural

```text
Authentication modülü JWT tabanlı olacaktır.
Refresh token desteği olacaktır.
Kullanıcı şifresi BCrypt ile hash'lenecektir.
Login endpoint rate limit ile korunacaktır.
```

## MVP Davranışı

- PRD'den ilk spec taslağı üretilebilir.
- Kullanıcı spec alanlarını manuel düzenleyebilir.
- Her spec bölümü task üretiminde referans olarak kullanılabilir.

## Kabul Kriterleri

- Spec dokümanı proje ile ilişkilidir.
- Task üretiminde ilgili spec bölümleri kullanılabilir.
- Teknik kararlar ADR dokümanlarına bağlanabilir.
