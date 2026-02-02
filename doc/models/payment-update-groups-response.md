
# Payment Update Groups Response

## Structure

`PaymentUpdateGroupsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this resource belongs to. | getEntity(): | setEntity( entity): void |
| `processing` | `?int` | Optional | Whether payment is processing. | getProcessing(): ?int | setProcessing(?int processing): void |
| `processed` | `?int` | Optional | Whether payment is processed. | getProcessed(): ?int | setProcessed(?int processed): void |
| `numberUpdated` | [`?int(PaymentNumberUpdatedModelEnum)`](../../doc/models/payment-number-updated-model-enum.md) | Optional | Whether payment number changes.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Updated**<br>- `1` - **Updated**<br></details><br> | getNumberUpdated(): ?int | setNumberUpdated(?int numberUpdated): void |
| `expirationUpdated` | [`?int(PaymentExpirationUpdatedEnum)`](../../doc/models/payment-expiration-updated-enum.md) | Optional | Whether token expiration date changes.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Updated**<br>- `1` - **Updated**<br></details><br> | getExpirationUpdated(): ?int | setExpirationUpdated(?int expirationUpdated): void |
| `payment` | [`?PaymentResponse`](../../doc/models/payment-response.md) | Optional | - | getPayment(): ?PaymentResponse | setPayment(?PaymentResponse payment): void |
| `paymentUpdates` | [`?(PaymentUpdatesResponse[])`](../../doc/models/payment-updates-response.md) | Optional | - | getPaymentUpdates(): ?array | setPaymentUpdates(?array paymentUpdates): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified2",
  "creator": "String9",
  "modifier": "modifier6"
}
```

