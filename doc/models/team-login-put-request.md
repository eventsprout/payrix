
# Team Login Put Request

## Structure

`TeamLoginPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `team` | `?string` | Optional | The identifier of the Team resource that the Login identified in the 'login' field should be marked as part of. | getTeam(): ?string | setTeam(?string team): void |
| `create` | [`?int(TeamLoginCreateEnum)`](../../doc/models/team-login-create-enum.md) | Optional | Create rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getCreate(): ?int | setCreate(?int create): void |
| `read` | [`?int(TeamLoginReadEnum)`](../../doc/models/team-login-read-enum.md) | Optional | Read rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br>**Default**: `TeamLoginReadEnum::NONE`<br> | getRead(): ?int | setRead(?int read): void |
| `update` | [`?int(TeamLoginUpdateEnum)`](../../doc/models/team-login-update-enum.md) | Optional | Update rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getUpdate(): ?int | setUpdate(?int update): void |
| `delete` | [`?int(TeamLoginDeleteEnum)`](../../doc/models/team-login-delete-enum.md) | Optional | Delete rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getDelete(): ?int | setDelete(?int delete): void |
| `reference` | [`?int(TeamLoginReferenceEnum)`](../../doc/models/team-login-reference-enum.md) | Optional | Reference use rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getReference(): ?int | setReference(?int reference): void |
| `teamAdmin` | [`?int(TeamLoginTeamAdminEnum)`](../../doc/models/team-login-team-admin-enum.md) | Optional | Team administration rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getTeamAdmin(): ?int | setTeamAdmin(?int teamAdmin): void |

## Example (as JSON)

```json
{
  "login": "t1_log_6802c54cba888f6abfd88cc",
  "team": "t1_tem_6621af6c10f4a29427a2d35",
  "create": 0,
  "read": 0,
  "update": 0,
  "delete": 0,
  "reference": 0,
  "teamAdmin": 0
}
```

