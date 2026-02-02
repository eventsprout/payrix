
# Apple Domains Mass Enablement Data Preview

## Structure

`AppleDomainsMassEnablementDataPreview`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dataPreview` | [`?(AppleDomainsMassEnablementDataPreviewItem[])`](../../doc/models/apple-domains-mass-enablement-data-preview-item.md) | Optional | - | getDataPreview(): ?array | setDataPreview(?array dataPreview): void |
| `msg` | `?string` | Optional | - | getMsg(): ?string | setMsg(?string msg): void |
| `status` | `?string` | Optional | - | getStatus(): ?string | setStatus(?string status): void |

## Example (as JSON)

```json
{
  "dataPreview": [
    {
      "merchantId": "merchantId2",
      "domain": "domain2"
    },
    {
      "merchantId": "merchantId2",
      "domain": "domain2"
    },
    {
      "merchantId": "merchantId2",
      "domain": "domain2"
    }
  ],
  "msg": "msg4",
  "status": "status0"
}
```

