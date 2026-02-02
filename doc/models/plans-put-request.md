
# Plans Put Request

## Structure

`PlansPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?int` | Optional | The amount to charge with each payment under this Plan, specified as an integer in cents. | getAmount(): ?int | setAmount(?int amount): void |
| `billing` | `?string` | Optional | The attached billing for which recurring payments should be made to pay off statements. | getBilling(): ?string | setBilling(?string billing): void |
| `order` | `?string` | Optional | The order of the Txn that will be created through this Plan. | getOrder(): ?string | setOrder(?string order): void |
| `txnDescription` | `?string` | Optional | The description of the Txn that will be created through this Plan. | getTxnDescription(): ?string | setTxnDescription(?string txnDescription): void |
| `description` | `?string` | Optional | A description of this Plan. This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `maxFailures` | `?int` | Optional | The maximum consecutive amount of payment failures to allow for a subscription before inactivating it. | getMaxFailures(): ?int | setMaxFailures(?int maxFailures): void |
| `name` | `?string` | Optional | The name of this Plan. This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `schedule` | [`?int(PlanScheduleEnum)`](../../doc/models/plan-schedule-enum.md) | Optional | The schedule that determines when the subscription related to this Plan is triggered.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Daily**<br>- `2` - **Weekly**<br>- `3` - **Monthly**<br>- `4` - **Annually**<br></details><br> | getSchedule(): ?int | setSchedule(?int schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, such as daily, weekly, monthly, or annually; this field is specified as an integer and its value determines how the interval is multiplied. | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `um` | [`?string(PlanUmEnum)`](../../doc/models/plan-um-enum.md) | Optional | The unit of measure for the amount on the plan.<br><br><details><br><summary>Valid Values</summary><br>- `actual` - **An actual amount to charge, in cents.**<br>- `percent` - **A percentage of another amount, in basis points.**<br></details><br>**Default**: `PlanUmEnum::ACTUAL`<br> | getUm(): ?string | setUm(?string um): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "name": "Lind - Wyman Subscription Plan weekly",
  "description": "Payment",
  "schedule": 1,
  "scheduleFactor": 1,
  "amount": 50000,
  "inactive": 0,
  "frozen": 0,
  "maxFailures": 2,
  "type": "recurring",
  "txnDescription": "Payment Plan",
  "order": "S1 - 1000 - LAST",
  "billing": "p1_bil_00cee36329ead6ae6d31e43",
  "um": "actual"
}
```

