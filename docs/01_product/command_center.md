# Command Center

## Amaç

Command Center, projenin ana kontrol ekranıdır. Kullanıcı burada projenin genel durumunu, aktif ajanları, bekleyen onayları ve bir sonraki önerilen aksiyonu görür.

## Gösterilecek Bilgiler

- Project name.
- Current phase.
- Progress percentage.
- Active agents.
- Open, blocked ve completed task sayıları.
- Pending approvals.
- Last run status.
- Test/build status.
- Risk level.
- Next recommended action.

## Örnek Durum

```text
Project: Clinic SaaS
Phase: MVP Planning
Progress: 34%
Active Agents: 3
Open Tasks: 27
Blocked Tasks: 3
Pending Approvals: 1
Next Action: Review generated backlog
```

## Ana Paneller

- **Project Health:** ilerleme, blokajlar, test durumu, risk.
- **Active Work:** çalışan ajanlar ve mevcut tasklar.
- **Approvals:** karar bekleyen riskli işlemler.
- **Recent Runs:** son ajan çalışmaları.
- **Next Actions:** sistemin önerdiği sıradaki işlem.

## MVP Davranışı

İlk sürümde Command Center sadece özet gösterecek:

- Proje durumu.
- Task sayıları.
- Son agent run.
- Bekleyen approval sayısı.
- Sonraki önerilen aksiyon.

Gerçek zamanlı detaylar Agent Runner ve Logs ekranlarına bırakılır.
