# AI Account Mapping

## Amaç

Mevcut AI hesaplarını doğru role yerleştirmek ve her aracın güçlü olduğu alanı netleştirmek.

## Claude

En iyi kullanım:

- PRD üretimi.
- Uzun doküman analizi.
- Mimari düşünme.
- Risk analizi.
- Code review.
- ADR ve karar metinleri.

Sınırlama:

- Doğrudan dosya ve terminal işlemleri güvenli worker olmadan yapılmamalıdır.

## GPT / Codex

En iyi kullanım:

- Kod üretimi.
- Task parçalama.
- Refactor planı.
- Test yazma.
- Repo içinde değişiklik önerme.
- Teknik açıklama ve debugging.

Sınırlama:

- Geniş kapsamlı refactor task sınırı olmadan verilmemelidir.

## Cursor

En iyi kullanım:

- Lokal repo içinde aktif geliştirme.
- Çok dosyalı düzenleme.
- Mevcut kodu okuyarak implementation.
- Geliştirici ajan gibi çalışma.

Sınırlama:

- Ürün kararlarını tek başına vermemeli; PRD/spec/context'e bağlı çalışmalıdır.

## Gemini / Antigravity

En iyi kullanım:

- UI kontrol.
- Browser tabanlı test.
- Görsel doğrulama.
- Web akışlarının test edilmesi.
- Çok modal değerlendirme.

Sınırlama:

- Backend mimari kararlarında tek otorite olmamalıdır.

## Önerilen Akış

```text
Planlama: Claude
Backlog: GPT / Codex
Kodlama: Cursor / Codex
UI ve browser doğrulama: Gemini / Antigravity
Review: Claude + GPT
Son karar: İnsan
```
