
# Team Login Response

## Structure

`TeamLoginResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `team` | string\|[TeamsResponse](../../doc/models/teams-response.md)\|null | Optional | The identifier of the Team resource that the Login identified in the 'login' field should be marked as part of. | getTeam(): | setTeam( team): void |
| `create` | [`?int(TeamLoginCreateEnum)`](../../doc/models/team-login-create-enum.md) | Optional | Create rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getCreate(): ?int | setCreate(?int create): void |
| `read` | [`?int(TeamLoginReadEnum)`](../../doc/models/team-login-read-enum.md) | Optional | Read rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br>**Default**: `TeamLoginReadEnum::NONE`<br> | getRead(): ?int | setRead(?int read): void |
| `update` | [`?int(TeamLoginUpdateEnum)`](../../doc/models/team-login-update-enum.md) | Optional | Update rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getUpdate(): ?int | setUpdate(?int update): void |
| `delete` | [`?int(TeamLoginDeleteEnum)`](../../doc/models/team-login-delete-enum.md) | Optional | Delete rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getDelete(): ?int | setDelete(?int delete): void |
| `reference` | [`?int(TeamLoginReferenceEnum)`](../../doc/models/team-login-reference-enum.md) | Optional | Reference use rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getReference(): ?int | setReference(?int reference): void |
| `teamAdmin` | [`?int(TeamLoginTeamAdminEnum)`](../../doc/models/team-login-team-admin-enum.md) | Optional | Team administration rights for this Login on this Team.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **None**<br>- `1` - **Allow**<br></details><br> | getTeamAdmin(): ?int | setTeamAdmin(?int teamAdmin): void |

## Example (as JSON)

```json
{
  "read": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

