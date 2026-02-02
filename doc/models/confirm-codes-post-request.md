
# Confirm Codes Post Request

## Structure

`ConfirmCodesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The identifier of the Login resource that this confirmation code relates to. | getLogin(): string | setLogin(string login): void |
| `type` | [`string(ConfirmCodeTypeEnum)`](../../doc/models/confirm-code-type-enum.md) | Required | The type of this confirmCode.<br><br><details><br><summary>Valid Values</summary><br>- `password` - **Forgot Password**<br>- `email` - **Verify Email**<br></details><br> | getType(): string | setType(string type): void |
| `key` | `string` | Required | The cryptographically secure, randomly generated key to be used for verification. | getKey(): string | setKey(string key): void |
| `email` | `?string` | Optional | If the 'type' of this confirmation code is '2' (email), then this field represents the email address that requires verification. | getEmail(): ?string | setEmail(?string email): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "p1_log_67dd2714959c3331228ffa3",
  "type": "email",
  "key": "fbdf954596b341d18cb4995b70d321f3",
  "email": "vijay.sample@payrix.com",
  "inactive": 0,
  "frozen": 0
}
```

