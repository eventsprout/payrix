
# Rev Share Statments Response

## Structure

`RevShareStatmentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `revShareSchedule` | string\|[RevShareSchedulesResponse](../../doc/models/rev-share-schedules-response.md)\|null | Optional | The RevShareSchedule object defines specific income sharing rules. | getRevShareSchedule(): | setRevShareSchedule( revShareSchedule): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The Entities object which is collecting the money. | getEntity(): | setEntity( entity): void |
| `forentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The Entities object which is paying the money. | getForentity(): | setForentity( forentity): void |
| `billing` | `?string` | Optional | The billing date of rev share statement. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getBilling(): ?string | setBilling(?string billing): void |
| `revenueShare` | `?float` | Optional | The cost to the partner for rev share enabled items, This field is specified in cents(up to three decimal points) | getRevenueShare(): ?float | setRevenueShare(?float revenueShare): void |

## Example (as JSON)

```json
{
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

