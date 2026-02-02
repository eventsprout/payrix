
# Payment Updates Response

## Structure

`PaymentUpdatesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `paymentUpdateGroup` | string\|[PaymentUpdateGroupsResponse](../../doc/models/payment-update-groups-response.md)\|null | Optional | The PaymentGroup resource that this PaymentUpdate belongs to. | getPaymentUpdateGroup(): | setPaymentUpdateGroup( paymentUpdateGroup): void |
| `payment` | string\|[PaymentResponse](../../doc/models/payment-response.md)\|null | Optional | The payment associated with this PaymentUpdate. | getPayment(): | setPayment( payment): void |
| `status` | [`?string(PaymentUpdateStatusEnum)`](../../doc/models/payment-update-status-enum.md) | Optional | The status of the payment update.<br><br><details><br><summary>Valid Values</summary><br>- `pending` - **The Payment Update was sent and is pending to be processed.**<br>- `processing` - **The Payment Update was received and is processing.**<br>- `failed` - **The Payment Update has failed.**<br>- `processed` - **The Payment Update was processed.**<br></details><br>**Default**: `PaymentUpdateStatusEnum::PENDING`<br> | getStatus(): ?string | setStatus(?string status): void |
| `token` | string\|[TokensResponse](../../doc/models/tokens-response.md)\|null | Optional | The ID of the token record to associate with this terminal activation request. | getToken(): | setToken( token): void |
| `account` | string\|[AccountsResponse](../../doc/models/accounts-response.md)\|null | Optional | The account associated with this Payment being updated. Used for instant funding payouts. | getAccount(): | setAccount( account): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `ref` | `?string` | Optional | A platform reference for this PaymentUpdate. This field is stored as a text string and must be between 0 and 50 characters long. | getRef(): ?string | setRef(?string ref): void |
| `clientRef` | `?string` | Optional | An internally generated reference for this PaymentUpdate. This field is stored as a text string and must be between 1 and 50 characters long. | getClientRef(): ?string | setClientRef(?string clientRef): void |
| `message` | `?string` | Optional | The message with details about the outcome of the paymentUpdate. This field is stored as a text string and must be between 0 and 500 characters long. | getMessage(): ?string | setMessage(?string message): void |
| `expiration` | `?string` | Optional | The expiration number of the payment being updated, this field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023. | getExpiration(): ?string | setExpiration(?string expiration): void |

## Example (as JSON)

```json
{
  "status": "pending",
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

