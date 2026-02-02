
# Org Entities Post Request

## Structure

`OrgEntitiesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `org` | string\|[OrgsPostRequest](../../doc/models/orgs-post-request.md) | Required | The identifier of the Org that this orgEntity is associated with. | getOrg(): | setOrg( org): void |
| `entity` | `string` | Required | The identifier of the Entity that this orgEntity is associated with. | getEntity(): string | setEntity(string entity): void |

## Example (as JSON)

```json
{
  "org": "t1_org_5b0e08025ec790d3f9b8c11",
  "entity": "t1_ent_10c99d558e910765c164a01"
}
```

