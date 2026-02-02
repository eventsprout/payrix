
# Token Post Request

## Structure

`TokenPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customer` | string\|[CustomersPostRequest](../../doc/models/customers-post-request.md) | Required | The Customer that this Token is associated with. | getCustomer(): | setCustomer( customer): void |
| `payment` | string\|[PaymentPostRequest](../../doc/models/payment-post-request.md) | Required | The payment method that is associated with this Token. | getPayment(): | setPayment( payment): void |
| `expiration` | `?string` | Optional | The expiry month for the payment method associated with this Token.In This field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023. The value must reflect a future date. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `name` | `?string` | Optional | The name of this Token. This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Token. This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `custom` | `?string` | Optional | Custom, free-form field for client-supplied text, must be between 0 and 1000 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `authTokenCustomer` | `?string` | Optional | The customer reference from the authToken used for user authentication | getAuthTokenCustomer(): ?string | setAuthTokenCustomer(?string authTokenCustomer): void |
| `origin` | `?int` | Optional | The origin of the token. | getOrigin(): ?int | setOrigin(?int origin): void |
| `entryMode` | `?int` | Optional | Entry mode set to the token. | getEntryMode(): ?int | setEntryMode(?int entryMode): void |
| `omnitoken` | `?string` | Optional | The omnitoken value. If this field has a value, the whole record is treated as an omnitoken. | getOmnitoken(): ?string | setOmnitoken(?string omnitoken): void |
| `status` | [`string(TokenStatusEnum)`](../../doc/models/token-status-enum.md) | Required | Indicates if this token is ready for use in transactions and subscriptions or not.<br>A token without complete payment details will be marked as 'pending'.<br><br><details><br><summary>Valid Values</summary><br>- `pending` - **The payment data is not yet available, Token is not ready for use.**<br>- `ready` - **The payment data is available, Token is ready for use.**<br><br></details><br> | getStatus(): string | setStatus(string status): void |
| `inactive` | [`int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Required | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): int | setInactive(int inactive): void |
| `frozen` | [`int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Required | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): int | setFrozen(int frozen): void |
| `subscriptionTokens` | [`?(SubscriptionTokensPostRequest[])`](../../doc/models/subscription-tokens-post-request.md) | Optional | - | getSubscriptionTokens(): ?array | setSubscriptionTokens(?array subscriptionTokens): void |
| `txns` | [`?(TxnsPostRequest[])`](../../doc/models/txns-post-request.md) | Optional | - | getTxns(): ?array | setTxns(?array txns): void |

## Example (as JSON)

```json
{
  "customer": "t1_cus_00c82eb304b0067620c7",
  "status": "pending",
  "payment": {
    "method": 1,
    "number": "378734493671000",
    "routing": "code",
    "last4": "last42",
    "bin": "bin6"
  },
  "expiration": "0123",
  "name": "test",
  "description": "test Token",
  "custom": "Custom Token Processor 2",
  "authTokenCustomer": "authToken",
  "origin": 2,
  "entryMode": 2,
  "omnitoken": "123",
  "inactive": 0,
  "frozen": 0
}
```

