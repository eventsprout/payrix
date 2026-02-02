
# Billing Events Response

## Structure

`BillingEventsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `billing` | string\|[BillingsResponse](../../doc/models/billings-response.md)\|null | Optional | The identifier of the Billing that this billingEvent applies to. | getBilling(): | setBilling( billing): void |
| `event` | [`?string(BillingEventEnum)`](../../doc/models/billing-event-enum.md) | Optional | The type of event that triggers billing.<br><br><details><br><summary>Valid Values</summary><br>- `fees` - **Fee.** Fee events trigger the billing configuration.<br>- `chargebacks` - **Chargebacks.** Chargeback events trigger the billing configuration.<br>- `returns` - **Returns.** Return events trigger the billing configuration.<br>- `profitShares` - **Profit Shares.** Profit Sharing events trigger the billing configuration.<br>- `revShares` - **RevShares.** Rev Sharing events trigger the billing configuration.<br></details><br> | getEvent(): ?string | setEvent(?string event): void |
| `eventSchedule` | `?string` | Optional | The record ID of a specific schedule for the event chosen for which the billing configuration applies, all other records of the same event are excluded. | getEventSchedule(): ?string | setEventSchedule(?string eventSchedule): void |
| `deductFromBalance` | [`?int(BillingEventsDeductFromBalanceEnum)`](../../doc/models/billing-events-deduct-from-balance-enum.md) | Optional | Whether to deduct the billing amount from the entity's account balance.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Do not deduct from balance.**<br>- `1` - **Deduct from balance.**<br></details><br> | getDeductFromBalance(): ?int | setDeductFromBalance(?int deductFromBalance): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier6"
}
```

