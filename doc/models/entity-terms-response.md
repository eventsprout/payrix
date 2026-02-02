
# Entity Terms Response

## Structure

`EntityTermsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the entity that the terms are associated with. | getEntity(): | setEntity( entity): void |
| `type` | `?string` | Optional | The type of entity that has accepted the terms. | getType(): ?string | setType(?string type): void |
| `version` | `?string` | Optional | The version of the terms that the entity has accepted. | getVersion(): ?string | setVersion(?string version): void |
| `versionId` | `?string` | Optional | The identifier of the version of the terms that the entity has accepted. | getVersionId(): ?string | setVersionId(?string versionId): void |
| `ip` | `?string` | Optional | The IP address of the entity that accepted the terms. | getIp(): ?string | setIp(?string ip): void |
| `dateAccepted` | `?string` | Optional | The date and time when the entity accepted the terms.<br>The date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDateAccepted(): ?string | setDateAccepted(?string dateAccepted): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

