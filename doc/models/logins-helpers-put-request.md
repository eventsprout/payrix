
# Logins Helpers Put Request

## Structure

`LoginsHelpersPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loginAsEnabled` | [`?int(LoginHelpersLoginAsEnabledEnum)`](../../doc/models/login-helpers-login-as-enabled-enum.md) | Optional | Whether the associated login can use loginAs or not.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **OFF**<br>- `1` - **ON**<br></details><br> | getLoginAsEnabled(): ?int | setLoginAsEnabled(?int loginAsEnabled): void |

## Example (as JSON)

```json
{
  "loginAsEnabled": 0
}
```

