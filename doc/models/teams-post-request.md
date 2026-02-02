
# Teams Post Request

## Structure

`TeamsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this Team. | getLogin(): string | setLogin(string login): void |
| `name` | `?string` | Optional | The name of this Team.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Team.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `autoCascadeDisabled` | [`?int(TeamsAutoCascadeDisabledEnum)`](../../doc/models/teams-auto-cascade-disabled-enum.md) | Optional | Whether new Logins created by member Logins of this Team will be added to this team or not. Default is 0 (enabled).<br><br><details><br><summary>Valid Values</summary> <br>- `0` - **Disabled**<br>- `1` - **Enabled**<br>  <br>  </details><br> | getAutoCascadeDisabled(): ?int | setAutoCascadeDisabled(?int autoCascadeDisabled): void |
| `autoCascadeOwner` | [`?int(TeamsAutoCascadeOwnerEnum)`](../../doc/models/teams-auto-cascade-owner-enum.md) | Optional | An integer-boolean indicating whether or not the cascading functionality should extend to the owner of this team.<br><br><details><br><summary>Valid Values</summary> <br>- `0` - **OFF**<br>- `1` - **ON**<br>  <br>  </details><br> | getAutoCascadeOwner(): ?int | setAutoCascadeOwner(?int autoCascadeOwner): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `alerts` | [`?(AlertsPostRequest[])`](../../doc/models/alerts-post-request.md) | Optional | - | getAlerts(): ?array | setAlerts(?array alerts): void |
| `teamLogins` | [`?(LoginsPostRequest[])`](../../doc/models/logins-post-request.md) | Optional | - | getTeamLogins(): ?array | setTeamLogins(?array teamLogins): void |
| `orgFlows` | [`?(OrgFlowsPostRequest[])`](../../doc/models/org-flows-post-request.md) | Optional | - | getOrgFlows(): ?array | setOrgFlows(?array orgFlows): void |

## Example (as JSON)

```json
{
  "login": "t1_log_6801559c6218199cb0820df",
  "name": "merchant-team-t1_mer_680155985dbaab55256ecb0",
  "description": "Esmeralda McCullough Team",
  "autoCascadeDisabled": 0,
  "autoCascadeOwner": 0,
  "inactive": 0,
  "frozen": 0
}
```

