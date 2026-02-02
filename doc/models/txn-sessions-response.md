
# Txn Sessions Response

## Structure

`TxnSessionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The login under which to perform this action. If you do not supply a login in this field, then the API defaults to the login that is currently authenticated. | getLogin(): | setLogin( login): void |
| `merchant` | `?string` | Optional | The Merchant being used to create this txn session. | getMerchant(): ?string | setMerchant(?string merchant): void |
| `status` | `?string` | Optional | The current status of this key. | getStatus(): ?string | setStatus(?string status): void |
| `configurations` | [`?TxnSessionsConfigurations`](../../doc/models/txn-sessions-configurations.md) | Optional | Configurable data to be used to enhance security. | getConfigurations(): ?TxnSessionsConfigurations | setConfigurations(?TxnSessionsConfigurations configurations): void |
| `origin` | `?string` | Optional | The origin from this request. | getOrigin(): ?string | setOrigin(?string origin): void |
| `durationAvailable` | `?int` | Optional | Specifies the number of minutes for which the key remains valid. Once this duration expires, the key will be automatically voided and cannot be used. | getDurationAvailable(): ?int | setDurationAvailable(?int durationAvailable): void |
| `timesUsed` | `?int` | Optional | Indicates the number of times the key has been used to make requests. | getTimesUsed(): ?int | setTimesUsed(?int timesUsed): void |
| `timesApproved` | `?int` | Optional | Indicates the number of approved transactions that have been made using this key. | getTimesApproved(): ?int | setTimesApproved(?int timesApproved): void |
| `key` | `?string` | Optional | The randomly generated key used to authenticate a user. | getKey(): ?string | setKey(?string key): void |

## Example (as JSON)

```json
{
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

