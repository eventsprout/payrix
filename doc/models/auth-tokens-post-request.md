
# Auth Tokens Post Request

## Structure

`AuthTokensPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this resource. | getLogin(): string | setLogin(string login): void |
| `customer` | `string` | Required | The customer identifier from the AuthToken used during authentication. | getCustomer(): string | setCustomer(string customer): void |
| `token` | `string` | Required | The auto-generated token identifier. | getToken(): string | setToken(string token): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_6372b01eed9b6a8c75ac8a3",
  "customer": "000a1eafdfdb335179adf94c1d8bc36d",
  "token": "261cf67bb2dc20f492abcdb39ecee847",
  "inactive": 0,
  "frozen": 0
}
```

