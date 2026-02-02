
# Txn Sessions Post Request

## Structure

`TxnSessionsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The login under which to perform this action. If you do not supply a login in this field, then the API defaults to the login that is currently authenticated. | getLogin(): string | setLogin(string login): void |
| `merchant` | `string` | Required | The Merchant being used to create this txn session. | getMerchant(): string | setMerchant(string merchant): void |
| `configurations` | [`?TxnSessionsConfigurations`](../../doc/models/txn-sessions-configurations.md) | Optional | Configurable data to be used to enhance security. | getConfigurations(): ?TxnSessionsConfigurations | setConfigurations(?TxnSessionsConfigurations configurations): void |

## Example (as JSON)

```json
{
  "login": "t1_log_65a6bb6506be50d9406eb00",
  "merchant": "t1_mer_66312e43815957c6767000z",
  "configurations": {
    "duration": 8,
    "maxTimesApproved": 2,
    "maxTimesUse": 4
  }
}
```

