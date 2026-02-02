
# Credentials Put Request

## Structure

`CredentialsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The name of this Credential resource.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Credential resource.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `username` | `?string` | Optional | The username to use when authenticating to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getUsername(): ?string | setUsername(?string username): void |
| `password` | `?string` | Optional | The password to use when authenticating to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long. | getPassword(): ?string | setPassword(?string password): void |
| `connectUsername` | `?string` | Optional | The username to use when connecting to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long.<br>This field is only necessary when it is required by the integration. | getConnectUsername(): ?string | setConnectUsername(?string connectUsername): void |
| `connectPassword` | `?string` | Optional | The password to use when connecting to the integration associated with this Credential resource.<br>This field is stored as a text string and must be between 1 and 50 characters long.<br>This field is only necessary when it is required by the integration. | getConnectPassword(): ?string | setConnectPassword(?string connectPassword): void |
| `secret` | `?string` | Optional | The secret resource identifier to use when connecting using this Credential.<br>This field is only necessary when a private key is required by the integration. | getSecret(): ?string | setSecret(?string secret): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "username": "JDoe123",
  "name": "name of Credential resource",
  "description": "description of Credential resource",
  "password": "password",
  "connectUsername": "username connecting to integration",
  "connectPassword": "password",
  "secret": "secret resource identifier",
  "inactive": 0,
  "frozen": 0
}
```

