
# Session Post Response

## Structure

`SessionPostResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `key` | `?string` | Optional | The cryptographically secure, randomly generated key to be used in authentication. | getKey(): ?string | setKey(?string key): void |
| `public` | [`?int(SessionPublicEnum)`](../../doc/models/session-public-enum.md) | Optional | Whether this Session should have access to only public resources.<br>All other resources are private. <details> <summary>Valid Values</summary><br><br>- `0` - **Session can also access private resources.**<br>- `1` - **Session can only access public resources.**<br><br> </details><br> | getPublic(): ?int | setPublic(?int public): void |
| `sso` | [`?int(SessionSsoEnum)`](../../doc/models/session-sso-enum.md) | Optional | Whether or not the Session is created using SSO. <details> <summary>Valid Values</summary><br><br>- `0` - **Session not created with SSO.**<br><br>- `1` - **Session created with SSO.**<br>  <br>  </details><br> | getSso(): ?int | setSso(?int sso): void |
| `token` | [`?int(SessionTokenEnum)`](../../doc/models/session-token-enum.md) | Optional | Whether or not an AuthToken is required as part of the authentication when this Apikey is used.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **The authToken mechanism is disabled.**<br>- `1` - **The authToken mechanism is required for 'POST' and 'DELETE' requests.**<br></details><br> | getToken(): ?int | setToken(?int token): void |
| `mfaAuthenticated` | [`?int(SessionMfaAuthenticatedEnum)`](../../doc/models/session-mfa-authenticated-enum.md) | Optional | Whether or not the MFA is enabled.. <details> <summary>Valid Values</summary><br><br>- `0` - **MFA is disabled.**<br><br>- `1` - **MFA is enabled.**<br>  <br>  </details><br> | getMfaAuthenticated(): ?int | setMfaAuthenticated(?int mfaAuthenticated): void |
| `effectiveRoles` | `?float` | Optional | Effective roles for this login. | getEffectiveRoles(): ?float | setEffectiveRoles(?float effectiveRoles): void |
| `effectiveResources` | `?string` | Optional | Array of all resources the login has access to with corresponding actions. | getEffectiveResources(): ?string | setEffectiveResources(?string effectiveResources): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

