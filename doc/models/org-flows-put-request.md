
# Org Flows Put Request

## Structure

`OrgFlowsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this resource. | getLogin(): string | setLogin(string login): void |
| `forlogin` | `?string` | Optional | The identifier of the Login resource for which this orgFlows resource is triggered. | getForlogin(): ?string | setForlogin(?string forlogin): void |
| `team` | `?string` | Optional | The identifier of the Team resource for which this orgFlows resource is triggered. | getTeam(): ?string | setTeam(?string team): void |
| `division` | `?string` | Optional | The identified of the Division resource for which this orgFlows resource is triggered. | getDivision(): ?string | setDivision(?string division): void |
| `trigger` | [`string(OrgFlowTriggerEnum)`](../../doc/models/org-flow-trigger-enum.md) | Required | This field sets the trigger that determines when this orgFlow runs.<br><br><details><br><summary>Valid Values</summary><br>- `create` - **Entity creation.**<br>- `low` - **Entity verification through decisions hits a configured low score.**<br>- `high` - **Entity verification through decisions hits a configured high score.**<br>- `board` - **Merchant boarding.**<br></details><br> | getTrigger(): string | setTrigger(string trigger): void |
| `partition` | `?string` | Optional | The identified of the Partition resource for which this orgFlows resource is triggered. | getPartition(): ?string | setPartition(?string partition): void |

## Example (as JSON)

```json
{
  "login": "g1577139c2304b7",
  "forlogin": "t1_log_67c203583fbd0a4437d1332",
  "team": "t1_tem_67c202b908935b505104500",
  "division": "t1_div_67c56806728fbbf0bae0b10",
  "trigger": "create",
  "partition": "t1_ptn_666834d4d504f21414978f5"
}
```

