
# Api Keys Post Request

## Structure

`ApiKeysPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The login under which to perform this action. If you do not supply a login in this field, then the API defaults to the login that is currently authenticated. | getLogin(): string | setLogin(string login): void |
| `name` | `?string` | Optional | The name for the key. An apikey may represent a private (secret) key code that is used internally (server-side) by the application authenticating to the API.<br><br>A private key should never be exposed to external/untrusted entities and should be immediately deactivated if compromised. All API resources and actions can be accessed/performed with a private apikey. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | Description of ApiKeys. | getDescription(): ?string | setDescription(?string description): void |
| `public` | [`?int(ApiKeyPublicEnum)`](../../doc/models/api-key-public-enum.md) | Optional | Whether this API key should have access to only public resources.<br>Public resources include Transactions, Tokens, Customers, and Items.<br>All other resources are private. <details> <summary>Valid Values</summary><br><br>- `0` - **The key can also access private resources.**<br>- `1` - **The key can only access public resources.**<br><br> </details><br> | getPublic(): ?int | setPublic(?int public): void |
| `token` | [`?int(ApikeysTokenEnum)`](../../doc/models/apikeys-token-enum.md) | Optional | Whether or not an AuthToken is required as part of the authentication when this Apikey is used.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **The authToken mechanism is disabled.**<br>- `1` - **The authToken mechanism is required for 'POST' and 'DELETE' requests.**<br></details><br> | getToken(): ?int | setToken(?int token): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "id": "t1_api_676a5353d67a6df2c47b198",
  "created": "2024-12-24 01:23:15.8882",
  "modified": "2024-12-24 01:23:15.8882",
  "creator": "t1_log_651fec1e202e349386ba321",
  "modifier": "t1_log_651fec1e202e349386ba321",
  "login": "t1_log_651fec1e202e349386ba321",
  "key": "f0d9fd14f9795590c01dd2c8083a35d7",
  "name": "api",
  "description": "API KEYS",
  "public": 0,
  "inactive": 0,
  "frozen": 0,
  "token": 0
}
```

