
# Account Payment

## Structure

`AccountPayment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `method` | [`?int(AccountMethodEnum)`](../../doc/models/account-method-enum.md) | Optional | The type of the Account.<br><br><details><br><summary>Valid Values</summary><br>- `8` - **Checking**<br>- `9` - **Savings**<br>- `10` - **Corporate Checking**<br>- `11` - **Corporate Savings**<br></details><br> | getMethod(): ?int | setMethod(?int method): void |
| `number` | `?string` | Optional | For credit payment method, the card number of the credit card associated with this Transaction.<br>For eCheck payment method, the bank account number associated with this Transaction. | getNumber(): ?string | setNumber(?string number): void |
| `last4` | `?string` | Optional | - | getLast4(): ?string | setLast4(?string last4): void |
| `routing` | `?string` | Optional | The routing code for the eCheck or bank account payment associated with this Transaction. | getRouting(): ?string | setRouting(?string routing): void |
| `bin` | `?string` | Optional | - | getBin(): ?string | setBin(?string bin): void |
| `payment` | `?string` | Optional | - | getPayment(): ?string | setPayment(?string payment): void |
| `lastChecked` | `?string` | Optional | - | getLastChecked(): ?string | setLastChecked(?string lastChecked): void |
| `mask` | `?string` | Optional | - | getMask(): ?string | setMask(?string mask): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified6",
  "creator": "String5",
  "modifier": "modifier0"
}
```

