
# Org Flows Response

## Structure

`OrgFlowsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `forlogin` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login resource for which this orgFlows resource is triggered. | getForlogin(): | setForlogin( forlogin): void |
| `team` | string\|[TeamsResponse](../../doc/models/teams-response.md)\|null | Optional | The identifier of the Team resource for which this orgFlows resource is triggered. | getTeam(): | setTeam( team): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division resource for which this orgFlows resource is triggered. | getDivision(): | setDivision( division): void |
| `trigger` | [`?string(OrgFlowTriggerEnum)`](../../doc/models/org-flow-trigger-enum.md) | Optional | This field sets the trigger that determines when this orgFlow runs.<br><br><details><br><summary>Valid Values</summary><br>- `create` - **Entity creation.**<br>- `low` - **Entity verification through decisions hits a configured low score.**<br>- `high` - **Entity verification through decisions hits a configured high score.**<br>- `board` - **Merchant boarding.**<br></details><br> | getTrigger(): ?string | setTrigger(?string trigger): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition resource for which this orgFlows resource is triggered. | getPartition(): | setPartition( partition): void |
| `orgFlowActions` | [`?(OrgFlowActionsResponse[])`](../../doc/models/org-flow-actions-response.md) | Optional | - | getOrgFlowActions(): ?array | setOrgFlowActions(?array orgFlowActions): void |
| `orgFlowRules` | [`?(OrgFlowRulesResponse[])`](../../doc/models/org-flow-rules-response.md) | Optional | - | getOrgFlowRules(): ?array | setOrgFlowRules(?array orgFlowRules): void |

## Example (as JSON)

```json
{
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

