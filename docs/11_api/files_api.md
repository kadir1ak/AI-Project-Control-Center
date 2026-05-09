# Files API

## Purpose

Files API, proje workspace içindeki dosya ağacı, dosya içeriği ve diff görüntüleme davranışını tanımlar.

## Endpoints

```text
GET   /api/v1/projects/{projectId}/files
GET   /api/v1/projects/{projectId}/files/content
GET   /api/v1/projects/{projectId}/files/diff
POST  /api/v1/projects/{projectId}/files
PATCH /api/v1/projects/{projectId}/files
```

## Request Examples

Content:

```json
{
  "path": "backend/src/Auth/AuthController.cs"
}
```

Create:

```json
{
  "path": "docs/new_note.md",
  "content": "# New Note"
}
```

## Response Examples

```json
{
  "success": true,
  "data": {
    "path": "docs/new_note.md",
    "content": "# New Note",
    "encoding": "utf-8"
  },
  "error": null,
  "meta": {}
}
```

Diff:

```json
{
  "success": true,
  "data": {
    "baseRef": "HEAD",
    "files": [
      {
        "path": "README.md",
        "status": "modified",
        "patch": "@@ ..."
      }
    ]
  },
  "error": null,
  "meta": {}
}
```

## Validation

- Path proje workspace sınırı içinde olmalıdır.
- Path traversal (`../`) engellenmelidir.
- File delete ayrı approval gerektirmelidir.
- Binary file handling MVP'de read-only olabilir.

## Security/Audit Notes

- File write audit log yazmalıdır.
- File delete approval gerektirir.
- Workspace dışına erişim blocked olmalıdır.

## Related Documents

- [Sandbox Design](../02_architecture/sandbox_design.md)
- [Security Model](../02_architecture/security_model.md)
- [Terminal Worker](../02_architecture/terminal_worker.md)
