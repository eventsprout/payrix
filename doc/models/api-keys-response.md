
# Api Keys Response

## Structure

`ApiKeysResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getLogin(): | setLogin( login): void |
| `key` | `?string` | Optional | The cryptographically secure, randomly generated key to be used<br>in authentication.<br><br>An apikey may represent a private (secret) key code that is used internally (server-side) by the application authenticating to the API.<br><br>A private key should never be exposed to external/untrusted entities and should be immediately deactivated if compromised. All API resources and actions can be accessed and performed with a private apikey. | getKey(): ?string | setKey(?string key): void |
| `name` | `?string` | Optional | The name of the API key. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | Description of the ApiKey. | getDescription(): ?string | setDescription(?string description): void |
| `public` | [`?int(ApiKeyPublicEnum)`](../../doc/models/api-key-public-enum.md) | Optional | Whether this API key should have access to only public resources.<br>Public resources include Transactions, Tokens, Customers, and Items.<br>All other resources are private. <details> <summary>Valid Values</summary><br><br>- `0` - **The key can also access private resources.**<br>- `1` - **The key can only access public resources.**<br><br> </details><br> | getPublic(): ?int | setPublic(?int public): void |
| `token` | [`?int(ApikeysTokenEnum)`](../../doc/models/apikeys-token-enum.md) | Optional | Whether or not an AuthToken is required as part of the authentication when this Apikey is used.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **The authToken mechanism is disabled.**<br>- `1` - **The authToken mechanism is required for 'POST' and 'DELETE' requests.**<br></details><br> | getToken(): ?int | setToken(?int token): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified2",
  "creator": "String9",
  "modifier": "modifier6"
}
```

