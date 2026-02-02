
# Token Results Response

## Structure

`TokenResultsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `txn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The identifier of the Txn resource that this tokenResult relates to. | getTxn(): | setTxn( txn): void |
| `token` | string\|[TokensResponse](../../doc/models/tokens-response.md)\|null | Optional | The identifier of the Token resource that this tokenResult relates to. | getToken(): | setToken( token): void |
| `merchant` | string\|[MerchantsResponse](../../doc/models/merchants-response.md)\|null | Optional | The identifier of the Merchant resource that this tokenResult relates to. | getMerchant(): | setMerchant( merchant): void |
| `code` | [`?string(TokenResultsCodeEnum)`](../../doc/models/token-results-code-enum.md) | Optional | The code type of the tokenResult.<br><br><details><br><summary>Valid Values</summary><br>- `omnitokenMinting` - **Indicates omnitoken minting event**<br>- `omnitokenLookup` - **Indicates omnitoken lookup event**<br>- `omnitokenUsage` - **Indicates omnitoken usage event**<br></details><br> | getCode(): ?string | setCode(?string code): void |
| `omniToken` | `?string` | Optional | The omniToken value. | getOmniToken(): ?string | setOmniToken(?string omniToken): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

