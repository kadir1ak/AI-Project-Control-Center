# Risks

## Teknik Riskler

- AI çıktılarının hatalı olması.
- Terminal komutlarının riskli olması.
- Sandbox güvenliği.
- Prompt maliyetleri.
- Uzun context yönetimi.
- Kod kalitesi.
- Çok fazla ajan karmaşası.
- GitHub ve external API permission hataları.

## Ürün Riskleri

- Kullanıcının nereden başlayacağını anlamaması.
- UI'ın fazla karmaşık olması.
- AI otomasyonuna güven eksikliği.
- Rakiplerin hızlı gelişmesi.
- API maliyetlerinin yüksek olması.
- Değerin "chatbot" gibi algılanması.

## Azaltma Yöntemleri

- MVP'yi sade tut.
- Önce planlama konsoluna odaklan.
- İnsan onayını zorunlu yap.
- Her şeyi logla.
- Task bazlı çalış.
- Küçük ajan sayısıyla başla.
- Güvenli sandbox kullan.
- Kod diff ve test sonuçlarını göster.
- Prompt paketlerini standartlaştır.

## Kritik Ürün Riski

En büyük risk, ürünü aynı anda Kanban, IDE, terminal, multi-agent framework ve SaaS platformu yapmaya çalışmaktır.

İlk sürüm net kalmalıdır:

> PRD + Backlog + Agent Prompt Packages + Approval + Run Logs.
