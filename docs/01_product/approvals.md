# Approvals

## Amaç

Approval Center, riskli veya geri dönüşü zor işlemler için insan kararını zorunlu kılar.

## Onay Gerektiren İşlemler

- Database migration çalıştırma.
- Dosya silme.
- Production deploy.
- Secret veya env değiştirme.
- Paket yükleme.
- Main branch'e push.
- Pull request merge.
- Payment sistemi değiştirme.
- Kullanıcı verisi işleme.
- External script çalıştırma.

## Approval Kartı

Her approval şunları göstermelidir:

- İşlem adı.
- Neden gerekli.
- Etkilenecek dosyalar.
- Etkilenecek servisler.
- Risk seviyesi.
- Komut önizlemesi.
- Rollback planı.
- Ajan önerisi.
- Onayla, reddet veya düzenle aksiyonları.

## Örnek

```text
Approval Request: Run database migration

Reason:
Authentication modülü için Users ve RefreshTokens tabloları oluşturulacak.

Command:
dotnet ef database update

Risk:
Medium

Rollback:
dotnet ef database update PreviousMigration
```

## MVP Davranışı

İlk sürümde approval akışı manuel olabilir. Sistem riskli işlemi çalıştırmaz; kullanıcı onay verdikten sonra run devam eder.

## Kabul Kriterleri

- Riskli işlem approval olmadan çalışmaz.
- Approval sonucu audit log'a yazılır.
- Reddedilen işlem run'ı durdurur veya alternatif aksiyon ister.
