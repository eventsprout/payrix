
# Entity Custom Fields Post Request

## Structure

`EntityCustomFieldsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | string\|[EntitiesPostRequest](../../doc/models/entities-post-request.md)\|null | Optional | Entity for which we are creating custom field. | getEntity(): | setEntity( entity): void |
| `key` | `?string` | Optional | Name of custom field. | getKey(): ?string | setKey(?string key): void |
| `value` | `?string` | Optional | Value of custom field. | getValue(): ?string | setValue(?string value): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_67d3ab7bc0ef1d4284d4578",
  "key": "companyId",
  "value": "70bbd35e-8500-f011-90cb-6045bdc7c168"
}
```

