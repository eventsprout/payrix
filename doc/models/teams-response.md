
# Teams Response

## Structure

`TeamsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this Team. | getLogin(): | setLogin( login): void |
| `name` | `?string` | Optional | The name of this Team.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Team.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `autoCascadeDisabled` | [`?int(TeamsAutoCascadeDisabledEnum)`](../../doc/models/teams-auto-cascade-disabled-enum.md) | Optional | Whether new Logins created by member Logins of this Team will be added to this team or not. Default is 0 (enabled).<br><br><details><br><summary>Valid Values</summary> <br>- `0` - **Disabled**<br>- `1` - **Enabled**<br>  <br>  </details><br> | getAutoCascadeDisabled(): ?int | setAutoCascadeDisabled(?int autoCascadeDisabled): void |
| `autoCascadeOwner` | [`?int(TeamsAutoCascadeOwnerEnum)`](../../doc/models/teams-auto-cascade-owner-enum.md) | Optional | An integer-boolean indicating whether or not the cascading functionality should extend to the owner of this team.<br><br><details><br><summary>Valid Values</summary> <br>- `0` - **OFF**<br>- `1` - **ON**<br>  <br>  </details><br> | getAutoCascadeOwner(): ?int | setAutoCascadeOwner(?int autoCascadeOwner): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `aggregations` | [`?(AggregationsResponse[])`](../../doc/models/aggregations-response.md) | Optional | - | getAggregations(): ?array | setAggregations(?array aggregations): void |
| `alerts` | [`?(AlertsResponse[])`](../../doc/models/alerts-response.md) | Optional | - | getAlerts(): ?array | setAlerts(?array alerts): void |
| `teamLogins` | [`?(LoginsResponse[])`](../../doc/models/logins-response.md) | Optional | - | getTeamLogins(): ?array | setTeamLogins(?array teamLogins): void |
| `orgFlows` | [`?(OrgFlowsResponse[])`](../../doc/models/org-flows-response.md) | Optional | - | getOrgFlows(): ?array | setOrgFlows(?array orgFlows): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

