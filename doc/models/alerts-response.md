
# Alerts Response

## Structure

`AlertsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getLogin(): | setLogin( login): void |
| `forlogin` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that this Alert applies to. | getForlogin(): | setForlogin( forlogin): void |
| `team` | string\|[TeamsResponse](../../doc/models/teams-response.md)\|null | Optional | The identifier (ID) of the team that this Alert relates to. The Alert is triggered based on the activity of this Team. | getTeam(): | setTeam( team): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division that this Alert applies to. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The partition for which this Alerts applies. | getPartition(): | setPartition( partition): void |
| `name` | `?string` | Optional | The name of this Alert.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | Description of Alerts. | getDescription(): ?string | setDescription(?string description): void |
| `alertActions` | [`?(AlertActionsResponse[])`](../../doc/models/alert-actions-response.md) | Optional | - | getAlertActions(): ?array | setAlertActions(?array alertActions): void |
| `alertTriggers` | [`?(AlertTriggersResponse[])`](../../doc/models/alert-triggers-response.md) | Optional | - | getAlertTriggers(): ?array | setAlertTriggers(?array alertTriggers): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified8",
  "creator": "String3",
  "modifier": "modifier2"
}
```

