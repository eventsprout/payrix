
# Subscriptions Response

## Structure

`SubscriptionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `plan` | string\|[PlansResponse](../../doc/models/plans-response.md)\|null | Optional | The identifier of the Plan that this Subscription is associated with. The Plan determines the frequency and amount of each payment. | getPlan(): | setPlan( plan): void |
| `statementEntity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | For a plan that is attached to a billing, this is the paying entity to match to the generated statements of that billing for which the recurring payments will be made. | getStatementEntity(): | setStatementEntity( statementEntity): void |
| `firstTxn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The identification of the first transaction processed through this subscription. This is used internally to process subsequent transactions. | getFirstTxn(): | setFirstTxn( firstTxn): void |
| `start` | `?int` | Optional | The date on which the Subscription should start. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. The value of this field must represent a date in the future. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which the Subscription should finish. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. The value of this field must represent a date in the future. | getFinish(): ?int | setFinish(?int finish): void |
| `tax` | `?int` | Optional | The amount of the total sum of this Subscription that is made up of tax. This field is specified as an integer in cents. | getTax(): ?int | setTax(?int tax): void |
| `descriptor` | `?string` | Optional | The descriptor used in this Subscription. This field is stored as a text string and must be between 1 and 50 characters long. If a value is not set, an attempt is made to set a default value from the merchant information. | getDescriptor(): ?string | setDescriptor(?string descriptor): void |
| `txnDescription` | `?string` | Optional | The description of the Txn that will be created through this Subscription. | getTxnDescription(): ?string | setTxnDescription(?string txnDescription): void |
| `order` | `?string` | Optional | The order of the Txn that will be created through this Subscription. | getOrder(): ?string | setOrder(?string order): void |
| `origin` | [`?int(SubscriptionOriginEnum)`](../../doc/models/subscription-origin-enum.md) | Optional | The origin of the Txn that will be created through this Subscription.<br><br><details><br><summary>Valid Values</summary><br>- `2` - **Customer will be subscribing through eCommerce.**<br>- `3` - **Customer will be subscribing by Mail Order/Telephone.**<br>- `4` - **Originated with Apple Pay.**<br>- `5` - **Originated as a Successful 3D Secure transaction.**<br>- `6` - **Originated as an Attempted 3D Secure transaction.**<br>- `8` - **Originated in a Payframe.**<br></details><br>**Default**: `SubscriptionOriginEnum::ECOMMERCE`<br> | getOrigin(): ?int | setOrigin(?int origin): void |
| `authentication` | `?string` | Optional | Authentication token for 3D Secure transactions. | getAuthentication(): ?string | setAuthentication(?string authentication): void |
| `authenticationId` | `?string` | Optional | Authentication reference ID for 3D Secure transactions. | getAuthenticationId(): ?string | setAuthenticationId(?string authenticationId): void |
| `failures` | `?int` | Optional | The current count of consecutive payment failures for this subscription. | getFailures(): ?int | setFailures(?int failures): void |
| `maxFailures` | `?int` | Optional | The maximum consecutive amount of payment failures to allow for this subscription before inactivating it. | getMaxFailures(): ?int | setMaxFailures(?int maxFailures): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `invoices` | [`?(InvoicesResponse[])`](../../doc/models/invoices-response.md) | Optional | - | getInvoices(): ?array | setInvoices(?array invoices): void |
| `subscriptionTokens` | [`?(SubscriptionTokensResponse[])`](../../doc/models/subscription-tokens-response.md) | Optional | - | getSubscriptionTokens(): ?array | setSubscriptionTokens(?array subscriptionTokens): void |

## Example (as JSON)

```json
{
  "origin": 2,
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created4",
  "modified": "modified6",
  "creator": "String5",
  "modifier": "modifier0"
}
```

