
# Billing Events Put Request

## Structure

`BillingEventsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billing` | `?string` | Optional | The billing to which this billingEvent applies. | getBilling(): ?string | setBilling(?string billing): void |
| `event` | [`?string(BillingEventEnum)`](../../doc/models/billing-event-enum.md) | Optional | The type of event that triggers billing.<br><br><details><br><summary>Valid Values</summary><br>- `fees` - **Fee.** Fee events trigger the billing configuration.<br>- `chargebacks` - **Chargebacks.** Chargeback events trigger the billing configuration.<br>- `returns` - **Returns.** Return events trigger the billing configuration.<br>- `profitShares` - **Profit Shares.** Profit Sharing events trigger the billing configuration.<br>- `revShares` - **RevShares.** Rev Sharing events trigger the billing configuration.<br></details><br> | getEvent(): ?string | setEvent(?string event): void |
| `eventSchedule` | `?string` | Optional | The record ID of a specific schedule for the event chosen for which the billing configuration applies, all other records of the same event are excluded. | getEventSchedule(): ?string | setEventSchedule(?string eventSchedule): void |
| `deductFromBalance` | [`?int(BillingEventsDeductFromBalanceEnum)`](../../doc/models/billing-events-deduct-from-balance-enum.md) | Optional | Whether to deduct the billing amount from the entity's account balance.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Do not deduct from balance.**<br>- `1` - **Deduct from balance.**<br></details><br> | getDeductFromBalance(): ?int | setDeductFromBalance(?int deductFromBalance): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "billing": "t1_bil_67d9cfac37cb75f7c8e0597",
  "event": "fees",
  "eventSchedule": "record ID",
  "deductFromBalance": 0,
  "inactive": 0,
  "frozen": 0
}
```

