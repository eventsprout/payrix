
# Sessions Post Request

## Structure

`SessionsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `public` | [`?int(SessionPublicEnum)`](../../doc/models/session-public-enum.md) | Optional | Whether this Session should have access to only public resources.<br>All other resources are private. <details> <summary>Valid Values</summary><br><br>- `0` - **Session can also access private resources.**<br>- `1` - **Session can only access public resources.**<br><br> </details><br> | getPublic(): ?int | setPublic(?int public): void |
| `token` | [`?int(SessionTokenEnum)`](../../doc/models/session-token-enum.md) | Optional | Whether or not an AuthToken is required as part of the authentication when this Apikey is used.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **The authToken mechanism is disabled.**<br>- `1` - **The authToken mechanism is required for 'POST' and 'DELETE' requests.**<br></details><br> | getToken(): ?int | setToken(?int token): void |
| `mfaAuthenticated` | [`?int(SessionMfaAuthenticatedEnum)`](../../doc/models/session-mfa-authenticated-enum.md) | Optional | Whether or not the MFA is enabled.. <details> <summary>Valid Values</summary><br><br>- `0` - **MFA is disabled.**<br><br>- `1` - **MFA is enabled.**<br>  <br>  </details><br> | getMfaAuthenticated(): ?int | setMfaAuthenticated(?int mfaAuthenticated): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "p1_log_00a4d56d1b5c98e8694ae28",
  "public": 1,
  "inactive": 0,
  "frozen": 0,
  "token": 0,
  "mfaAuthenticated": 0
}
```

