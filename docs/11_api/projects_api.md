# Projects API

## Purpose

Project endpointleri proje oluşturma, listeleme, güncelleme ve arşivleme davranışını tanımlar.

## Endpoints

```text
GET    /api/v1/projects
POST   /api/v1/projects
GET    /api/v1/projects/{projectId}
PATCH  /api/v1/projects/{projectId}
DELETE /api/v1/projects/{projectId}
```

## Request Examples

```json
{
  "name": "Clinic SaaS",
  "description": "Randevu, hasta takip ve ödeme modülü olan SaaS",
  "status": "planning",
  "techStack": ["Next.js", ".NET", "PostgreSQL"]
}
```

## Response Examples

```json
{
  "success": true,
  "data": {
    "id": "project_123",
    "name": "Clinic SaaS",
    "status": "planning",
    "createdAt": "2026-05-09T10:00:00Z"
  },
  "error": null,
  "meta": {}
}
```

## Validation

- `name` zorunludur.
- `name` boş veya sadece whitespace olamaz.
- `status` izin verilen project status değerlerinden biri olmalıdır.
- Delete, MVP'de soft delete/archive olarak ele alınmalıdır.

## Security/Audit Notes

- Create/update/delete işlemleri audit log yazmalıdır.
- Delete/archive işlemi yüksek etki yaratıyorsa approval gerektirebilir.
- Project ownership kontrolü zorunludur.

## Related Documents

- [Data Model](../02_architecture/data_model.md)
- [Audit Logging](../02_architecture/audit_logging.md)
- [Build Order](../09_execution/build_order.md)
