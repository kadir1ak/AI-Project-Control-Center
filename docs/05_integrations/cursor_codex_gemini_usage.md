# Cursor, Codex and Gemini Usage

## Amaç

Cursor, Codex ve Gemini/Antigravity hesaplarını aynı sistem içinde rol bazlı ve kontrollü şekilde kullanmak.

## Cursor

Cursor, aktif repo geliştirme aracıdır.

Kullanım:

- Task paketini alır.
- İlgili dosyaları düzenler.
- Lokal kod tabanında değişiklik yapar.
- Diff ve test sonucu üretir.

Kural:

- Cursor'a verilen prompt her zaman task, acceptance criteria, ilgili dosyalar ve sınırlar içermelidir.

## Codex

Codex, kod üretimi, refactor, test ve repo analizi için kullanılmalıdır.

Kullanım:

- Taskları implementation planına dönüştürme.
- Çok dosyalı değişiklikleri yapma.
- Test çalıştırma.
- Hata analizi.

Kural:

- Codex'e geniş ve belirsiz görev verilmemeli; task paketleri küçük tutulmalıdır.

## Gemini / Antigravity

Gemini/Antigravity, UI ve browser doğrulama katmanında güçlüdür.

Kullanım:

- Sayfa akışlarını test etme.
- Görsel UI kontrolü.
- Browser test raporu.
- Kullanıcı deneyimi değerlendirme.

Kural:

- UI doğrulama çıktısı QA report olarak kaydedilmelidir.

## Ortak Çıktı Formatı

Her araçtan beklenen minimum çıktı:

```json
{
  "summary": "",
  "changedFiles": [],
  "commandsRun": [],
  "testResults": [],
  "risks": [],
  "requiresApproval": false,
  "nextAction": ""
}
```
