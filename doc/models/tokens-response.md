
# Tokens Response

## Structure

`TokensResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `customer` | string\|[CustomersResponse](../../doc/models/customers-response.md)\|null | Optional | The Customer that this Token is associated with. | getCustomer(): | setCustomer( customer): void |
| `payment` | string\|[PaymentResponse](../../doc/models/payment-response.md)\|null | Optional | The payment method that is associated with this Token. | getPayment(): | setPayment( payment): void |
| `status` | [`?string(TokenStatusEnum)`](../../doc/models/token-status-enum.md) | Optional | Indicates if this token is ready for use in transactions and subscriptions or not.<br>A token without complete payment details will be marked as 'pending'.<br><br><details><br><summary>Valid Values</summary><br>- `pending` - **The payment data is not yet available, Token is not ready for use.**<br>- `ready` - **The payment data is available, Token is ready for use.**<br><br></details><br> | getStatus(): ?string | setStatus(?string status): void |
| `token` | `?string` | Optional | The auto-generated token identifier. | getToken(): ?string | setToken(?string token): void |
| `track` | `?string` | Optional | The magnetic stripe track data for the payment record for use in a transaction. | getTrack(): ?string | setTrack(?string track): void |
| `cvv` | `?string` | Optional | The CVV (Card Verification Value) for the payment record for use in a transaction | getCvv(): ?string | setCvv(?string cvv): void |
| `expiration` | `?string` | Optional | The expiry month for the payment method associated with this Token.<br>This field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023.<br>The value must reflect a future date. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `name` | `?string` | Optional | The name of this Token.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Token.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `custom` | `?string` | Optional | Custom, free-form field for client-supplied text, must be between 0 and 1000 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `authTokenCustomer` | `?string` | Optional | The customer reference from the authToken used for user authentication | getAuthTokenCustomer(): ?string | setAuthTokenCustomer(?string authTokenCustomer): void |
| `origin` | `?string` | Optional | The origin of the token. | getOrigin(): ?string | setOrigin(?string origin): void |
| `entryMode` | `?int` | Optional | Entry mode set to the token. | getEntryMode(): ?int | setEntryMode(?int entryMode): void |
| `omnitoken` | `?string` | Optional | The omnitoken value. If this field has a value, the whole record is treated as an omnitoken. | getOmnitoken(): ?string | setOmnitoken(?string omnitoken): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `paymentUpdates` | [`?(PaymentUpdatesResponse[])`](../../doc/models/payment-updates-response.md) | Optional | - | getPaymentUpdates(): ?array | setPaymentUpdates(?array paymentUpdates): void |
| `subscriptionTokens` | [`?(SubscriptionTokensResponse[])`](../../doc/models/subscription-tokens-response.md) | Optional | - | getSubscriptionTokens(): ?array | setSubscriptionTokens(?array subscriptionTokens): void |
| `txns` | [`?(TxnsResponse[])`](../../doc/models/txns-response.md) | Optional | - | getTxns(): ?array | setTxns(?array txns): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

