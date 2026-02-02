
# Alerts Put Request

## Structure

`AlertsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `forlogin` | `?string` | Optional | The identifier of the Login that this Alert relates to.<br>The Alert is triggered based on the activity of this Login. | getForlogin(): ?string | setForlogin(?string forlogin): void |
| `team` | `?string` | Optional | The identifier (ID) of the team that this Alert relates to. The Alert is triggered based on the activity of this Team. | getTeam(): ?string | setTeam(?string team): void |
| `division` | `?string` | Optional | The division for which this Alerts applies. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The partition for which this Alerts applies. | getPartition(): ?string | setPartition(?string partition): void |
| `name` | `?string` | Optional | The name of this Alert.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | Description of Alerts. | getDescription(): ?string | setDescription(?string description): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_61f2efc258eb7bf6d380000",
  "forlogin": "t1_log_61f2efc258eb7bf6d380000",
  "team": "t1_tem_67c202b908935b505104500",
  "division": "t1_div_67c56806728fbbf0bae0z00",
  "partition": "t1_ptn_666834d4d504f21414978f0",
  "name": "williamson",
  "description": "Used by the FrontDesk system to keep information up to date via webhook alerts",
  "inactive": 0,
  "frozen": 0
}
```

